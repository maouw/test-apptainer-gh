Bootstrap: docker
From: debian:stable-slim

%post
	export DEBIAN_FRONTEND=noninteractive
	set -eE
	# Install cowsay
	apt-get update --yes --quiet && \
	apt-get install --yes --quiet cowsay && \
	apt-get clean --yes --quiet && \
	rm -rf /var/lib/apt/lists/*

%environment
	export PATH=/usr/games:$PATH
	export LC_ALL=C.UTF-8
	export LANGUAGE=C.UTF-8
	export LANG=C.UTF-8

%runscript
	# Run fortune with the arguments passed to the container
	cowsay "${@:-}"

%test
	set -eE
	/.singularity.d/runscript "Cowsay runs!"
