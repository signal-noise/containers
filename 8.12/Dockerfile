FROM node:8.12-alpine

ENV CLOUD_SDK_VERSION 220.0.0

# Packages for Signal Noise workflows
RUN apk add --no-cache vim tar gzip jq curl

# Packages for CircleCi compatibility
RUN apk add --no-cache bash git openssh ca-certificates

# Packages as install helpers for the SDKs
RUN apk add --no-cache python py-crcmod py-pip libc6-compat openssh-client

# Add GCloud SDK
ENV PATH /google-cloud-sdk/bin:$PATH
RUN curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-sdk-${CLOUD_SDK_VERSION}-linux-x86_64.tar.gz && \
  tar xzf google-cloud-sdk-${CLOUD_SDK_VERSION}-linux-x86_64.tar.gz && \
  rm google-cloud-sdk-${CLOUD_SDK_VERSION}-linux-x86_64.tar.gz && \
  ln -s /lib /lib64 && \
  gcloud config set core/disable_usage_reporting true && \
  gcloud config set component_manager/disable_update_check true && \
  gcloud config set metrics/environment github_docker_image

# Add AWS CLI
RUN pip --no-cache-dir install awscli && \
  rm -rf /var/cache/apk/*

VOLUME ["/root/.config"]
