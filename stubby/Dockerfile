FROM debian:latest

RUN apt-get update && apt-get install -y stubby

COPY stubby.yml /etc/stubby/stubby.yml

CMD ["stubby", "-l"]