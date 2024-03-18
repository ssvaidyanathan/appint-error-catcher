# appint-error-catcher

## Pre-req
- [integrationcli](https://github.com/GoogleCloudPlatform/application-integration-management-toolkit)
- A GCP Project with Application Integration and Integration Connectors already enabled
- Roles to create/publish Integrations and create connectors

## Steps
- create a Pub/Sub topic - `<prefix>-appintlab`
- update the topic_id in the [prefix-appintlab-pubsub-connector.json](./dev/connectors/prefix-appintlab-pubsub-connector.json) and the connection_name in the [overrides.json](./dev/overrides/overrides.json)
```
export PREFIX=<prefix>
sed -i "s/PREFIX/$PREFIX/g" ./dev/connectors/prefix-appintlab-pubsub-connector.json
sed -i "s/PREFIX/$PREFIX/g" ./dev/overrides/overrides.json
```
- rename prefix-appintlab-pubsub-connector.json to use your prefix

```
mv ./dev/connectors/prefix-appintlab-pubsub-connector.json ./dev/connectors/${PREFIX}-appintlab-pubsub-connector.json
```

- Create the Integration and Connectors using the integrationcli apply command

```
integrationcli 
```