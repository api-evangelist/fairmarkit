---
name: Create and award a Fairmarkit RFQ
description: Create an RFQ event, review incoming quotations, and award it to a supplier
  via the Fairmarkit Buyer API.
api: openapi/fairmarkit-buyer-openapi.json
operations:
- create_services_self_service_api_v3_rfq__post
- get_quotations_list_services_self_service_api_v3_rfq__uuid__quotations__get
- award_rfq_services_self_service_api_v3_rfq__uuid__award_post
- retrieve_services_self_service_api_v3_rfq__uuid___get
generated: '2026-07-19'
method: generated
---

# Create and award a Fairmarkit RFQ

## Steps
1. Authenticate every request with the `X-FM-API-KEY` header (see authentication/fairmarkit-authentication.yml).
2. Create the RFQ event with `create_services_self_service_api_v3_rfq__post` (POST /services/self-service/api/v3/rfq/). Capture the returned RFQ `uuid`.
3. Poll `get_rfq_list_services_self_service_api_v3_rfq__get` or fetch details with `retrieve_services_self_service_api_v3_rfq__uuid___get` to confirm the event is open.
4. Retrieve submitted quotations with `get_quotations_list_services_self_service_api_v3_rfq__uuid__quotations__get`.
5. Award the RFQ with `award_rfq_services_self_service_api_v3_rfq__uuid__award_post`, selecting quotation items and optionally passing a purchase-order number.

## Conventions
- Pagination is limit/offset. Validation failures return HTTP 422 (JSON); auth failures 401.
- No idempotency key — do not blindly retry POSTs; check state with the GET first.
- Subscribe to the `RFQ_AWARDED` webhook to confirm the award downstream.
