FROM java:8-jre-alpine

RUN apk add --no-cache curl && \
	curl -Lo tabula.jar https://github.com/tabulapdf/tabula-java/releases/download/v1.0.1/tabula-1.0.1-jar-with-dependencies.jar

ENTRYPOINT ["java","-jar", "./tabula.jar"]