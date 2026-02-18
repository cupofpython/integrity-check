# Release Notes

# v1.0.0
Iterate through all base images in a Dockerfile (to account for multi-stage), verify signature with Cosign, pass job if base image has signature, fail if any base has no signature.