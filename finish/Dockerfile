FROM open-liberty as server-setup
COPY /target/LibertyProject.zip /config/
RUN unzip /config/LibertyProject.zip && \
    mv /wlp/usr/servers/sampleAppServer/* /config/ && \
    rm -rf /config/wlp && \
    rm -rf /config/LibertyProject.zip

FROM open-liberty
LABEL maintainer="Graham Charters" vendor="IBM" github="https://github.com/WASdev/ci.maven"
COPY --from=server-setup /config/ /config/
EXPOSE 9080 9443