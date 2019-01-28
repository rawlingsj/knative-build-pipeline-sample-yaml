# Sample Knative Build Pipeline

## Add helm repo
```
helm repo add jenkins-x https://storage.googleapis.com/chartmuseum.jenkins-x.io
```
## Install Knative Build Pipline

Using your Git and Dockerhub credentials
```
helm upgrade --install --set auth.docker.username=fred --set auth.docker.password=flintstone --set auth.docker.url=https://index.docker.io/v1/ --set auth.git.username=test-bot-user --set auth.git.password=abcdef12345 --set auth.git.url=https://github.com knative-build-pipeline jenkins-x/knative-build-pipeline
```

## Clone repo
```
git clone https://github.com/rawlingsj/knative-build-pipeline-sample-yaml.git && cd knative-build-pipeline-sample-yaml
```
## Replace `rawlingsj` with your dockerhub username
```
sed s/rawlingsj/[YOUR_DOCKERHUB_USERNAME]/g yaml/1-image-pipeline-resource.yaml
```
```
kubectl apply -f yaml/
```
