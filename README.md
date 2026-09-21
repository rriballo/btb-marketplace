# NORDVELL CX Coworker Marketplace

Standalone marketplace for NORDVELL brand governance and Adobe Journey Optimizer email and offer content authoring.

The plugin turns a short request such as "build NORDVELL content for the Aurora M/L view-without-add audience" into an evidence-backed content package, a polished responsive email, targeted and fallback offer fragments, and an approval-gated AJO build plan. It does not invent campaign facts or silently mutate Adobe resources.

Version 1.1 adds the fixed colorful `bright-editorial-v1` email scaffold and draft-first authoring. Coworker generates the complete visual preview without a design interview, then asks once for unresolved activation facts before an AJO write.

## Configuration

Provide the deployed `my-mcp-server` connection through the Coworker host environment:

```text
AJO_MCP_URL=<deployed App Builder MCP endpoint>
ADOBE_IMS_TOKEN=<fresh Adobe IMS user access token>
ADOBE_IMS_ORG_ID=<IMS organization ID>
```

No credential, tenant identifier, or endpoint is committed to this marketplace.

## Installation

Install the marketplace and enable the `nordvell-brand` plugin in CX Coworker. Restart or refresh Coworker after installing or updating the plugin so its skills and MCP configuration are reloaded.

See `plugins/nordvell-brand/README.md` for prompts, required facts, outputs, and safety boundaries.
