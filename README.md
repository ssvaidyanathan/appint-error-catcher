# appint-error-catcher

- create a Pub/Sub topic - `<prefix>-appintlab`
- update the topic_id in the [prefix-appintlab-pubsub-connector.json](./dev/connectors/prefix-appintlab-pubsub-connector.json)
- update the connection_name in the [overrides.json](./dev/overrides/overrides.json)
- execute `integrationcli integrations apply -f . -e dev`