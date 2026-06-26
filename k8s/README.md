# Kubernetes deployment notes

## Quick start

```bash
kubectl apply -f namespace.yaml
kubectl get storageclass microk8s-hostpath >/dev/null 2>&1 || echo "microk8s-hostpath storage class is not available"
kubectl apply -f ollama.yaml
```

## Notes

- The deployment uses a hostPath-backed persistent volume at /home/nander/repos/gobble/models.
- The service exposes port 11434.
- The smoke-test job pulls the default Ollama model and runs a simple generation request automatically after deployment.
- Update the GitHub Actions secrets before enabling the workflow.
