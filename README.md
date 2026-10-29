# HelloGem for Claude

Know what a cosmetic ingredient is, what it does, and who says so.

Ask Claude about a name on a cosmetic ingredient label, by its INCI, common or chemical name. Claude looks it up with HelloGem and answers in plain words. HelloGem returns source-attributed statements, each with its source and link:

- cosmetic functions and short definitions from CosIng, the EU's cosmetic ingredient database;
- chemical roles from ChEBI, a chemistry reference, and roles HelloGem infers from cosmetic functions, labelled as inferences;
- descriptions from skincare brands, an editorial ingredient website and an industry reference, credited to whichever source said them.

The plugin's skill asks Claude to keep each statement with its source, so you can see who says what. Coverage varies: some ingredients have several sources, some have one or none.

HelloGem explains ingredients. It doesn't judge safety, give medical advice, suggest concentrations, review formulas or certify regulatory status.

## What's in this plugin

- A connection to HelloGem's hosted, read-only service at `https://api.hellogem.ai/mcp`, with two tools: `search_ingredients` and `get_ingredient`. You don't need a HelloGem account or API key, only a Claude plan that lets you add plugins.
- One skill, `explain-ingredient`, which tells Claude how to answer: lead with what you asked, say who says what, keep a definition (what an ingredient is) apart from a function (what it does), and treat a related term as another name only when HelloGem confirms it's the same ingredient.

There are no hooks, commands, agents or scripts.

## Install

**Claude apps (web and desktop)**

1. Download `hellogem-0.1.0.zip` from this repository's [latest release](https://github.com/omnishades/hellogem-claude/releases/latest).
2. In Claude, go to **Customize > Plugins**, select **Add**, then **Upload plugin**, and choose the ZIP.
3. Open HelloGem, go to its **Connectors** tab and connect **hellogem**. It doesn't ask you to sign in.

**Claude Code**

```
claude plugin install hellogem --marketplace omnishades/hellogem-claude
```

Or, inside a session:

```
/plugin marketplace add omnishades/hellogem-claude
/plugin install hellogem@hellogem
```

Claude Code connects to HelloGem directly. Start a new session after installing.

## Try it

- "What does glycerin do in skincare? Show who says what."
- "What is Nonapeptide-9 on an ingredient label?"
- "Is nicotinamide the same ingredient as niacinamide?"
- "What is tocopherol, and who says so?"

Names are matched exactly as written. If a name isn't listed, the skill tells Claude to say so rather than guess. When several ingredients match, Claude shows them and asks which you mean.

## What is sent and stored

When Claude uses a HelloGem tool, it sends HelloGem the ingredient name or ID, and HelloGem returns the result. HelloGem stores each request with its exact result privately, so a report can refer to it. Records expire after 365 days. HelloGem doesn't receive your conversation; Anthropic handles that under your Claude account. See the [privacy policy](https://api.hellogem.ai/privacy).

## Reporting a problem

Each HelloGem result comes with its own report link, and the skill asks Claude to end its answer with it as **Report an issue**. Your report is tied to that exact request and result. Claude's wording isn't included, so if the wording is the problem, paste that part into your report.

## Links

- Website: https://hellogem.ai/
- Support: https://api.hellogem.ai/support
- Privacy: https://api.hellogem.ai/privacy
- Terms: https://api.hellogem.ai/terms
- Sources and attribution: https://api.hellogem.ai/attribution

## License

The files in this repository are released under the MIT License; see [LICENSE](LICENSE). The license covers these plugin files only. It doesn't license the hosted HelloGem service, its data, or any third-party source material, which remain under their own terms; see [Sources and attribution](https://api.hellogem.ai/attribution).
