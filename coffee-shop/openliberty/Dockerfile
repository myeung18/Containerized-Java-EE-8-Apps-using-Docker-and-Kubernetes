FROM java:9-b149-jdk
LABEL maintainer="mail@sebastian-daschner.com"

# change version to current builds
ENV RELEASE 2018-03-09_2209
ENV VERSION 18.0.0.1
ENV BINARYFILE openliberty-${VERSION}.zip

RUN wget https://public.dhe.ibm.com/ibmdl/export/pub/software/openliberty/runtime/release/${RELEASE}/${BINARYFILE} \
    && unzip ${BINARYFILE} -d /opt \
    && rm ${BINARYFILE} 

ENV DEPLOYMENT_DIR /opt/wlp/usr/servers/defaultServer/dropins/
ENV CONFIG_DIR /opt/wlp/usr/servers/defaultServer/

COPY server.xml $CONFIG_DIR
COPY postgresql-9.4-1201-jdbc41.jar /opt/wlp/lib/

CMD ["/opt/wlp/bin/server", "run", "defaultServer"]
