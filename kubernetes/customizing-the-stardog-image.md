# Customizing the Stardog Image

To customize the Stardog image in k8s we recommend extending the base Stardog image and pushing your custom image into a container registry, either a local or on-prem registry, or a cloud-based one, such as DockerHub, Elastic Container Registry \(ECR\), Google Container Registry \(GCR\), or Azure Container Registry \(ACR\).

As an example, to configure an image with extra client drivers, create a Dockerfile:

```text
FROM stardog/stardog:latest
RUN mkdir -p /var/opt/drivers/
COPY ./elasticsearch-rest-client-7.4.0.jar /var/opt/drivers/
ENV STARDOG_EXT=/var/opt/drivers/
```

This defines a simple Docker image, based on Stardog’s official image hosted on DockerHub, which adds the Elastic Search client and sets the `STARDOG_EXT` environment variable. When this image is run the `ENTRYPOINT` for the `stardog/stardog:latest` image will be used to start Stardog but with the additions included in the custom Dockerfile.

After creating the Dockerfile, you need to build, tag, and push it into your registry \(authenticating as required\). Below we build the image and push it to ECR with a custom tag:

```text
docker build . -t customstardog:0.0.1
$(aws ecr get-login --region us-west-1 --no-include-email)
docker push customstardog:0.0.1
```

Once your image is available, you can set the `image.*` parameters for Helm to deploy Stardog cluster into k8s with your custom image.

You can read more about the various container registries in their respective documentations: [ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/images.html), [GCR](https://cloud.google.com/container-registry/docs/), and [ACR](https://docs.microsoft.com/en-us/azure/container-registry/).

