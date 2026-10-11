# PAP Checker

### The independent checker for the Personal Agent Protocol's `poppy.json`.

A company's `/.well-known/poppy.json` sets what a personal agent can do with it: how the agent finds the company, how customers sign in, what the agent may view or change, and which APIs, website session and company agent it can use. PAP Checker reads that file from outside and checks it against the published draft.

---

### 🔎 **Tools**

| Tool | Description | Status |
| :--- | :--- | :--- |
| **[PAPChecker.com](https://papchecker.com)** | Check any domain's `poppy.json` against draft 0.1: discovery, sign-in, scopes, routes and extensions, each tied to its section of the draft. Free, read-only, no sign-up. | 🟢 **Live** |
| **[Sites publishing poppy.json](https://papchecker.com/sites)** | Every domain found with a Personal Agent Protocol discovery file, the day it was first seen, its sign-in types, routes and problems. Rechecked weekly. Demos are tagged. | 🟢 **Live** |
| **[What is poppy.json?](https://papchecker.com/what-is-poppy-json)** | A field-by-field guide to the discovery document, following section 3 of the specification. | 🟢 **Live** |

### 📐 **What we check**

* **Discovery:** `protocol_version` in `major.minor` form, and `organization` with a name and a `domain` that matches the host asked for.
* **Sign-in:** an `auth` block whenever an agent, APIs or a website session is listed; the issuer's OAuth metadata matches the file and lists the domain in `poppy_domains`; mediated sign-in has its endpoint and credential fields.
* **Scopes:** custom scopes don't reuse reserved names, and each one is described.
* **Routes:** at least one way in for a personal agent: a company agent, APIs, or the website, each at an HTTPS URL.
* **Extensions:** each one has a version, the operations extension has its endpoint, and custom extensions carry a domain prefix.

We read only public documents. We never sign in, start a session or send anything to a company's endpoints.

---

### **About**
PAP Checker is an independent project. It is not affiliated with or endorsed by the Personal Agent Protocol's authors; "Personal Agent Protocol" and "Poppy" are their names. Rules follow [draft 0.1](https://personalagentprotocol.org/docs/spec) (published 9 Oct 2026).

_Maintained by the PAP Checker team._
