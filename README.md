# Integrity Check

## Description
This repo provides a GitHub action meant to be incorporated into build pipelines to check for the integrity of base images in Dockerfiles. It detects if there are signatures associated with base images, and fails if there is not.

The presence of a cryptographic signature indicates the authenticity of an image. Cosign signs images with ephemeral keys by authenticating with an OIDC protocol. This bakes authenticity into the signing process.

## How to Use
You can plug-and-play the GitHub action into your pipeline like so:

```
steps:
  - uses: cupofpython/integrity-check@v1
    with:
      dockerfile: Dockerfile # or path to Dockerfile
```