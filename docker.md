# TIL - docker

## Run a local registry

```bash
docker run -d -p 5000:5000 --restart=always --name registry registry:2
```

## Build image normally, and push it to local

```bash
docker build -t localhost:5000/my-image
```

```bash
docker push localhost:5000/my-image
```

## Aquire in yaml

```yaml
image: localhost:5000/my-image
```

## Remove all volumes

```bash
docker volume rm $(docker volume ls -q)
```

