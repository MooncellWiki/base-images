FROM debian:12-slim as exporter
RUN apt-get update \
    && apt-get install -y curl \
    && curl -O -L https://github.com/MooncellWiki/varnish_exporter/releases/download/1.7.0/varnish_exporter_Linux_x86_64.tar.gz \
    && mkdir /exporter \
    && tar -C /exporter -xzvf varnish_exporter_Linux_x86_64.tar.gz

FROM varnish:7.5.0
COPY --from=exporter /exporter/varnish_exporter /exporter/varnish_exporter 
WORKDIR /exporter

ENTRYPOINT [ "./varnish_exporter" ]