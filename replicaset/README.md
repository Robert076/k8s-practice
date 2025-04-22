# replicaset.yaml

Contains a **declarative** configuration of the desired state of our ReplicaSet.

A ReplicaSet manages multiple Pods and makes sure that we have as many Pods we desire running at all times.

In the *replicaset.yaml* file, for example:

```
apiVersion: apps/v1 # the api version that has ReplicaSets
kind: ReplicaSet # case-sensitive
metadata: # name and labels for our ReplicaSet
  name: myapp-replicaset
  labels:
    type: front-end
specs:
  template: # template for our Pod
    
    metadata: # name and labels for our Pod (check pods/pod.yaml)
      name: myapp-pod
      labels:
        type: front-end
    specs:
      containers:
      - name: container-name
      - image: container-image

  replicas: 3 # how many Pods we want to run, this changes overtime to adapt our needs
  selector: # the labels that will match (what our ReplicaSet will look over)
    matchLabels:
      type: front-end # each Pod with the front-end tag will be replicated 3 times
```

The ReplicaSet fulfills its purpose by creating and deleting Pods as needed to reach the desired number.

A ReplicaSet ensures that a spdecific number of Pod replicas are running at any given time, however a Deployment is a higher-level concept that manages ReplicaSets. ReplicaSets should be directly used when you require custom update orchestration only. 
