FROM openjdk:11-jre-slim
WORKDIR /app
# Copia el JAR que bajaste en tmp/issuetracking.jar
COPY issuetracking.jar ./issuetracking.jar
# Exponer puerto de la aplicación
EXPOSE 9096
# Healthcheck (opcional, comprueba el endpoint de salud)
# Necesita esta dependencia de springboot: spring-boot-starter-actuator
HEALTHCHECK --interval=30s --timeout=5s --start-period=30s \
  CMD curl -f http://localhost:9096/actuator/health || exit 1
# Arrancar Spring Boot
ENTRYPOINT ["java", "-jar", "issuetracking.jar"]
