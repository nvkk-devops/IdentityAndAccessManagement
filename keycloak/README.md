# Keycloak : Identify and Access Management

```
cd /Projects/IdentityAndAccessManagement/keycloak
docker-compose --env-file custom-keycloak.env up

BASE_IMAGE=quay.io/keycloak/keycloak:latest
docker run -it --rm $BASE_IMAGE /bin/bash
```
