---
description: Look up, amend, or cancel an Airport Pickups London booking
argument-hint: <booking-ref> [action]
allowed-tools: [Read, Bash]
---

# Manage APL Booking

Look up, amend, or cancel an existing Airport Pickups London booking.

## Arguments

The user provided: $ARGUMENTS

## Instructions

1. Parse the booking reference (e.g. APL-CJ5KDJ or 959400) from the arguments
2. If no action specified, call `lookup_booking` to show booking details
3. If action is "cancel", call `cancel_booking` with the reference
4. If action is "amend" or "change", ask what they want to change, then call `amend_booking`
5. If action is "track", call `track_driver` to get live driver position

## Examples

```
/apl-booking APL-CJ5KDJ
/apl-booking APL-CJ5KDJ cancel
/apl-booking APL-CJ5KDJ track
/apl-booking 959400 amend
```

## Cancellation Policy

- 12+ hours before pickup: Free (£10 admin fee)
- 6-12 hours: 50% charge
- Under 6 hours: No refund — contact 0208 688 7744
