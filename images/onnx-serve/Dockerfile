FROM ubuntu:18.04

RUN apt-get update -qq && apt-get install -y -q \
        build-essential \
        curl \
        libfreetype6-dev \
        libpng-dev \
        libzmq3-dev \
        pkg-config \
        rsync \
        software-properties-common \
        unzip \
        zlib1g-dev \
        python3.6-dev \
        python3.6-distutils \
        git \
    && apt-get clean -qq && rm -rf /var/lib/apt/lists/* && \
    curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py && \
    python3.6 get-pip.py && \
    pip install --upgrade pip && \
    rm -rf /root/.cache/pip*

ENV PYTHONPATH "${PYTHONPATH}:/src:/mnt/project"

COPY pkg/workloads/cortex/lib/requirements.txt /src/cortex/lib/requirements.txt
COPY pkg/workloads/cortex/serve/onnx.requirements.txt /src/cortex/serve/requirements.txt

ARG ONNXRUNTIME_VERSION="1.1.0"

RUN pip install --upgrade pip && \
    pip install --no-cache-dir -r /src/cortex/lib/requirements.txt && \
    pip install --no-cache-dir -r /src/cortex/serve/requirements.txt && \
    pip install onnxruntime==${ONNXRUNTIME_VERSION} && \
    rm -rf /root/.cache/pip*

COPY pkg/workloads/cortex/consts.py /src/cortex
COPY pkg/workloads/cortex/lib /src/cortex/lib
COPY pkg/workloads/cortex/serve /src/cortex/serve

ENTRYPOINT ["/src/cortex/serve/run.sh"]
