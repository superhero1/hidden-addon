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
    pip3 install pyyaml==6.0.1 && \
    pip3 install tinydb==4.7.1 && \
    pip3 install paho-mqtt==1.6.1 && \
    pip3 install setuptools && \
    pip3 install git+https://github.com/superhero1/enocean.git && \
    git clone -b master --single-branch --depth 1 https://github.com/embyt/enocean-mqtt.git && \
    cd enocean-mqtt && python3 setup.py develop && cd .. && \
    echo "Installing support-eltako branch" && \
    git clone -b support-eltako --single-branch --depth 1 https://github.com/superhero1/HA_enoceanmqtt.git && \
    cp -rf HA_enoceanmqtt/enoceanmqtt enocean-mqtt && \
    rm -rf HA_enoceanmqtt

# Copy data for add-on
COPY run.sh .
RUN chmod a+x run.sh

CMD [ "/app/run.sh" ]
