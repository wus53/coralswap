FROM ghcr.io/fuellabs/fuel-core:v0.10.1

ARG IP=0.0.0.0
ARG PORT=4000
ARG DB_PATH=./mnt/db/

ENV IP="${IP}"
ENV PORT="${PORT}"
ENV DB_PATH="${DB_PATH}"

# Install curl to use on
# healthcheck config
RUN apt update
RUN apt install curl -y

WORKDIR /root/

COPY chainConfig.json .

CMD ./fuel-core \
    --ip ${IP} \
    --port ${PORT} \
    --db-path ${DB_PATH} \
    --utxo-validation \
    --min-gas-price ${MIN_GAS_PRICE} \
    --chain ./chainConfig.json

EXPOSE ${PORT}
