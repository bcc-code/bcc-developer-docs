---
description: >-
  There would be a full day workshop where we make a strategy for Open APIs and
  specifically the authentication architecture.
---

# BCC Open Api's Workshop

## Approach

The idea would be that each team leader comes with some user scenarios for their application, as well as potentially how they would like to use data from other applications \(especially Members\)

In addition we would look at some reference architectures \(e.g. Microsoft Graph, Shopify API, Facebook API, Google API, Oslofjord\) as a guide.

## Goal

1. How to authenticate end-users \(e.g. OpenID connect\)
2. How to authenticate service-to-service \(e.g. OAuth\)
3. How to propogate user context between services \(e.g. end-user token, or system token + user parameter\)
4. Network security for internal and external services
5. API Gateway for BCC vs. API Gateway per application vs. completely independent microservices
6. How to manage system integration permissions \(as opposed to user specific permissions\)
7. How to support micro-frontend \(widget\) scenarios
8. How to provision clients \(self service?\)
9. Client libraries - which languages? swagger
10. Protocols / styles? REST, OData, Graphql, GRPC
11. How to support event based communication \(internally, externally\) - webhooks, message brokers, event streams etc.?

### BCC Membership Api Use Cases

1. BUK want's access to BCC's members api to synchronize personal data of the BCC members that gave consent for BUK to handle their data. The fields BUK needs access to are. firstName, lastName, email and address.
2. -

### Brunstad TV Api Use Cases

1. -
2. -

### MyShare Api Use Cases

1. -
2. -

### BMM Api Use Cases

1. -
2. -

