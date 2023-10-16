Bootstrap: docker
From: mambaorg/micromamba:{{ MICROMAMBA_TAG }}

%arguments
	MICROMAMBA_TAG=jammy-cuda-12.1.1
	COWSAY_PYTHON_VERSION=3.9

%environment
	export MAMBA_DOCKERFILE_ACTIVATE=1

%post
	micromamba install -y -n base python={{ COWSAY_PYTHON_VERSION }} -c conda-forge pip && \
    micromamba run -n base pip install cowsay && \
    micromamba clean --all --yes

%runscript
	micromamba run -n base cowsay -t "${@:-Hello World!}"
