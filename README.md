# Deploy service used GPUs with Kubernetes

K8s cluster contain types of GPUs and none GPUs

![alt](../images/cluster.png)

### Requirements

- Kubernetes worker nodes have to installed with NVIDIA drivers, nvidia-docker 2.0.

![alt](../images/nvidia-smi.png)

- `nvidia-container-runtime` must be configured as the default runtime for Docker. Change default docker runtime on `/etc/docker/daemon.json`.

```
{
    "default-runtime": "nvidia",
    "runtimes": {
        "nvidia": {
            "path": "/usr/bin/nvidia-container-runtime",
            "runtimeArgs": []
        }
    }
}
```

### Deploy

- Add label and taint on worker nodes GPU

```
kubectl label nodes <node-gpu> app=gpu
kubectl taint nodes <node-gpu> app=gpu:NoSchedule
```
- Install nvidia-device-plugin on worker nodes gpu

```

```

- Verification. Run deployment test

```

```

### Reference

- https://kubernetes.io/docs/tasks/manage-gpus/scheduling-gpus/