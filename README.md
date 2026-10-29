# prefrosh.ai MCP server

<img src="https://prefrosh.ai/icon-512.png" width="72" align="right" alt="prefrosh.ai">

College admissions data and a simulated admissions committee, inside Claude, ChatGPT and other AI chat apps.
Free, no sign-in, no API key.

**Server URL:** `https://prefrosh.ai/mcp` (remote, Streamable HTTP, no authentication)
**Website:** https://prefrosh.ai · **Docs:** https://prefrosh.ai/connector · **Registry:** `ai.prefrosh/prefrosh` in the [official MCP Registry](https://registry.modelcontextprotocol.io)

This repository holds the connector's public docs and registry manifest (`server.json`). The server itself is hosted at prefrosh.ai; there's nothing to install or run.

## Tools

| Tool | What it does | Try asking |
|---|---|---|
| `school_card` | One college as a card: admit rate overall and by round (Early Decision, Early Action, Regular), deadlines, SAT/ACT middle 50%, testing policy, sticker cost and average net price, graduation rate, biggest majors | "How hard is it to get into Tufts?" |
| `my_odds` | Estimated admission odds by round with a likely range, from GPA and test scores | "3.8 GPA, 1450 SAT, from NJ. My chances at Michigan, Northeastern and BU?" |
| `compare` | 2–4 colleges side by side, plus your odds if you give a GPA or scores | "Compare Bowdoin, Colby and Bates." |
| `admissions_game` | Runs the student's own application past a simulated committee: five fictional readers read, argue and vote, then the verdict and the top three fixes | "Here's my Common App. Run it past Georgetown, Early Action." |

`school_card`, `my_odds` and `compare` are read-only lookups. The admissions game is a simulation that gives feedback on the student's own words; it never writes or rewrites essays. Interactive cards show in clients that support MCP Apps (Claude, ChatGPT); elsewhere the same answers come back as text.

## Add it

**Claude** (any plan, including Free): Settings → Connectors → *Add custom connector* → paste `https://prefrosh.ai/mcp`, name it `prefrosh`, leave sign-in off.

**ChatGPT** (Pro, Business, Enterprise, Edu, in Developer Mode): Settings → Apps & Connectors → Advanced settings → turn on *Developer Mode*; then *Create*, name it `prefrosh`, paste the URL, no authentication.

**Any MCP client** that supports remote servers:

```json
{
  "mcpServers": {
    "prefrosh": { "type": "http", "url": "https://prefrosh.ai/mcp" }
  }
}
```

## Data and privacy

Admissions numbers come from each college's Common Data Set and US Department of Education data (IPEDS, College Scorecard), covering 1,000+ US colleges. Odds are estimates from grades and scores; essays, activities and recommendations move real outcomes a lot. What you send is used for that answer only and not saved. See the [privacy policy](https://prefrosh.ai/privacy) and [terms](https://prefrosh.ai/terms).

## Contact

hello@prefrosh.ai · https://prefrosh.ai/contact

Built by Dan Simmonds, with his daughter, during her own college search.
