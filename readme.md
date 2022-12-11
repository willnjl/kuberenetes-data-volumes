# Data and Volumes with Docker and Kubernetes

## notes

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
- 


