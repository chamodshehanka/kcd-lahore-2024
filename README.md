# KCD Lahore 2024 - Smooth Saling with Helm

### Create a new Helm Chart
```bash

helm create kcdlahore-2024

```

### Install the Helm Chart
```bash

helm install kcdlahore-2024-release-1 ./kcdlahore-2024

```

### Upgrade the Helm Chart
```bash 

helm upgrade kcdlahore-2024-release-1 ./kcdlahore-2024

```

### Uninstall the Helm Chart
```bash

helm uninstall kcdlahore-2024-release-1

```

## Helm Hooks
```yaml

apiVersion: batch/v1
kind: Job
metadata:
  name: pre-install-hook
  namespace: {{ .Values.namespace }}
spec:
  template:
    spec:
      containers:
        - name: pre-install-hook
          image: alpine:latest
          command: ["echo", "Executing pre-installation hook"]
      restartPolicy: Never
  backoffLimit: 1
```

### Get the status of the Job
kubectl get jobs -n <namespace>

### Get the name of the Job pod
kubectl get pods -n <namespace>

### View the logs of the Job pod
kubectl logs <job-pod-name> -n <namespace>


