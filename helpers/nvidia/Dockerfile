FROM nvidia/cuda:7.0-cudnn4-devel
#FROM nvidia/cuda:cudnn-devel
MAINTAINER Yuri Laskin <y.laskin@agentvi.com>

ENV PATH /usr/local/bin:$PATH
ENV LANG C.UTF-8

RUN apt-get update && apt-get install -y --no-install-recommends --force-yes \
		wget \
		git \
		ca-certificates \
		python2.7 \
		python-pip \
	&& rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/pasifus/nvidia_exporter

WORKDIR /nvidia_exporter

RUN pip install -r requirements.txt

CMD ["python", "-m", "nvidia_exporter.main"]
