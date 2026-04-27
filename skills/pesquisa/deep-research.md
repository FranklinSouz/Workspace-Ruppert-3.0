---
name: deep-research
description: Conduct deep research on any topic by planning the investigation, gathering at least 5 credible and varied sources, comparing viewpoints, identifying trends, and synthesizing a recommendation tailored to the user's context. Use when the user asks for deep research, market/competitor analysis, tool comparisons, interview or podcast preparation, trend mapping, paper/article synthesis, or executive-ready research briefs with sources and recommendations.
---

# Deep Research

## Overview

Use this skill to turn a broad research request into a structured, multi-source analysis with a clear recommendation.

Prefer high-quality synthesis over speed. Use thinking mode when available, and expand or refine the scope before researching if the topic is ambiguous.

## Workflow

### 1. Define the research frame

Clarify or infer:
- The exact topic or decision the user cares about
- The user's context, constraints, region, budget, audience, or technical level
- The desired depth, time horizon, and output format

If the prompt is broad, restate the scope in one tight sentence before proceeding.

### 2. Build a research plan

Break the topic into parallel lanes such as:
- Market landscape
- Primary tools or approaches
- Expert opinions and debates
- Recent developments and trends
- User sentiment or practitioner reports
- Pricing, positioning, or competitor signals

When sub-agents are available, split research lanes across them and consolidate the findings. Avoid redundant searches.

### 3. Gather diverse sources

Use at least 5 distinct and relevant sources. Mix source types when possible, such as:
- Official docs or company pages
- Reputable articles or industry analysis
- Academic papers or technical reports
- Community discussions (Reddit, Hacker News, forums)
- Newsletters, interviews, podcasts, or social posts with signal

Prefer recent sources for fast-moving topics. For evergreen topics, combine foundational and current material.

For every source, capture:
- Title
- Link
- Date if available
- What it claims
- How trustworthy or biased it may be

### 4. Analyze instead of just summarizing

For each major claim:
- Compare where sources agree or disagree
- Separate marketing language from evidence
- Note missing data, tradeoffs, and uncertainty
- Identify what is changing versus what is stable

Look explicitly for:
- Pros and cons of each approach
- Open debates or unresolved questions
- Emerging trends and weak signals
- Practical implications for the user's situation

### 5. Compare options clearly

When the topic involves solutions, competitors, or approaches, produce a compact comparison covering the factors that matter most, for example:
- Price or business model
- Core features or capabilities
- Strengths
- Weaknesses
- Ideal use case
- Risks or limitations

Use a table only when it truly improves readability.

### 6. Make a recommendation

Do not stop at neutral summary. Give a recommendation grounded in:
- The user's stated or inferred context
- The evidence quality
- Cost, risk, complexity, and likely upside
- Short-term next steps

If confidence is limited, say so and explain what would change the recommendation.

## Required output structure

Use this default structure unless the user asks for another format:

### Resumo executivo
- Write 3 short paragraphs for a decision-maker in a hurry
- State the core conclusion early
- Highlight the biggest tradeoff or opportunity

### Análise detalhada
- Organize by source or theme
- Include links inline
- Explain what each source contributed, not just what it said

### Comparativo
- Compare the main solutions, schools of thought, or competitors
- Use bullets or a table if helpful

### Recomendação
- Say what the user should do next
- Tailor to the user's profile, budget, maturity, or goals when known

### Fontes
- List the links cleanly so the user can go deeper

## Variations

### Competitor research

For competitor analysis, include for each competitor when available:
- Pricing
- Core features
- Positioning
- Strengths
- Weaknesses
- Recent launches, posts, or moves
- Gaps the user can exploit

### Interview or podcast prep

For people research, cover:
- Trajectory and current role
- Notable projects
- Public opinions or controversial takes
- Recent appearances or content
- Angles that are overused versus underexplored

Then propose 10 differentiated questions.

### Trend analysis

For trend mapping, prioritize:
- Newsletters
- Practitioner communities
- Social chatter with strong signal
- Product launches and funding patterns
- Repeated themes across multiple independent sources

Distinguish hype from real adoption.

## Quality bar

Before finalizing, check that the output:
- Uses at least 5 meaningful sources
- Includes multiple viewpoints
- Identifies what is changing
- Compares the main options
- Ends with a user-specific recommendation
- Cites sources with links

If the evidence is thin, say that directly instead of pretending certainty.

