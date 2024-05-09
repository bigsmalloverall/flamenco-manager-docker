FROM ubuntu:latest

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    curl \
    git-all && \
    apt-get clean && rm -rf /var/lib/apt/lists/*    
   
# Flamenco Manager and Worker executables
RUN mkdir -p /flamenco/ && \
    curl https://flamenco.blender.org/downloads/flamenco-3.5-linux-amd64.tar.gz > /flamenco/flamenco-3.5-linux-amd64.tar.gz && \
    cd /flamenco/ && \
    tar xzf flamenco-3.5-linux-amd64.tar.gz && \
    mv flamenco-3.5-linux-amd64/* .

# Multilayer render support
RUN mkdir -p /flamenco/scripts/ && \
    mkdir -p /flamenco/tmp && \
    git clone https://github.com/dblanque/flamenco-compositor-script /flamenco/tmp && \
    mv /flamenco/tmp/startup_script.py /flamenco/ && \
    mv /flamenco/tmp/multi_pass_render.js /flamenco/scripts/ && \
    rm -rf /flamenco/tmp/

# COPY /config/flamenco-manager.yaml /flamenco/flamenco-manager.yaml
# COPY /config/flamenco-worker.yaml /flamenco/flamenco-worker.yaml

ENV DEBIAN_FRONTEND=dialog

WORKDIR /flamenco

# Ustaw polecenie, które zostanie uruchomione podczas startu kontenera
CMD ["/flamenco/flamenco-manager"]