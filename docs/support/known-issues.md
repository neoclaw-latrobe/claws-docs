# Known Issues

This page tracks known issues affecting Hosted Claws instances and their workarounds.

---

## Config Editor Slow to Load

**Status:** Awaiting upstream fix  
**Affected:** All instances  
**Upstream Issue:** [openclaw/openclaw#10384](https://github.com/openclaw/openclaw/issues/10384)

### Symptoms

When opening the Config Editor in the WebUI for the first time, the page may appear to hang or load indefinitely for **2-3 minutes**. The gateway remains responsive during this time, but the WebUI tab will appear stuck.

### Cause

The Config Editor requests the full OpenClaw configuration schema on first load. This schema is large (~400KB) and takes significant time to generate and transmit on resource-constrained containers.

### Workarounds

**Option 1: Wait for initial load**

The first load takes 2-3 minutes, but the schema is then cached in your browser. Subsequent visits to the Config Editor will load instantly (until you clear browser data).

**Option 2: Use chat commands instead**

If you have a messaging channel connected (Discord, Telegram, etc.), you can manage your configuration entirely via chat commands:

```
/config get models.default          # View a setting
/config set models.default gpt-5    # Change a setting
/config list                        # See available options
```

This bypasses the WebUI entirely and responds immediately.

### Resolution

We are monitoring the upstream issue and will update all customer instances as soon as a fix is released.

---

*Last updated: 7 March 2026*
