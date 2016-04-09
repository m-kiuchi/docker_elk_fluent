FROM kiyoto/fluentd:0.10.56-2.1.1
MAINTAINER kiyoto@treausure-data.com
RUN mkdir /etc/fluent
ADD fluent.conf /etc/fluent/
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "--yes", "make", "libcurl4-gnutls-dev"]
RUN ["/usr/local/bin/gem", "install", "fluent-plugin-elasticsearch", "--no-rdoc", "--no-ri"]
RUN ["/usr/local/bin/gem", "install", "fluent-plugin-record-reformer", "--no-rdoc", "--no-ri"]
RUN ["/usr/local/bin/gem", "install", "fluent-plugin-docker-tag-resolver", "--no-rdoc", "--no-ri"]
ENTRYPOINT ["/usr/local/bin/fluentd", "-c", "/etc/fluent/fluent.conf"]

