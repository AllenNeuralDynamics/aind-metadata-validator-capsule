# hash:sha256:4ec6f330adb9dfe549bc26a7033b64c638fd1b50413ff49254eb25527cc77645
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/py-julia-r:python3.10.12-R4.2.3-julia1.7.0-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive
ARG AWS_ACCESS_KEY_ID
ARG AWS_DEFAULT_REGION
ARG AWS_SECRET_ACCESS_KEY

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

ENV API_GATEWAY_HOST=api.allenneuraldynamics-test.org
ENV DATABASE=metadata_index
ENV COLLECTION=data_assets

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        postgresql=14+238 \
    && rm -rf /var/lib/apt/lists/*

RUN pip install -U --no-cache-dir \
    aind-metadata-validator==0.6.4
