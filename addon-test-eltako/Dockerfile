ARG BUILD_FROM
FROM $BUILD_FROM

ARG BUILD_VERSION

# Create Working Directory
WORKDIR /app

# Install enoceanmqtt and requirements
RUN apk add --no-cache python3 py3-pip git && \
    python3 -m venv /app/venv && \
    . /app/venv/bin/activate && \
    python3 -m pip install --upgrade pip && \
    pip3 install pyyaml && \
    pip3 install tinydb && \
    pip3 install git+https://github.com/mak-gitdev/enocean.git && \
    git clone https://github.com/embyt/enocean-mqtt.git && \
    cd enocean-mqtt && python3 setup.py develop && cd .. && \
    echo "Installing support-eltako branch" && \
    git clone -b support-eltako --single-branch --depth 1 https://github.com/mak-gitdev/HA_enoceanmqtt.git && \
    cp -rf HA_enoceanmqtt/enoceanmqtt enocean-mqtt && \
    rm -rf HA_enoceanmqtt

# Copy data for add-on
COPY run.sh .
RUN chmod a+x run.sh

CMD [ "/app/run.sh" ]
