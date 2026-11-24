# PeakRoam MCP server

**Answers bulk-buying questions on event chairs, tables, canopies, tents and campground gear for US rental companies, campgrounds and FBA sellers.**

A free, public [MCP](https://modelcontextprotocol.io) server from [PeakRoam](https://superboutdoorco.com?utm_source=github&utm_medium=readme&utm_campaign=mcp): **PeakRoam Wholesale Outdoor Event Infrastructure Database**. Connect it to ChatGPT, Claude or another AI assistant and it answers from PeakRoam's published guides and articles, citing the page each answer comes from.

```
https://superboutdoorco.com/mcp
```

No sign-in, no API key, nothing to install. Listed in the [official MCP Registry](https://registry.modelcontextprotocol.io/v0.1/servers?search=com.superboutdoorco%2Fsite) as `com.superboutdoorco/site`.

## What you can ask

- "How many guests can I seat at a 48-inch round table compared to a 42-inch round?"
- "For a rental fleet, what's the real difference between steel folding chairs and consumer-grade folding chairs?"
- "What separates a heavy-duty commercial 10x10 canopy from a recreational one, and what fabric denier should I look for?"
- "What do tent waterproof ratings like 1500mm or 3000mm mean, and which seam types actually keep water out?"
- "What does Amazon FBA inspection involve for tents, wagons and cast iron cookware before they ship to a fulfillment center?"
- "Can I mix SKUs to reach a volume pricing tier, and how do MOQ, samples, private label and lead time usually work for bulk outdoor gear?"

## Tools

| Tool | What it does |
|---|---|
| `about_site` | Start here: what wholesale outdoor event infrastructure and bulk camping gear procurement database covers (Bulk event seating, tables and canopy planning, Campground and outdoor hospitality site equipment, Commercial-grade vs consumer chairs, tents and canopies, Amazon FBA inspection and specs for outdoor products, Tent seams, waterproof ratings, fabric denier, pole alloys, Wholesale pricing, volume tiers and mixing SKUs, Dealer-ready outdoor equipment assortments, Supplier quality, ISO 9001 and private labeling), who it is for (US event rental companies, campground operators, hospitality procurement teams and outdoor brands buying in bulk), and its free calculators. |
| `search_site` | Search wholesale outdoor event infrastructure and bulk camping gear procurement library: Bulk event seating, tables and canopy planning, Campground and outdoor hospitality site equipment, Commercial-grade vs consumer chairs, tents and canopies, Amazon FBA inspection and specs for outdoor products, Tent seams, waterproof ratings, fabric denier, pole alloys, Wholesale pricing, volume tiers and mixing SKUs, Dealer-ready outdoor equipment assortments, Supplier quality, ISO 9001 and private labeling. |
| `read_page` | The full text of one PeakRoam page: an article, guide, FAQ page or calculator page. |
| `ask_expert` | A question still open? With your OK, your name and email, the assistant sends it to PeakRoam's specialists, and a person replies by email. |

Every tool only reads PeakRoam's published pages, except `ask_expert`, which sends only what you approve.

## Connect it

**Claude** (claude.ai and desktop, every plan; Free allows one custom connector): Customize > Connectors > **+ Add** > **Add custom connector**. Name it, paste `https://superboutdoorco.com/mcp`, choose **No sign in**, then **Add**. In a chat: **+** > Connectors, switch it on. ([Claude help](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp))

**ChatGPT** (Pro, Business, Enterprise, Edu; web): **Plugins** > **+** > **Add custom MCP server**. Name it, paste the URL under Connection, accept the notice, **Create as a plugin**. In a new chat type **@** and pick it. ([OpenAI help](https://help.openai.com/en/articles/12584461))

**Claude Code**:
```bash
claude mcp add --transport http peakroam https://superboutdoorco.com/mcp
```
Or clone this repo: its `.mcp.json` connects it for the project.

**Cursor** (`~/.cursor/mcp.json`):
```json
{ "mcpServers": { "peakroam": { "url": "https://superboutdoorco.com/mcp" } } }
```

**VS Code (GitHub Copilot)**: Command Palette > **MCP: Add Server** > HTTP > paste the URL.

**Gemini CLI**:
```bash
gemini mcp add --transport http peakroam https://superboutdoorco.com/mcp
```

## Try it without an AI

```bash
curl -s https://superboutdoorco.com/mcp -H 'content-type: application/json' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/call","params":{"name":"search_site","arguments":{"query":"heavy-duty canopy"}}}'
```

## More from PeakRoam

- Website: [superboutdoorco.com](https://superboutdoorco.com?utm_source=github&utm_medium=readme&utm_campaign=mcp)
- Questions: [superboutdoorco.com/contact](https://superboutdoorco.com/contact?utm_source=github&utm_medium=readme&utm_campaign=mcp)

Answers are general information from PeakRoam's published pages.

## License

This repository (README and config) is MIT licensed. The server is operated by PeakRoam.
