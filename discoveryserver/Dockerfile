FROM openjdk:17-alpine

COPY target/*.jar app.jar

ENTRYPOINT ["java", "-Dspring.profiles.active=production", "-jar", "/app.jar"]