

## Resource limit in docker container

*  Resources: CPU, memory, GPU
*  Requests means reserve, are what the container is guaranteed to get
*  Limits, make sure a container never goes above a certain value
// CPU limit, memory limit


```
docker run -it --cpus=".5" ubuntu /bin/bash
```

*  1m CPU = 1 / 1000 Core (mili-core)
*  1m Memory = 1 Medibyte(megabyte)

Generally, you should do resource planning before deploy: specify resource request and limit

// millicores. If your container needs two full cores to run, you would put the value “2000m”
//  If your app starts hitting your CPU limits, Kubernetes starts throttling your container. This means the CPU will be artificially restricted, giving your app potentially worse performance! However, it won’t be terminated or evicted

//  mebibyte 2^20
// , if a container goes past its memory limit it will be terminated.

//  it’s important that the containers have enough resources to actually run

// K8s pod schedule build based on it




// ## Proxy

// Create a proxy to remote Pods
// Kubectl proxy save your trouble to put request credential because kubectl already has it.
 //  ![20200705211742](https://raw.githubusercontent.com/eliteGoblin/images/master/blog/img/picgo/20200705211742.png)