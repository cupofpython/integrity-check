# Integrity Check

## Description
This repo provides a GitHub action meant to be incorporated into build pipelines to check for the integrity of base images in Dockerfiles. It detects if there are signatures from trusted signers associated with base images, and fails if there is not. Trusted signers are specified in the `image-policy.json` file.

The presence of a cryptographic signature from a trusted signer indicates the authenticity of an image. Cosign signs images with ephemeral keys by authenticating with an OIDC protocol. This bakes authenticity into the signing process.

## How to Use
You can plug-and-play the GitHub action into your pipeline like so:

```
- uses: cupofpython/integrity-check@v1
        with:
          dockerfile: Dockerfile # or path to your Dockerfile
          policy-file: image-policy.json # or path to your policy file
```