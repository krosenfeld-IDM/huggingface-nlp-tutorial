FROM ghcr.io/mamba-org/micromamba

USER root

# Install Git
RUN apt-get update && \
    apt-get install -y git curl python3-pip && \
    rm -rf /var/lib/apt/lists/*

USER mambauser

RUN micromamba create -n huggingface-env python=3.10 -c conda-forge -y
SHELL ["micromamba", "run", "-n", "huggingface-env", "/bin/bash", "-c"]

RUN pip install -y jupyter transformers[sentencepiece]

SHELL ["/bin/bash", "-c"]