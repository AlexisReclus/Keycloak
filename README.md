# Keycloak Docker image

This is a set of Docker images related to Keycloak. 

- [keycloak](https://registry.hub.docker.com/u/jboss/keycloak/) example Keycloak server
- [keycloak-mysql](https://registry.hub.docker.com/u/jboss/keycloak-mysql/) example connecting Keycloak to MySQL
- [keycloak-postgres](https://registry.hub.docker.com/u/jboss/keycloak-postgres/) example connecting Keycloak to PostgreSQL
- [keycloak-adapter-wildfly](https://registry.hub.docker.com/u/jboss/keycloak-adapter-wildfly/) builds on top of the [jboss/wildfly](https://registry.hub.docker.com/u/jboss/wildfly/) image, adding the Keycloak adapter for Wildfly to it, as well as the required changes to the standalone.xml
- [keycloak-examples](https://registry.hub.docker.com/u/jboss/keycloak-examples/) builds on top of [keycloak](https://registry.hub.docker.com/u/jboss/keycloak/), adding the examples.


To launch your app using the command line in the application folder:
1. ```cd docker-compose-examples```
2. launch docker
3. ```docker-compose -f keycloak-postgres.yml up```
4. Generate your certificate using the tutorial https://github.com/AlexisReclus/Keycloak/blob/master/Generate%20Certificate

5. Running the application on https://localhost:8443/auth/
