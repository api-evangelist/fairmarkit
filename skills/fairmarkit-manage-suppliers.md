---
name: Manage Fairmarkit suppliers
description: Create, list, update, activate/deactivate suppliers in Fairmarkit via
  the Buyer API.
api: openapi/fairmarkit-buyer-openapi.json
operations:
- create_services_self_service_api_v3_supplier__post
- list_services_self_service_api_v3_supplier__get
- update_services_self_service_api_v3_supplier__uuid___put
- SupplierApi_de_activate_services_self_service_api_v3_supplier__uuid__deactivate__post
generated: '2026-07-19'
method: generated
---

# Manage Fairmarkit suppliers

## Steps
1. Send `X-FM-API-KEY` on every request.
2. List existing suppliers with `list_services_self_service_api_v3_supplier__get` (limit/offset paginated) to avoid duplicates.
3. Create a supplier with `create_services_self_service_api_v3_supplier__post`, or load many with `bulk_create_services_self_service_api_v3_supplier_bulk_create__post`.
4. Update a supplier with `update_services_self_service_api_v3_supplier__uuid___put`; update diversity/business classifications with `update_services_self_service_api_v3_supplier__uuid__business_classifications__post`.
5. Deactivate with `SupplierApi_de_activate_services_self_service_api_v3_supplier__uuid__deactivate__post` and re-activate with `SupplierApi_re_activate_services_self_service_api_v3_supplier__uuid__activate__post`.

## Conventions
- Validation errors return HTTP 422. Deletes are soft deletes.
- The `SUPPLIER_CREATED` webhook fires on supplier creation.
