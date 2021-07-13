# Webhooks

### Structure

```json
{
	"webhook": "{service}",
	"action": "{resource}.{subresource?}.{event}",
	"signature": "{signedSHA-256(action + payload + token)}",
	"idempotent": "{hash(action + payload)}"
	"ts": 1626167843704,
	"payload": [] || {}
}
```


### Definitions:

- **service**: The name of the service sending this webhook, eg. Members
- **resource**: The resource name this webhook is triggered on, eg. Person
- **subsresource**: (optional) a child relationship of the main resource eg. Church
- **event**: The event that took place for this webhook to be triggered, eg. Updated
- **signature**: The `action` and `payload` signed by a shared token between the `service` and the `receiver`
- **idempotent**: A simple md5 hash of the `action` and `payload` to use as an idempotent key
- **ts**: The timestamp this event was triggered
- **payload**: The actual data of the resource either in full or in partial depending on the `event`


### Example

```json
{
  "webhook": "Members",
  "action": "User.Church.Updated",
  "signature": "4684284F6637F831C24FF6FDF6022BB61612BAF59ABADBD4A1C00FE72094EA9E",
  "idempotent": "1A099C93A0E29129899A01C61B05C8DB",
  "ts": 1626167843704,
  "payload": {
    "id": 1231,
    "fullname": "John Doe",
    "churchId": 32,
    "church": {
      "id": 32,
      "name": "Oslo"
    }
  }
}
```
