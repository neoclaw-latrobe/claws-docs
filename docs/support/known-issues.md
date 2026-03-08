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

## Tool Error Warnings After Successful Operations

**Status:** Awaiting upstream fix  
**Affected:** All instances  
**Upstream Issue:** [openclaw/openclaw#39406](https://github.com/openclaw/openclaw/issues/39406)

### Symptoms

You may occasionally see warning messages like:

```
⚠️ 📝 Edit: in ~/IDENTITY.md (521 chars) failed
```

...even when your assistant reports that the task completed successfully.

### Cause

When a tool (like file edit) fails on the first attempt, OpenClaw immediately shows a warning. If the assistant retries and succeeds, you'll see both:

1. The success message ("Done!" or similar)
2. The earlier warning bubble

This is intentional upstream behavior — OpenClaw surfaces all tool errors, even transient ones the assistant recovered from.

### Workarounds

**Option 1: Trust the final message**

If your assistant says the task succeeded, it did. The warning refers to an earlier failed attempt that was automatically retried.

**Option 2: Check for confirmation**

Ask your assistant: "Did that actually work?" — it will confirm whether the operation succeeded.

### What the warnings mean

| Warning | What happened |
|---------|---------------|
| `Edit: ... failed` | File edit content didn't match; assistant likely retried with corrected content |
| `exec: ... failed` | Command failed; assistant may have adjusted and retried |
| `read: ... failed` | File not found or inaccessible; assistant may have tried an alternative path |

### Resolution

We've raised a feature request to add a config option that suppresses transient errors when the assistant self-corrects. We'll update all instances when this is available.

---

*Last updated: 8 March 2026*
