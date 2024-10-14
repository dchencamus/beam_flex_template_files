This repository contains files that can will be used to create a beam flex template. 

The current release uses the following image tags:
- gcr.io/dataflow-templates-base/python310-template-launcher-base:flex_templates_base_image_release_20240918_RC00
- apache/beam_python3.10_sdk:2.59.0

You can find a list of flex template base images here:
https://cloud.google.com/dataflow/docs/reference/flex-templates-base-images

and a list of beam sdk templates here:
https://hub.docker.com/r/apache/beam_python3.10_sdk/tags

To update these dependencies, from this directory, run something like
```
# To update apache beam version
docker pull apache/beam_python3.10_sdk:2.59.0
cid=$(docker create apache/beam_python3.10_sdk:2.59.0)
docker cp $cid:/opt/apache opt/apache
```

```
# To update flex templates base image
docker pull gcr.io/dataflow-templates-base/python310-template-launcher-base:flex_templates_base_image_release_20240918_RC00
cid=$(docker create gcr.io/dataflow-templates-base/python310-template-launcher-base:flex_templates_base_image_release_20240918_RC00)
docker cp $cid:/opt/google opt/google
```
