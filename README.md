# Airport Pickups London — Claude Code Plugin

Book UK airport and cruise port transfers directly from Claude Code. A complete end-to-end transfer booking workflow — quotes, flight validation, bookings, amendments, cancellations, and live driver tracking.

## What's Included

| Component | Description |
|-----------|-------------|
| **MCP Connector** | 7 tools via `mcp.airport-pickups-london.com` (OAuth 2.1) |
| **Skills** | 4 context-aware skills (quote, book, validate-flight, setup) |
| **Slash Commands** | `/apl-quote` and `/apl-booking` |
| **Sub-Agent** | Trip planner for multi-leg and group transfers |

## Supported Locations

**Airports**: Heathrow (T2-T5), Gatwick (N&S), Stansted, Luton, London City, Edinburgh
**Cruise Ports**: Southampton, Dover, Portsmouth, Harwich, Tilbury
**Addresses**: Any UK postcode, address, hotel, or city — nationwide coverage

## Installation

```bash
/plugin install airport-pickups-london@mfy-apl/claude-plugin-airport-pickups-london
```

No API keys needed — OAuth 2.1 auto-discovery handles authentication automatically.

## Usage

### Slash Commands

```
/apl-quote Heathrow to Oxford
/apl-quote Gatwick to Brighton 15 April 2026
/apl-booking APL-CJ5KDJ
/apl-booking APL-CJ5KDJ cancel
/apl-booking APL-CJ5KDJ track
```

### Natural Language

Just ask Claude:
- "How much is a taxi from Heathrow to central London?"
- "Get me a quote from Gatwick to Brighton for 4 passengers"
- "Book a transfer from Stansted to Cambridge"
- "I need a round trip — Heathrow to Oxford tomorrow and back on Friday"
- "We have 12 people arriving at Luton — what vehicles do we need?"
- "Check flight BA2534 on April 15th"
- "Where is my driver for booking APL-CJ5KDJ?"

### Trip Planner (Sub-Agent)

For complex requests, Claude spawns the trip planner agent to handle:
- Round trips (outbound + return)
- Multi-leg itineraries (airport → hotel → cruise port)
- Group vehicle planning (12+ passengers)
- Date comparisons

## Plugin Structure

```
airport-pickups-london/
├── .claude-plugin/plugin.json       # Plugin metadata
├── .mcp.json                        # MCP server (streamable HTTP, OAuth 2.1)
├── skills/
│   ├── setup/SKILL.md               # Setup & connection guide
│   ├── quote/SKILL.md               # Auto-triggers on price questions
│   ├── book/SKILL.md                # Auto-triggers on booking requests
│   └── validate-flight/SKILL.md     # Auto-triggers on flight checks
├── commands/
│   ├── apl-quote.md                 # /apl-quote slash command
│   └── apl-booking.md               # /apl-booking slash command
├── agents/
│   └── trip-planner.md              # Multi-leg & group planning agent
├── README.md
└── LICENSE                          # MIT-0
```

## MCP Server

- **Endpoint**: `https://mcp.airport-pickups-london.com/mcp`
- **Auth**: OAuth 2.1 (auto-discovery via `/.well-known/oauth-authorization-server`)
- **Server Card**: `https://www.airport-pickups-london.com/.well-known/mcp.json`
- **Registry**: Listed on `registry.modelcontextprotocol.io`

### Available Tools

| Tool | Description |
|------|-------------|
| `london_airport_transfer_quote` | Get fixed-price quotes for any UK route |
| `book_london_airport_transfer` | Create confirmed bookings |
| `validate_flight` | Verify flight numbers, get terminal info |
| `lookup_booking` | Check booking status and details |
| `amend_booking` | Modify booking details |
| `cancel_booking` | Cancel a booking |
| `track_driver` | Live GPS driver tracking |

## Pricing

- All prices in GBP (£), **per vehicle** (not per person)
- Fixed prices — no surge, no hidden charges
- Includes meet & greet, flight monitoring, waiting time, parking
- Free cancellation 12+ hours before pickup

## Vehicle Types

| Vehicle | Passengers | Bags | From |
|---------|-----------|------|------|
| Saloon | Up to 3 | 3 | ~£33 |
| People Carrier | Up to 5 | 5 | ~£45 |
| 8 Seater | Up to 8 | 8 | ~£55 |
| Executive Saloon | Up to 3 | 3 | ~£65 |
| Executive MPV | Up to 7 | 7 | ~£85 |
| Executive 8 Seater | Up to 8 | 8 | ~£95 |

## Support

- 24/7 Phone: +44 208 688 7744
- WhatsApp: +44 7425 987310
- Email: info@aplcars.com
- Website: https://www.airport-pickups-london.com

## License

MIT-0 — Free to use, modify, and redistribute. No attribution required.
