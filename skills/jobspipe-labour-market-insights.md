---
name: jobspipe-labour-market-insights
description: Retrieve detailed labour market insights for a specific occupation, including ranking, snapshot, compensation, and top skills.
api: openapi/jobspipe-openapi.json
operations:
- insightsOccupations
- insightsOccupationSnapshot
- insightsCompensation
- insightsTopSkills
generated: '2026-10-02'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/jobspipe-openapi.json ; every operationId checked against the contract
---

# jobspipe-labour-market-insights

Retrieve detailed labour market insights for a specific occupation, including ranking, snapshot, compensation, and top skills.

## Steps

1. 1. Call `insightsOccupations` to list occupations (supports pagination via `limit`, `cursor`, `offset`, `page`).
2. 2. Call `insightsOccupationSnapshot` with the selected occupation `code` to get the occupation snapshot.
3. 3. Call `insightsCompensation` with the same `code` to obtain advertised compensation percentiles.
4. 4. Call `insightsTopSkills` with the same `code` to retrieve the top skills for that occupation.

## Rules

- Include an `apiKey` header for authentication (http scheme).
- Respect the rate limit of 2 requests per second; exceeding returns HTTP 429.
- Use pagination parameters (`limit`, `cursor`, `offset`, `page`) where supported.
