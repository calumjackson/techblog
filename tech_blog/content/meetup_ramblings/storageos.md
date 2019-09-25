---
title: "Kubernetes: 05/09"
date: 2019-09-13T15:59:47+01:00
draft: false
weight: 1
---

---

**My. First. Meetup.**

I turned up to this as a lone ranger, without knowing what to really expect other than the possibility of free beer and pizza! The CodeNode I was aware of from a previous Worldpay "mini tech conference" back in 2017, and has a cool setup. Note: maybe we should encourage someone to do another tech conference.

This meetup had been organised by [Infrastructure as Code](https://skillsmatter.com/groups/10787-london-infrastructure-as-code), under the [Skills matter](https://skillsmatter.com/) umbrella. It was quite light on talkers, however the StorageOs team spent a reasonable amount of time talking and demonstrating so it wasn't too short.

#### Kubernetes in a nutshell

Dennis initially gave a brief overview of Kubernetes, explaining the K8 pods as a group of containers within a Node/VM. Which was a very brief overview.

And then the walkthrough, where he setup a static website on a K8 cluster. You may as well just [watch the video](https://skillsmatter.com/skillscasts/14358-london-infrastructure-as-code-september#video) if you're interested.

He had a docker pod setup with a small sized image, built the image / app into a docker pod, pushed his image to his docker hub, started MiniKube & KubeCTL,

What I've learnt whilst following this:

* Setting up Docker was simple enough :smile:

* Spent a reasonable amount of time trying to host my HTML file onto the docker image. Basically I'd misunderstood the way of standing up the Docker build, and showed my time away from coding. The COPY command is pretty obvious, but I'd forgotten that the '.' stood for something, namely _everything in the folder you are running from_ :sob:

{{< highlight bash>}}
FROM nginx:alpine
COPY . /usr/share/nginx/html
EXPOSE 80
{{< / highlight >}}

* Once I understood that you copied the directory into the image rather (writing this out makes me feel super stupid, as this surely is one of the main concepts of containers :see_no_evil:), I was on my way.

I'll dive into the Kubernetes setup later on in this page, lest you fall asleep before the other points of interest. :sleeping:

### [StorageOS](https://skillsmatter.com/skillscasts/14359-running-stateful-applications-in-kubernetes)

The technical talk around this was interesting and quite thorough, particularly as it was showing the service in action whilst explaining the concepts. I've pretty shamelessly [stolen some of their diagrams](https://docs.storageos.com/docs/) below to help me remember what they talked about :laughing:

#### Data Transfer and High Availability

The platform was using replicated volumes across multiple nodes to provide data protections and high availability. Interestingly, the platform uses _synchronous_ replication across leader based replication for consistency. This means there is a round trip involved and that writes are dependent on a quorum being complete, and likely needs an aggressive failure identification model to determine if a node is non-accessible.

![high-avail](/images/meetup_pics/storageos/high-availability.png?classes=float-left,shadow)

This basically works in sending data to the primary data store first, and then replicating across the replica nodes. Replicas are aggressively replaced, and these are synced _asynchronously_ and work with eventual consistency until they are in sync. (This means that the new replica will not require acknowledgements until it is in sync).

![architecture](/images/meetup_pics/storageos/storageos-cluster.png)


This separates the storage from the application (this is same as cassandra?), which means if the application fails the storage isn't lost (because the database is contained within the container, and K8s can take up to 5 minutes to be deemed as lost.)

Another key feature is that the storage is failed over between availability zones if one goes down.

---

### Running a basic Kubernetes app

Steps to run a docker image in Kubernetes (I've excluded [instaling minikube, kubectl, and vmware](https://kubernetes.io/docs/tasks/tools/install-minikube/) as this was relatively straightforward)

Builds the image into a docker pod

{{< highlight bash>}}
$ sudo docker build -t practice-app .
{{< / highlight >}}

Run the docker pod against a particular port, and started minikube

{{< highlight bash>}}
$ sudo docker run -d -p 80:80
$ minikube start
{{< / highlight >}}

Logged into the dockerhub instance

{{< highlight bash>}}
$ sudo docker login --username=yourUserName
$ sudo docker tag 209cd5379600 yourUserName/practice-app:101
$ sudo docker push yourUserName/practice-app:101
{{< / highlight >}}

Within kubernetes, run the container application against a particular port. Can check the yaml file to see the current configuration.

{{< highlight bash>}}
$ kubectl run practice-app --image=yourUserName/practice-app:101 --port=80
$ kubectl get deployment --export -o yaml
{{< / highlight >}}

Expose the deployment against the internal NodePort. 'Get service' will return the details of the deployment.

{{< highlight bash>}}
$ kubectl expose deployment practice-app --type=NodePort
$ kubectl get service
{{< / highlight >}}

Get the url of where the service is running - removing the --url hint will trigger the web browser to open at that page.

{{< highlight bash>}}
$ minikube service practice-app --url
$ minikube service practice-app
{{< / highlight >}}

Finally, to scale out to X amounts of replicas. The -o wide commands below allow all details about the services to be seen.

{{< highlight bash>}}
$ kubectl scale deployment practice-app --replicas=4
$ kubectl get po -o wide
{{< / highlight >}}
