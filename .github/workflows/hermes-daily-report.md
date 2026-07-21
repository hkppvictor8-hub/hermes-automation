---
on:
  schedule: daily
  workflow_dispatch:
    inputs:
      research_topic:
        description: "Research topic for today's report"
        required: false
        default: "AI agent tools & automation"

permissions:
  contents: read

engine: copilot

safe-outputs:
  create-issue:
    title-prefix: "[hermes-daily] "
    labels: [hermes, daily-report, automated]
    close-older-issues: true
---

## Hermes 每日自動研究報告

Generate a daily research report for the Hermes AI agent ecosystem.

### Instructions

1. Search GitHub for trending repositories in the topics: AI agents, automation tools, LLM frameworks
2. Check the latest releases of hermes-agent on PyPI
3. Summarize key findings about:
   - New AI agent tools or frameworks
   - Security updates or vulnerabilities
   - Relevant open-source releases
4. Format the report as a GitHub issue with clear sections

### Output Format

Create a structured issue with:
- **Trending Repos**: Top 5 GitHub repos with stars + descriptions
- **AI Agent News**: Notable releases or updates
- **Security Note**: Any relevant CVEs or security patches
- **Recommendations**: What to integrate or watch

### Research Topic

{{ inputs.research_topic || "AI agent tools & automation" }}
