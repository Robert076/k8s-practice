# pod.yaml 

This is a **declarative** configuration file that defines the desired state of a pod.

Instead of manually creating a Pod using imperative commands, we create a .yaml file to define what the Pod should like, making it easier to use by only running

`kubectl apply -f pod.yaml`

A pod is an abstraction over the container runtime. It is the smallest unit in Kuberenetes. It wraps one (or sometimes more) containers.
