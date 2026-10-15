# PAP Checker

### Independent tools for the Personal Agent Protocol: check a company's `poppy.json`, run a personal agent against it, and test against companies built for it.

A company's `/.well-known/poppy.json` sets what a personal agent can do with it: how the agent finds the company, how customers sign in, what the agent may view or change, and which APIs, website session and company agent it can use. These tools cover both sides of that: the company's published setup, and what an agent actually does with it.

---

### 🔎 **Check**

| Tool | Description | Status |
| :--- | :--- | :--- |
| **[PAPChecker.com](https://papchecker.com)** | Check any domain's `poppy.json` against draft 0.1: discovery, sign-in, scopes, routes and extensions, each tied to its section of the draft. Free, read-only, no sign-up. | 🟢 **Live** |
| **[poppy.json validator](https://papchecker.com/poppy-json-validator)** | Paste a `poppy.json` and get the same checks before it goes live. | 🟢 **Live** |
| **[Sites publishing poppy.json](https://papchecker.com/sites)** | Every domain found with a Personal Agent Protocol discovery file, the day it was first seen, its sign-in types, routes and problems. Rechecked weekly. Demos are tagged. | 🟢 **Live** |

### 🧪 **Test**

| Tool | Description | Status |
| :--- | :--- | :--- |
| **[PAP Playground](https://papplayground.com)** | A personal agent you can give a task. It finds the company, starts a session, signs in on the company's own page (direct, device or mediated), works through its OpenAPI or MCP API, its website or its own agent, and asks you to approve exact terms before anything changes. Every request and response is recorded. The Inspector lets you send each call yourself. | 🟢 **Live** |
| **[PAP Sandbox](https://papsandbox.com)** | Three test companies that speak the protocol: a noodle bar, a flower shop and a holiday let. Each has discovery, all three sign-in types, an OpenAPI API and an MCP server, website sessions, its own company agent and the operations extension. A test customer with one open order; nothing is charged or shipped. Open to any agent. | 🟢 **Live** |

### 📖 **Learn**

| Read | What it covers |
| :--- | :--- |
| **[What is poppy.json?](https://papchecker.com/what-is-poppy-json)** | A field-by-field guide to the discovery document, following section 3 of the specification. |
| **[How the Personal Agent Protocol works](https://papchecker.com/blog/how-personal-agent-protocol-works)** | A real agent, step by step: finding a company, signing in, approving exact terms, and talking to the company's own agent. |
| **[Blog](https://papchecker.com/blog)** | Walkthroughs, changes to the draft, and what early adopters publish. |

### 📐 **What the checker checks**

* **Discovery:** `protocol_version` in `major.minor` form, and `organization` with a name and a `domain` that matches the host asked for.
* **Sign-in:** an `auth` block whenever an agent, APIs or a website session is listed; the issuer's OAuth metadata matches the file and lists the domain in `poppy_domains`; mediated sign-in has its endpoint and credential fields.
* **Scopes:** custom scopes don't reuse reserved names, and each one is described.
* **Routes:** at least one way in for a personal agent: a company agent, APIs, or the website, each at an HTTPS URL.
* **Extensions:** each one has a version, the operations extension has its endpoint, and custom extensions carry a domain prefix.

The checker reads only public documents: it never signs in, starts a session or sends anything to a company's endpoints. PAP Playground makes changes only at PAP Sandbox's test companies; anywhere else it only reads.

---

### **About**
PAP Checker, PAP Playground and PAP Sandbox are independent projects. They are not affiliated with or endorsed by the Personal Agent Protocol's authors; "Personal Agent Protocol" and "Poppy" are their names. Rules follow [draft 0.1](https://personalagentprotocol.org/docs/spec) (published 9 Oct 2026).
