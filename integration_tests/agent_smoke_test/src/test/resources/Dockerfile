# ${project.version} is replaced by Maven when Dockerfile is copied to the target/ directory.
# ${base.image} is replaced programmatically in JavaVersionsIT.
FROM ${base.image}
RUN mkdir -p /app
COPY jmx_prometheus_javaagent-${project.version}.jar /app/
COPY jmx_example_application.jar /app/
COPY config.yml /app/
WORKDIR /app/
CMD java -javaagent:jmx_prometheus_javaagent-${project.version}.jar=9000:config.yml -jar jmx_example_application.jar