FROM maven:3.9-eclipse-temurin-25 AS build
WORKDIR /build
COPY pom.xml .
# The aggregator pom declares both modules, so Maven's reactor needs both
# module poms present to initialise — even though -pl builds only this one.
COPY product-service/pom.xml product-service/pom.xml
COPY supplier-service/pom.xml supplier-service/pom.xml
RUN mvn -B -q -pl product-service -am dependency:go-offline
COPY product-service/src product-service/src
RUN mvn -B -q -pl product-service -am clean package -DskipTests

FROM eclipse-temurin:25-jre-alpine
WORKDIR /app
RUN addgroup -S app && adduser -S app -G app
COPY --from=build /build/product-service/target/*.jar app.jar
USER app
EXPOSE 8081
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
