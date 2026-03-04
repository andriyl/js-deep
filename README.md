# JS-Deep

**JS-Deep** — a deep guide to JavaScript as an embedded execution layer in various hosts (Node.js, browsers, Electron, databases).  
This resource is aimed at students, developers, and enthusiasts who want to go beyond basic tutorials and understand **JS engines, host interaction, API bindings, and execution context**.

---

## Overview

JavaScript always runs inside a **host** (browser, Node.js, Electron, database).
 **Layers :**
- **JS** – user scripts, functions, variables, libraries
- **Engine** – parsing, JIT compilation, garbage collection (V8, QuickJS, SpiderMonkey)
- **Host** – context, API bindings, sandbox, access to filesystem, network, DOM

---

## Components

| Component | Description | Responsibilities | Does Not Do |
|-----------|-------------|-----------------|-------------|
| JavaScript (JS) | Code, ECMAScript | Logic, computations, calls host API | Access OS, FS, network |
| JS Engine | V8, SpiderMonkey, QuickJS | Parsing, JIT, execution, GC | Provides host API |
| Host | Browser, Node.js, Electron, Database | Context, API, sandbox, control execution | Executes JS by itself |

---

```mermaid
flowchart TB
    subgraph Layer_JS [JS Layer]
        direction TB
        JS["JavaScript (user code, functions, libraries)"]
    end

    subgraph Layer_Engine [Engine Layer]
        direction TB
        JS_Engine["JS Engine (V8 / QuickJS / SpiderMonkey)"]
    end

    subgraph Layer_Host [Host Layer]
        direction TB
        API["API Bindings / Native Bridge"]
        Sandbox["Sandbox / Security Layer"]
        HostApp["Host Application\n(FS, HTTP, DOM, OS)"]
    end

    JS --> JS_Engine
    JS_Engine --> API
    API --> Sandbox
    Sandbox --> HostApp
