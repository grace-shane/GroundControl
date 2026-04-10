# GroundControl

**GroundControl** is the localized "Command Center" for Grace Engineering’s tooling ecosystem. It provides a unified interface to browse, manage, and deploy tool assemblies, effectively serving as an on-premise alternative to MachiningCloud.

## 🛰 The Ecosystem
GroundControl doesn't work alone. It orchestrates data between two primary services:
* **[Datum](https://github.com/grace-shane/Datum):** The "Source of Truth" for tool geometry and library state.
* **[FAASST](https://github.com/grace-shane/FAASST):** The "Calculated Truth" providing optimized feeds, speeds, and physics-based cutting parameters.

## 🛠 Core Functions
* **Local Tool Assembly:** Build complex tool assemblies (Holder + Extension + Cutter) without relying on external cloud uptime.
* **Unified API:** Serves as the single endpoint for shop-floor tablets and CAM workstations to pull both geometry and cutting data.
* **Digital Twin Export:** Generates localized tool data packages for Fusion 360, Mastercam, or specialized Swiss turn environments.

## 🏗 Getting Started
1.  **Dependency Check:** Ensure your local instances of **Datum** and **FAASST** are reachable on the internal network.
2.  **Environment Setup:**
    ```bash
    cp .env.example .env
    # Define your DATUM_API_URL and FAASST_API_URL
    ```
3.  **Run Development:**
    ```bash
    npm run dev
    ```

## 🔒 Internal Security
GroundControl is designed to run within the Grace Engineering firewall. It caches manufacturer data locally to ensure that shop production is never halted by external internet outages or third-party service changes.

---

### Next Steps for the GroundControl Repo:
* **Architecture Diagram:** Since you’re sharing data across three repos, adding a `mermaids.js` flowchart in the README would be a great way to visualize how the data flows from **FAASST** and **Datum** into **GroundControl**.
* **Shared Types:** Are you planning to use a shared Git submodule for the tool/material types, or will you just handle that through API schema validation?
