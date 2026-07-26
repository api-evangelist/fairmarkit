---
name: Respond to a Fairmarkit buyer request (Supplier API)
description: As a supplier, list buyer requests, review a request, and submit or reject
  a response.
api: openapi/fairmarkit-supplier-openapi.json
operations:
- get_requests-Requests_Requests_Requests
- get_request-Requests_Requests_Requests
- submit_response-Requests_Requests_Requests
- reject_request-Requests_Requests_Requests
generated: '2026-07-19'
method: generated
---

# Respond to a Fairmarkit buyer request (Supplier API)

## Steps
1. Authenticate with the supplier `X-FM-API-KEY` (suppliers may hold up to 5 keys).
2. List requests buyers created for your company with `get_requests-Requests_Requests_Requests`.
3. Retrieve full detail for a request with `get_request-Requests_Requests_Requests`.
4. Submit a bid/response with `submit_response-Requests_Requests_Requests`, or decline with `reject_request-Requests_Requests_Requests`.
5. Check your submitted response with `get_request_response-Requests_Requests_Requests`.

## Conventions
- Supplier API base host is https://uat.fairmarkit.com. Pagination is limit/offset. Validation errors return HTTP 422.
