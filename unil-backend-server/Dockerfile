FROM eclipse-temurin:21-alpine

LABEL maintainer="Yann Bailly, yann.bailly@unil.ch, UNIL"

COPY ebsi-api-proxy.jar /opt/app.jar

RUN addgroup --gid 1000 --system javauser && \
    adduser --uid 1000 --system javauser --ingroup javauser && \
    chown javauser:javauser /opt/app.jar && \
    chmod 644 /opt/app.jar

USER 1000

WORKDIR /opt

ENTRYPOINT ["java", "-Dfile.encoding=UTF-8", "-Duser.timezone=Europe/Zurich", "-XX:MaxRAMPercentage=80", "-XX:ActiveProcessorCount=8", "-XshowSettings:vm", "-jar", "/opt/app.jar"]