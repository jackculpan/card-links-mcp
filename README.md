# Card Links MCP

A remote MCP server that gives any Claude client live credit card data — welcome bonuses, earn rates, annual fees, benefit credits, and transfer partners — across **US, UK, AU, and EU** markets.

## Add to Claude

**Claude.ai** (Max/Team/Enterprise): Settings → Integrations → Add more → paste:
```
https://mcp.milesandpointsdaily.com/mcp
```

**Claude Desktop** (`claude_desktop_config.json`):
```json
{
  "mcpServers": {
    "card-links": {
      "url": "https://mcp.milesandpointsdaily.com/mcp"
    }
  }
}
```

**Smithery / other MCP clients**: search for `card-links` or use the URL above.

## What it does

| Tool | Description |
|---|---|
| `list_cards` | Browse all cards — filter by region, provider, or card type |
| `get_card` | Full card details: all multipliers, benefits, welcome bonus |
| `compare_cards` | Head-to-head on 2–4 cards (fees, bonuses, net annual cost) |
| `find_cards_for_category` | Best earn rate for a spend bucket — supports UK/AU terms like "petrol", "woolworths" |
| `rank_welcome_bonuses` | Current SUBs ranked by points value, filterable by spend achievability |
| `analyze_spending` | Score every card against a monthly spend breakdown; returns net annual fee after benefit credits |
| `list_changes` | What changed in card data recently — bonus updates, fee changes |
| `list_transfer_partners` | All airline/hotel transfer programs by region |
| `find_transfer_programs_for_airline` | Which programs transfer to a given airline or hotel |

## Coverage

**82 cards** across 9 providers and 8 regions, updated weekly.

| Region | Issuers |
|---|---|
| 🇺🇸 US | Amex, Chase, Bilt, Capital One |
| 🇬🇧 UK | Amex, Barclaycard, HSBC, Virgin Money, Lloyds, Yonder, Currensea |
| 🇦🇺 AU | Amex, ANZ, NAB, Westpac, CommBank |
| 🇪🇺 EU | Amex (DE, FR, IT, ES, NL) |

### US highlights
Amex Gold/Platinum/Green · Business Gold/Platinum · Hilton Honors/Surpass/Aspire · Delta Gold/Platinum/Reserve · Marriott Brilliant/Bevy · Chase Sapphire Preferred/Reserve · Ink Preferred/Cash/Unlimited · Freedom Unlimited/Flex · United Explorer/Quest/Club Infinite · Marriott Boundless/Bold · Bilt Blue/Palladium · Capital One Venture/Venture X

### UK highlights
Amex Gold/Platinum · Barclaycard Avios Plus/Avios · HSBC Premier World Elite · Virgin Atlantic Reward/Reward+ · Lloyds Avios · Yonder Free/Full · Currensea Essential/Premium/Elite + KrisFlyer/Marriott/Hilton/United co-brands

## Affiliate URLs

Add `?ref=<your-id>` to the MCP URL to surface your affiliate apply links in every tool response:
```
https://mcp.milesandpointsdaily.com/mcp?ref=youraffiliatehandle
```

Register at `POST /affiliates/register` to get your ID and API key, then upload your card links at `PUT /affiliates/links`.

## Endpoints

| Method | Path | Description |
|---|---|---|
| POST | `/mcp` | MCP server (Streamable HTTP, JSON-RPC 2.0) |
| GET | `/cards` | REST: list cards |
| GET | `/cards/:id` | REST: get card |
| GET | `/changes` | REST: recent changes |
| GET | `/transfer-partners` | REST: transfer programs |
| GET | `/health` | Health check |

## License

Data from public issuer pages. Code MIT.
