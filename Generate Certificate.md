Identify the running container, and connect to it, `keycloak-postgres_keycloak_1` is probably the default name

```
docker ps
docker exec -it keycloak-postgres_keycloak_1 /bin/bash
```

generate the self signed cert as per https://www.keycloak.org/docs/4.3/server_installation/index.html#enabling-ssl-https-for-the-keycloak-server
````
keytool -genkey -alias localhost -keyalg RSA -keystore keycloak.jks -validity 10950
````


Use `secret` for the password, and other answers as below
````
Use `secret` for the password, and other answers as below
What is your first and last name?
  [Unknown]:  localhost
What is the name of your organizational unit?
  [Unknown]:  keycloak
What is the name of your organization?
  [Unknown]:
What is the name of your City or Locality?
  [Unknown]:
What is the name of your State or Province?
  [Unknown]:
What is the two-letter country code for this unit?
  [Unknown]:
Is CN=localhost, OU=keycloak, O=Unknown, L=Unknown, ST=Unknown, C=Unknown correct?
  [no]:  yes
  ````

now move that file into place
````
mv keycloak.jks /opt/jboss/keycloak/standalone/configuration/
````
now move that file into place

Restart keycloak
````
cd /opt/jboss/keycloak/bin/
./jboss-cli.sh --connect command=:reload
````

Config will be saved if container is restarted

Running in https://localhost:8443/auth
