---
name: rental-listings
description: Manage the user's Reallyo rental listings - see the plan and how many more rentals it allows, find a listing, check or create one, change its rent, availability or status, and take it down.
---

Reallyo holds the user's own long-term rental listings and posts the available ones to Zillow and its other partner
rental sites. Renters' inquiries reach the user as leads. These steps use the Reallyo connector's tools.

1. Start with `whoami` when the plan or the listing limit matters, and pass on its `limit_summary` as it is.
2. Find a listing the user names by address with `list_listings` (`q` = the address words). Exactly one match: use its
   id. Several: show them and ask which. None: say so. Never change a listing the user did not clearly identify.
3. To add a listing, collect what an available listing needs (rent, description, bedrooms, bathrooms, the address) and
   ask for anything missing rather than inventing it. `validate_listing` checks a listing without saving anything;
   `create_listing` saves it. Give the user's own reference as `external_id` when they have one.
4. To change a listing, send only the fields that change with `update_listing`. A let unit is `{"status": "rented"}`.
5. `remove_listing` takes a listing down. It is kept, so it can be restored. Confirm with the user first.
6. After a change, report `last_change.result` and its message as Reallyo gives them. A change can be queued for a
   short while before it is applied; `get_listing` shows where it is.
7. Reallyo is for long-term rentals. Say so if the user asks about nightly or vacation lets.
