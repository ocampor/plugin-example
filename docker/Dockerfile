FROM gradle:6.7.1-jdk15 AS assemble

ADD build.gradle build.gradle
ADD src src
ADD NOTICE.txt NOTICE.txt

RUN gradle assemble

FROM docker.elastic.co/elasticsearch/elasticsearch:7.10.0 AS cache

ENV PLUGIN_PACKAGE_NAME=example-rescore.zip

COPY --from=assemble /home/gradle/build/distributions/${PLUGIN_PACKAGE_NAME} /tmp/${PLUGIN_PACKAGE_NAME}
RUN ./bin/elasticsearch-plugin install file:/tmp/${PLUGIN_PACKAGE_NAME}
