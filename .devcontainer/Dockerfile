FROM mcr.microsoft.com/devcontainers/base:bullseye

# USER root

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        tree zip \
    && apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ARG CONDA_ROOT="/opt/conda"
ARG CONDA_BIN="${CONDA_ROOT}/bin"
COPY --from=jupyter/minimal-notebook:x86_64-2023-03-06 /opt/conda ${CONDA_ROOT}
ENV PATH="${PATH}:${CONDA_BIN}"

ARG GH_VERSION=2.30.0
RUN wget https://github.com/cli/cli/releases/download/v${GH_VERSION}/gh_${GH_VERSION}_linux_amd64.tar.gz -O - \
    | tar xvzf - -C${CONDA_BIN} gh_${GH_VERSION}_linux_amd64/bin/gh --strip-components=2

RUN pip install copier==8.3.0
