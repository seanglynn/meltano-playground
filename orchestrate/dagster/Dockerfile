# Param with default
ARG BASE_IMAGE=meltano/meltano:latest
FROM ${BASE_IMAGE}

# Param with default
ARG DAGSTER_VERSION=0.14.20

# ==> Add Dagster layer
RUN \
    pip install \
        dagster==${DAGSTER_VERSION} \
        dagster-postgres==${DAGSTER_VERSION} \
        dagster-celery[flower,redis,kubernetes]==${DAGSTER_VERSION} \
        dagster-aws==${DAGSTER_VERSION} \
        dagster-k8s==${DAGSTER_VERSION} \
        dagster-celery-k8s==${DAGSTER_VERSION} \
# Cleanup
    &&  rm -rf /var \
    &&  rm -rf /root/.cache  \
    &&  rm -rf /usr/lib/python2.7 \
    &&  rm -rf /usr/lib/x86_64-linux-gnu/guile

# ==> Add user code layer
# Example pipelines
COPY build_cache/ /
