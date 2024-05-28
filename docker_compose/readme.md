# About

This [documentation](https://developer.hashicorp.com/packer/integrations/hashicorp/hashicups) describes Hashicups.

# HashiCups menu and orders
Get the available coffees: `curl -v localhost:19090/coffees | jq`

The following api call requires authorization.

First, sign-in with previously created account: `curl -X POST localhost:19090/signin -d '{"username":"education", "password":"test123"}'`

Then, export the returned JWT token to HASHICUPS_TOKEN: `export HASHICUPS_TOKEN=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MTY5NjgwMzUsInRva2VuX2lkIjo0NSwidXNlcl9pZCI6MSwidXNlcm5hbWUiOiJlZHVjYXRpb24ifQ.JMYflT8ICykd3C9zYXORgRL9j6tjBEMsQjPMCd-T8zI`

With that, you can perform authorized calls.

Get the ingredients for a coffee: `curl -X GET  -H "Authorization: ${HASHICUPS_TOKEN}" localhost:19090/coffees/1/ingredients | jq`

Get the created orders: `curl -X GET  -H "Authorization: ${HASHICUPS_TOKEN}" localhost:19090/orders | jq`