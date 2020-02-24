# Hands-on labs Introduction to Docker

## Exercise 05: Push to an Azure Container Registry
To share container with others, or make them available on your cluster, your container images should be stored in a container registry. You can use Docker Hub for public images or a private registry like Azure Container Registry. 

- Go to Docker Hub and create an account or create an Azure Container Registry (or ask proctors for existing one)
- On the command line login to the registry

```
docker login
```

- Tag your container image to match the name of your repository. e.g. name.azurecr.io/imagename

```
docker tag image  name.azurecr.io/imagename
```

- Push your image to the registry
```
docker push name.azurecr.io/imagename
``` 
