# Data and Volumes with Docker and Kubernetes

### Theory and Docker Comparison

- k8 can mount volumes into containers
- k8 can support a variety of types / drivers
  - greater control over where data is stored
    - Docker has basically no Driver / Type support (all files are stored locally) 
  - eg local volumes (i.e on nodes)
  - cloud provider specific volumes
- volumes are part of the Pod object
  - volumes are Pod specific
  - volume lifetime depends on the Pod lifeetime
  - volumes survive Container restarts / removal but are removed when Pods are destroyed
    - this means that data is not necessarily persistant in k8
    - whereas in Docker volumes do persist until manually cleared
- volumes are defined in the pod specification in deployment
- next to containers (same level)

### emptyDir

- creates a directory that will stay alive as long a Pod is alive
- containers can read and write from this directory.
- containers can be restarted. and the directory will survive
- because data is closely attached to pods if we have multiple pods then we will get different data

### hostPath

- hostPath is one step above pod... it directory is hosted on the worker node (may have multiple pods)
- similar to a bind mount
- hostPath path setting is like the src directory. wheere on the worker node the data is actually stored
  - be careful not to overwrite any folders required by the host operating system eg linux
- node specific
  - only the pods on the same node have access to this data

### csi

- added to make sure that they dont have to add more and more built in types for cloud providers and use cases
- its an api so that anyone can create drivers for interacting between hosts and k8
- for example aws has an efs - csi driver on github making it easy to use efs as as a storage solution
- its an integration driver
- many official drivers exists




