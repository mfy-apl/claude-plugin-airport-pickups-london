---
name: apl-setup
description: "This skill activates when the user installs the Airport Pickups London plugin, or asks to set up, configure, or connect the APL transfer booking service."
version: 1.0.0
---

# Airport Pickups London — Setup Guide

## Automatic Setup

This plugin connects to the Airport Pickups London MCP server automatically via OAuth 2.1. No API keys or manual configuration needed.

### What Happens on Install

1. The `.mcp.json` configures the MCP server at `https://mcp.airport-pickups-london.com/mcp`
2. When you first use a tool (e.g. get a quote), OAuth auto-discovery kicks in:
   - Discovers auth server via `/.well-known/oauth-authorization-server`
   - Registers a client automatically via `/register`
   - Obtains an access token via `/token`
3. You're ready to get quotes and make bookings

### Verify the Connection

Ask Claude: "Get me a quote from Heathrow to Oxford" — if prices come back, everything is working.

### If Something Goes Wrong

1. **"Unauthorized" errors**: The OAuth token may have expired. Ask Claude to retry — it will auto-refresh.
2. **"Connection refused"**: The MCP server may be temporarily down. Try again in a moment. 24/7 support: +44 208 688 7744.
3. **No tools showing**: Run `/plugin list` to verify the plugin is installed, then try `/apl-quote Heathrow to Oxford`.

## What You Can Do

Once connected, you can:

- **Get quotes**: "How much from Gatwick to Brighton for 3 passengers?"
- **Book transfers**: "Book a People Carrier from Heathrow T5 to Oxford for tomorrow"
- **Check flights**: "Verify flight BA2534 on April 15th"
- **Manage bookings**: "Look up booking APL-CJ5KDJ" / "Cancel booking APL-CJ5KDJ"
- **Track drivers**: "Where is my driver for booking APL-CJ5KDJ?"

## Coverage

**Airports**: Heathrow (T2-T5), Gatwick (N&S), Stansted, Luton, London City, Edinburgh
**Cruise Ports**: Southampton, Dover, Portsmouth, Harwich, Tilbury
**Addresses**: Any UK postcode, hotel, or address — nationwide coverage
