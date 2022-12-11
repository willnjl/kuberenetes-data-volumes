# Data and Volumes with Docker and Kubernetes

## notes

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

###

