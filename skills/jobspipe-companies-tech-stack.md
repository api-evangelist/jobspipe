---
name: jobspipe-companies-tech-stack
description: Find companies that use a specific technology and retrieve their detailed tech stack.
api: openapi/jobspipe-openapi.json
operations:
- searchCompaniesByTechnology
- getCompanyTechnologies
generated: '2026-10-02'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/jobspipe-openapi.json ; every operationId checked against the contract
---

# jobspipe-companies-tech-stack

Find companies that use a specific technology and retrieve their detailed tech stack.

## Steps

1. 1. Call `searchCompaniesByTechnology` with the required request body fields (e.g., `technology`) and optional pagination parameters (`limit`, `cursor`, `offset`, `page`).
2. 2. From the response, extract the `key` of each company of interest.
3. 3. For each extracted `key`, call `getCompanyTechnologies` using the path parameter `{key}` to obtain the company's technology stack.

## Rules

- Auth: Include an `apiKey` value in the HTTP `Authorization` header as required by the API.
- Rate limiting: Do not exceed 2 requests per second; a 429 response indicates exhaustion.
- Pagination: Use `limit`, `cursor`, `offset`, or `page` query parameters as supported by `searchCompaniesByTechnology` to page through results.
