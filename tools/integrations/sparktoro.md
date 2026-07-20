# SparkToro

Audience research platform that reveals what your target audience reads, watches, listens to, follows, and searches for — using clickstream data, Google search data, and public social profiles.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | Yes | Magister uses the company-managed SparkToro REST API through built-in audience-research actions |
| MCP | Yes | SparkToro also offers a separate OAuth MCP connection for customer-owned accounts |
| CLI | - | Not available |
| SDK | - | Not available |

Use Magister's built-in actions for product workflows. Do not scrape the SparkToro web app or call SparkToro's raw endpoints from an agent.

## Authentication

- **Magister runtime**: Company-provided server credential; users do not paste or manage a SparkToro API key
- **Direct REST API**: Bearer API key and prepaid credits, separate from SparkToro subscriptions
- **SparkToro MCP**: OAuth 2.1 against the user's own SparkToro account; separate from Magister's built-in REST integration

## API Credits

- Creating an audience report costs provider credits; requested sections add variable cost.
- Re-reading the same section for the same report is free after its first successful purchase.
- Magister always estimates customer credits before a run and settles the actual charge when the durable research job completes.
- API bundles, trial allowances, and endpoint prices can change; use SparkToro's current API credit page as the source of truth.

## What SparkToro Reveals

### Audience Behaviors
- **Websites** they visit and engage with
- **Podcasts** they listen to
- **YouTube channels** they watch
- **Subreddits** they participate in
- **Social accounts** they follow
- **Search keywords** they use on Google
- **AI prompt topics** they ask ChatGPT, Claude, Gemini

### Audience Demographics
- Gender, age ranges
- Job titles and roles
- Industries and skills
- Education levels
- Geographic distribution
- Interests and affinities

### Audience Characteristics
- Bio descriptions and self-identifiers
- Language patterns in posts and comments
- Preferred social networks and platforms
- E-commerce platforms they use

## Common Agent Operations

Use the three built-in actions in this order:

1. `estimate_audience_research` with a precise audience, location, and workflow profile.
2. Show the scope and estimated credits, then obtain explicit user confirmation.
3. Call `start_audience_research` once with a stable idempotency key.
4. Poll `get_audience_research` until it reaches a terminal state.

Choose the narrowest profile that answers the decision: `campaign_brief`, `influencer_media`, `content_demand`, `icp_validation`, or `ai_positioning`. Use `custom` only when the needed sections do not fit a standard profile.

### Audience Profile Research

Describe one concrete audience with signals such as:
- "People who follow @competitor" — reveals shared audience behaviors
- "People who visit competitor.com" — shows what else they consume
- "People who frequently talk about [topic]" — finds audience affinities
- "People whose bio contains [job title]" — profiles a role-based segment

### Finding Where Your ICP Spends Time

1. Define the ICP by role, problem, behavior, competitor affinity, or website affinity.
2. Run the `influencer_media` profile after estimate and confirmation.
3. Turn the policy-safe result into a prioritized outreach, sponsorship, or community-testing plan.

### Discovering Content Topics

1. Define the audience segment and the content decision to make.
2. Run `content_demand` for search and channel demand, or `ai_positioning` for AI-question patterns.
3. Use the resulting themes as hypotheses, then validate exact keywords with DataForSEO before committing SEO or paid-search budget.

### Building Data-Backed Personas

1. Propose distinct, precise segment descriptions.
2. Estimate each run before asking the user which segments to purchase.
3. Run `icp_validation` separately for each approved segment.
4. Compare the derived evidence and design follow-up qualitative research for the "why."

### Competitive Audience Analysis

1. Describe the competitor-affinity audience and the brand's intended audience as separate segments.
2. Estimate both; do not purchase both without explicit approval.
3. Compare the completed derived results for channel, message, and experiment gaps.

## Data Sources

SparkToro aggregates from three sources:
- **Clickstream data** — anonymized browsing behavior
- **Google search results** — search keyword patterns
- **Public social profiles** — bios, follows, engagement

## When to Use

- Identifying where your ICP spends time online (podcasts, YouTube, subreddits, websites)
- Finding influencers and social accounts your audience follows
- Discovering content topics and search keywords your audience cares about
- Building data-backed personas instead of assumption-based ones
- Planning podcast guest appearances, sponsorships, or content partnerships
- Understanding what your competitors' audience looks like
- Validating audience assumptions with behavioral data
- Discovering AI prompt topics your audience uses

## Limitations

- Research is paid and variable-cost; estimate and confirm before every new or refreshed report
- Magister exposes policy-safe derived outputs by default, not raw provider payloads, identifiers, rankings, scores, percentages, or source lists
- External display of SparkToro data points requires a separate written agreement and attribution; derived output mode does not reproduce those data points
- Data skews toward English-language, US-centric audiences
- Clickstream data may not capture all niche audiences
- Cannot track individual users — all data is aggregated and anonymized

## Relevant Skills

- customer-research
- content-strategy
- competitors
- ads
- social
- cold-email
