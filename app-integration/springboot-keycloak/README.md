# Springboot Keycloak integration

* Get Access Token
* 

## Pre-requisite
Keycloak is up and serving from 'http://localhost:8080/auth'.
Change auth URL accordingly.

## Step1: Get the access token
```
token_endpoint=http://localhost:8080/auth/realms/vkrealm/protocol/openid-connect/token

## Get_Access_token
input_data="grant_type=password&username=venkata&password=xxxxx&client_id=springboot-keycloak"
curl -X POST -H "Content-Type: application/x-www-form-urlencoded" -d ${input_data}  ${token_endpoint}

## Refresh_token
input_data="client_id=myClientID&client_secret=myClientPassword&grant_type=refresh_token&refresh_token=xxxx-xxxx-xxx-xx"

```

## Step2: Invoke APIs bounded by AUTHENTICATED ROLE
```
APPLICATION_API_URL=http://localhost:9100/employees
ACCESS_TOKEN=<previous-request-output>
curl -H "Bearer ${ACCESS_TOKEN}" -X POST ${APPLICATION_API_URL}
```