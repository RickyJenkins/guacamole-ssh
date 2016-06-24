FROM mattgruter/guacamole-guacd

RUN apt-get update && \
    apt-get install -y libpango1.0-dev && \
    apt-get install -y libssh2-1-dev

RUN cd /guacamole-server-${GUACAMOLE_VERSION} && \
    ./configure && \
    make install && \
    ldconfig

ENV GUACAMOLE_HOME /guacd
WORKDIR /guacd
EXPOSE 4822

CMD ["guacd", "-f", "-b", "0.0.0.0", "-l", "4822"]
