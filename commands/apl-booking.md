---
description: Look up, amend, or cancel an Airport Pickups London booking
argument-hint: <booking-ref> [action]
---

# Manage APL Booking

Look up, amend, or cancel an existing Airport Pickups London booking.

## Arguments

The user provided: $ARGUMENTS

## Instructions

1. Parse the booking reference (a plain reservation number, e.g. 1031380) from the arguments
2. If no action specified, call `lookup_booking` to show booking details
3. If action is "cancel", call `cancel_booking` with the reference
4. If action is "amend" or "change", ask what they want to change, then call `amend_booking`
5. If action is "track", call `track_driver` to get live driver position

## Examples

```
/apl-booking 1031380
/apl-booking 1031380 cancel
/apl-booking 1031380 track
/apl-booking 1026044 amend
```

## Cancellation Policy

- 12+ hours before pickup: free cancellation, no fee (the tool cancels it)
- 6–12 hours before pickup: 50% of the fare is charged — the tool cannot cancel inside 12 hours; the customer calls +44 20 8688 7744
- Under 6 hours: no refund — call +44 20 8688 7744
