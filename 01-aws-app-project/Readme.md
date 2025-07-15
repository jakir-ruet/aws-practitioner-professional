## Welcome to AWS App Project

### Preparing `Public Repository on ECR`

#### Build the Docker image locally

```bash
docker build -t aws-first-docker-app .
```

#### Tag the image for your ECR Public Repository

```bash
docker tag aws-first-docker-app:latest public.ecr.aws/a4v7z3x3/aws-first-docker-app:latest
```

#### Login to AWS Public ECR

```bash
aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws
```

#### Push your image

```bash
docker push public.ecr.aws/a4v7z3x3/aws-first-docker-app:latest
```

```bash
kubectl apply -f https://raw.githubusercontent.com/jakir-ruet/aws-beginners-professionals/master/01-aws-app-project/aws-app-project.yaml
```
