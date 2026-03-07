# Wireshark Lesson 10: Automation: API Request and Response Validation

## Scenario

Script says success but network state unchanged.

## Useful Filters

- http 

## Packet Analysis Procedure

1. 

## Interpretation Notes

-  tls
- ip.addr == 10.0.0.50|Capture automation host to API endpoint.
- Inspect method, URI, and response code.
- Inspect response payload for async job ID.
- Verify follow-up state check request and response.|HTTP success code alone may not confirm intent applied.
- Asynchronous operations require job completion polling.
- Payload mismatch can produce partial state changes.

## Verification Checklist

- Capture contains both failing and successful reference packets where possible.
- Root-cause statement cites exact packet evidence.
- After-fix capture demonstrates restored behavior.

## Reflection Exercise

1. Reproduce this scenario in your lab.
1. Capture before and after your fix.
1. Write a five-line root-cause summary from packet evidence.
