# Pulsar manager version 0.3.0, kubernetes deployment

Manifests for pulsar-manager to deploy in EKS cluster.

[Pulsar Manager](https://pulsar.apache.org/docs/en/administration-pulsar-manager/) is a web-based GUI management and monitoring tool that helps administrators and users manage and monitor tenants, namespaces, topics, subscriptions, brokers, clusters, and so on, and supports dynamic configuration of multiple environments.

## Prerequisites

- broker (pulsar broker must be up and running)
- bookkeeper (pulsar bookkeeper must be up and running)

> **Note**: Make sure to check the name of existing services for `broker and bookkeeper` and change them @configmap and @statefulset before deploy it.

## Installing

To install run the following commands:

```bash
$ kubectl apply -f pulsar-manager-configmap.yaml
$ kubectl apply -f pulsar-manager-statefulset.yaml
$ kubectl apply -f pulsar-manager-services.yaml
$ kubectl apply -f pulsar-manager-batch-job.yaml
```

The commands deploys the `pulsar manager` on the EKS cluster in the default configuration.

The docker image used for this deployment is the Streamnative maintained pulsar-manager version 0.3.0 chart.

### To check it out view the AWS Load Balancer link of the Frontend service:

```bash
$ kubectl get services
```
> **Note**: To access the Pulsar manager dashboard use the username and password **pulsar**.
