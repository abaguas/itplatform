FROM ghcr.io/backstage/backstage:1.14.0
USER root
RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt,sharing=locked \
    apt-get update && \
    apt-get install -y --no-install-recommends python3-pip
RUN pip install mkdocs-techdocs-core
USER node
