---
title: API
---
This document will cover the following aspects of the MyHome API:

1. Overview of the API and its offerings
2. Details on where to find the list of endpoints
3. Usage of the API via Swagger and Postman

<SwmSnippet path="/api/src/main/resources/public/swagger/api.yaml" line="1">

---

# Overview of the MyHome API

The MyHome API is defined in the OpenAPI specification. It provides various services related to managing an apartment, including authentication, user management, document management, community management, amenities management, house management, payment management, and member management.

```yaml
openapi: 3.0.2
servers:
  - url: http://localhost:8080/
info:
  description: This is a OpenApi specification for MyHome backend service.
  version: 2.0.0
  title: Swagger MyHome - OpenAPI 3.0
  _exporter_id: 9986502
tags:
  - name: Authentication
  - name: Users
  - name: Documents
  - name: Communities
  - name: Amenities
  - name: Houses
  - name: Payments
  - name: Members
```

---

</SwmSnippet>

<SwmSnippet path="/api/src/main/resources/public/swagger/api.yaml" line="19">

---

# List of Endpoints

The list of endpoints for the MyHome API is defined in the OpenAPI specification. Each endpoint is associated with a specific service and has its own path, HTTP method, parameters, and response definitions.

```
  /auth/login:
    post:
      tags:
        - Authentication
      description: Login user to system
      operationId: login
      requestBody:
        required: true
```

---

</SwmSnippet>

<SwmSnippet path="/api/src/main/resources/public/swagger/api.yaml" line="1">

---

# Swagger

The MyHome API is available via Swagger. The specification for the API is defined in the `api.yaml` file. This file includes the details of all the endpoints, their request parameters, and response formats.

```
openapi: 3.0.2
servers:
  - url: http://localhost:8080/
info:
  description: This is a OpenApi specification for MyHome backend service.
  version: 2.0.0
  title: Swagger MyHome - OpenAPI 3.0
  _exporter_id: 9986502
tags:
  - name: Authentication
  - name: Users
  - name: Documents
  - name: Communities
  - name: Amenities
  - name: Houses
  - name: Payments
  - name: Members
```

---

</SwmSnippet>

<SwmSnippet path="postman/MyHome.postman_collection.json" line="2">

---

# Postman

The MyHome API is also available via Postman. The `MyHome.postman_collection.json` file includes the collection of API requests that can be imported into Postman. It also includes the details of how to use the API, the variables used, and the request details for each API endpoint.

```
	"info": {
		"_postman_id": "3c85fc87-412a-4093-b9da-41a3f439e7d0",
		"name": "MyHome",
		"description": "# MyHome API Guide\n\n## Usage\n\nTo use any API except **Create User and Login User**, you'll need to obtain Authentication Token.\n\nTo get Authentication Token.\n\n1. First Create New User with **Create User API**.\n2. Login with New user with **New User API**. Login will obtain New Token for user.\n    \n\nNow you can use other APIs.\n\n## Variables\n\nAll APIs are configured with Postman variables to keep consistensy for static and dynamic values.\n\n1. **ENV_URL**: This variable hold value for Enviroment URL. e.g. 127.0.0.1:8080 (Default to local environment, with 8080 port), or example.com.\n2. **AUTH_TOKEN**: This variable hold authentication token obtained by Login User API, which is used in request header. This is stored each time you use Login User API.\n3. **COMMUNITY_ID**: This variable hold default community id created for testing Community related APIs.\n4. **HOUSE_ID**: This variable hold default house id created for testing House related APIs.\n5. **USER_ID**: This variable hold userId obtained by Login User API. This is stored each tiem you use Login User API.\n6. **ADMIN_ID**: This variable hold default admin id created for testing related APIs.\n7. **MEMBER_ID**: This variable hold default member id created for testing related APIs.\n8. **DEFAULT_EMAIL**: This variable hold default value for user login email.\n9. **DEFAULT_PASSWORD**: This variable hold default value for user login password.\n    \n\nYou can configure your own values for these either by editing in _MyHome > ... (View more actions) > Edit > Variables Tab_ or you can create your environment and add variable there. \\[How to create Environment in Postman\\] ([https://learning.postman.com/docs/postman/variables-and-environments/managing-environments/#creating-environments](https://learning.postman.com/docs/postman/variables-and-environments/managing-environments/#creating-environments))",
		"schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
	},
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm AI 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
