# replicaset.yaml

Contains a **declarative** configuration of the desired state of our replica set.

A replica set manages multiple pods and makes sure that we have as many containers we desire running at all times.

In the *replicaset.yaml* file, for example:

```
apiVersion: apps/v1 # the api version that has replica sets
kind: ReplicaSet # case-sensitive
metadata: # name and labels for our replica set
  name: myapp-replicaset
  labels:
    type: front-end
specs:
  template: # template for our pod
    
    metadata: # name and labels for our pod (check pod/pod.yaml)
      name: myapp-pod
      labels:
        type: front-end
    specs:
      containers:
      - name: container-name
      - image: container-image

  replicas: 3 # how many pods we want to run, this changes overtime to adapt our needs
  selector: # the labels that will match (what our replica set will look over)
    matchLabels:
      type: front-end # each pod with the front-end tag will be replicated 3 times
```
