# Clean up Docker repo

You must clean up repo every six months. 

The root of the docker hosted repository is at:

```
nexus-docker-publish.ship.gov.sg/<repo-name> 
```

### To clean up Docker repo

1. Log in to the docker registry using the following command:

    ```
    docker login nexus-docker-publish.ship.gov.sg
    ```

1. Add the following prefix to your images: 

    ```
    nexus-docker-publish.ship.gov.sg/<repo-name>
    ```

    For example, an alpine image would be tagged as such:

    ```
    docker tag <image original tag or image id> nexus-docker-publish.ship.gov.sg/<repo-name>/alpine
    ```

1. Push the image to the docker registry using the following command, assuming the same alpine image you have prepared in the previous step:

    ```
    docker push nexus-docker-publish.ship.gov.sg/<repo-name>/alpine
    ```

1. Pull the image using the following command:

    ```
    docker pull nexus-docker-publish.ship.gov.sg/<repo-name>/alpine
    ```

1. If you are using the docker proxy repo that points to docker registry, use the following commands. You can pull the images without login. 
    ```
    docker pull nexus-docker.ship.gov.sg/<image:tag>
    ```
    
    For example, 
    
    ```
    docker pull  nexus-docker.ship.gov.sg/alpine:latest
    ```

### Troubleshooting

[Troubleshooting](./snippets/troubleshooting.md ':include')


<!--In the pipeline, if you receive a `403` error or are **unable to update docker**, add the following commands before `docker login nexus-docker-publish.ship.gov.sg`

```
rm -f ~/.docker/config.json
```

```
docker logout
```

This is because the login points to the docker hub and needs to be refreshed using the above commands.-->

### Related Topics

- [Cleanup Policy](nexus-repository/nexus-repo-clean-up-policy)