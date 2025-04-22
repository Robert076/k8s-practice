# pod.yaml 

This is a **declarative** configuration file that defines the desired state of a pod.

Instead of manually creating a Pod using imperative commands, we create a .yaml file to define what the Pod should like, making it easier to use by only running

`kubectl apply -f pod.yaml`

A pod is an abstraction over the container runtime. It is the smallest unit in Kuberenetes. It wraps one (or sometimes more) containers.

The structure of a .yaml file for declaring a pod looks like this:

```
apiVersion: v1 # specifies the kubernetes api version
kind: Pod # case-sensitive
metadata:
  name: your-pod-name-here # name of the pod
  labels:
    myKey: myValue # key-value labels for your pod, enables easier lookup down the line
specs:
  containers:
  - name: your-container-name-here
    image: image-name-from-dockerhub # or you can use the path to another image
```
