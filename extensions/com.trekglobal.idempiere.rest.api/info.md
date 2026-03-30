# iDempiere REST API

**Summary:** The iDempiere REST API extension provides comprehensive endpoints to interact with your iDempiere instance, allowing external systems to authenticate, access data, and execute processes via standard HTTP requests.

## 🚀 Features

* **Authentication & Security:** Supports secure login and JWT token-based authentication (`api/v1/auth`) valid for 1 hour.
* **Data & Models Access:** Full CRUD operations for Persistent Objects (POs) and attachments (`api/v1/models`).
* **UI Abstraction:** Direct interactions with Windows, Tabs, and Forms (`api/v1/windows`, `api/v1/forms`).
* **Process Execution:** Trigger processes and reports, and easily retrieve the generated files (`api/v1/processes`, `api/v1/files`).
* **Workflow Management:** Access workflow nodes to approve, reject, forward, or acknowledge records directly (`api/v1/workflow`).
* **System Operations:** Manage servers, schedulers, caches, and retrieve node logs via API (`api/v1/servers`, `api/v1/caches`, `api/v1/nodes`).

## ⚙️ Compatibility

* **iDempiere Version:** 12.0+
* **Java Version:** 11+

## 📦 Database Changes

* **System PackIn:** Standard REST dictionary elements and endpoint configurations are applied via standard OSGi bundle activation. No specific database extensions are required.

## 🛠 Usage & Configuration

* **Testing:** A Postman collection is provided in the repository (`postman/trekglobal-idempiere-rest.postman_collection.json`). You must run `POST api/v1/auth/tokens` and `PUT api/v1/auth/tokens` to acquire your session token before testing other API calls.
* **Documentation:** Detailed endpoint specifications and payload examples can be found at the [iDempiere REST Docs](https://bxservice.github.io/idempiere-rest-docs/).
* **OpenAPI(Swagger)** https://hengsin.github.io/idempiere-rest-swagger-ui

## 👤 Author / Support

* **Developer:** [BX Service GmbH](https://github.com/bxservice/)
* **Source Code:** [https://github.com/bxservice/idempiere-rest](https://github.com/bxservice/idempiere-rest)
* **Issue Tracker:** [https://github.com/bxservice/idempiere-rest/issues](https://github.com/bxservice/idempiere-rest/issues)
