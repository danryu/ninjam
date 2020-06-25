FROM ubuntu:latest

ENV PATH /usr/local/ninjam:$PATH
ARG TAG
ADD https://github.com/danryu/ninjam/releases/download/${TAG}/ninjam.tar.gz /var/tmp/

RUN mkdir -p /var/tmp/ninjam && tar -xzf /var/tmp/ninjam.tar.gz -C /var/tmp/ninjam && rm /var/tmp/ninjam.tar.gz && mv /var/tmp/ninjam /usr/local/
WORKDIR /usr/local/ninjam

# forward  error logs to docker log collector
RUN ln -sf /proc/1/fd/1 ./ninjamserver.log

EXPOSE 2049
ENTRYPOINT ["ninjamsrv", "server.cfg"]
