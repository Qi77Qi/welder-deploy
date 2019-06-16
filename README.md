# welder-deploy

## Run welder locally
Prerequisites
- Enable kubernetes in local docker desktop
- Run `gcloud auth application-default login`
- Run `kubectl config current-context` and make sure it outputs `docker-for-desktop`
- Update `path: /Users/qi/.config` in `kubernetest-deployment.yaml` to your own home directory

Deploy
- Run `kubectl apply -f kubernetest-deployment.yaml`
- Accessing welder
  - Try `curl 127.0.0.1:30000/status` and you should see something like `{"buildTime":"Sun Jun 16 02:47:53 UTC 2019","gitHeadCommit":"a28c8c543cf21015f212613da5eea1666dc0b2b8"}`
- Accessing jupyter
  - `http://127.0.0.1:30001/tree`

### Useful kubectl commands

- SSH to a container: `kubectl exec -it welder-859f865b5d-4dmvp --container jupyter -- /bin/bash`
- List pods: `kubectl get pods`