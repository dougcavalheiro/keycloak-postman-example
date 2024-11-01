# Auth-Keycloak

This repo covers the most common api rest calls to manage users through keycloak. 

## Prerequisites

- [Docker](https://docs.docker.com/engine/install/)
- [Postman](https://www.postman.com/downloads/)

## Keycloak Config

1. Run `docker compose -f docker-compose.yaml up`.
2. Access Keycloak admin dashboard on `http://localhost:8080` by entering the credentials `admin`/`admin`.
3. Create a new Realm with `realm-example` as Realm name, enabled `on`.
4. Under the above Realm selected, create a new Client as `realm-example-client` as OpenID Connect, fill other fields optionally. Check `Client authentication` in the client capability config.

Allowing admin rest api:

1. Go to `master` realm
2. Under `clients`, Select `admin-cli`
2.1. Check both `Client authentication` and `Service accounts roles`
3. Assign the roles `create-realm` and `admin` to the admin-cli client in the `Service account roles` tab


## Postman Collection Config

1. Import the `keycloack.postman_collection.json` collection to your postman application
2. Select the collection and open the `variables` tab
3. In the keycloak system, select `admin-cli` client config, grab the Client Secret value and paste to the `admin_cli_client_secret` initial and current values in the `variables` tab
4. Do the same for the `client_secret` values with `realm-example-client` credentials.

## Read More

- [Keycloak Rest API Docs](https://www.keycloak.org/docs-api/latest/rest-api/index.html)
- [Managing Variables in Postman](https://learning.postman.com/docs/sending-requests/variables/variables/)
- [Keycloak main page](https://www.keycloak.org/)
- [Docker (compose)](https://docs.docker.com/compose/)