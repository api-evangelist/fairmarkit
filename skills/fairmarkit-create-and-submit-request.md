---
name: Create and submit a Fairmarkit request (v4)
description: Create a v4 Request, add request items, and submit it for sourcing via
  the Buyer API.
api: openapi/fairmarkit-buyer-openapi.json
operations:
- RequestApi_create_request_services_self_service_api_v4_requests__post
- RequestApi_create_request_item_batch_services_self_service_api_v4_requests__request_id__items_batch_post
- RequestApi_submit_request_services_self_service_api_v4_requests__request_id__submit_post
generated: '2026-07-19'
method: generated
---

# Create and submit a Fairmarkit request (v4)

## Steps
1. Authenticate with `X-FM-API-KEY`.
2. Fetch the current request schema with `SchemaApi_get_current_schema_services_self_service_api_v3_schemas_current_get` so the request/item payload matches the account schema.
3. Create the request with `RequestApi_create_request_services_self_service_api_v4_requests__post` (v4 — the v3 create is deprecated). Capture `request_id`.
4. Add items with `RequestApi_create_request_item_batch_services_self_service_api_v4_requests__request_id__items_batch_post` (batch) or `RequestApi_create_item_services_self_service_api_v4_requests__request_id__items__post`.
5. Submit with `RequestApi_submit_request_services_self_service_api_v4_requests__request_id__submit_post`.

## Conventions
- Use v4 endpoints; v3 Requests operations are deprecated. Validation errors return HTTP 422.
- Track lifecycle via `REQUEST_SUBMITTED` / `REQUEST_IN_PROGRESS` webhooks.
