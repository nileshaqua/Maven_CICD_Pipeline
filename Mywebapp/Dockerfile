FROM maven AS build
WORKDIR /app
COPY . .
RUN mvn package

FROM tomcat AS run
COPY --from=build /app/target/Mywebapp.war /usr/local/tomcat/webapp
EXPOSE 8080
CMD ["catalina.sh", "run"]


