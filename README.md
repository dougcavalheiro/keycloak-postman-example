# Auth-Keycloak

## Keycloak Config

1. Run `docker compose -f docker-compose.yaml up`.
2. Enter the credentials `admin`/`admin`.
3. Create a new Realm with `realm-example` as Realm name, enabled `on`.
4. Under the above Realm selected, create a new Client as `realm-example-client` as OpenID Connect, fill other fields optionally. Check `Client authentication` in the client capability config.

Allowing admin rest api:

1. Go to `master` realm
2. Under `clients`, Select `admin-cli`
2.1. Check both `Client authentication` and `Service accounts roles`
3. Assign the roles `create-realm` and `admin` to the admin-cli client in the `Service account roles` tab


## Postman Collection Config

1. Import the `keycloack.postman_collection.json` collection to your postman application
2. Select the collection and open the `Variables` tab
3. In the keycloak `admin-cli` client config, grab the Client Secret value and paste to the `admin_cli_client_secret` initial and current values
4. Do the same for the `client_secret` values with `realm-example-client` credentials.