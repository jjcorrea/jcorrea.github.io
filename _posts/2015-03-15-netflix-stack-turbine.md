---
layout: post
title: Netflix Stack - Turbine
---

Turbine is a tool for **aggregating streams of Server-Sent Event (SSE) JSON data** into a single stream. The targeted use case is metrics streams from instances in an SOA being aggregated for dashboards.

For example, Netflix uses **Hystrix** which has a realtime dashboard that **uses Turbine to aggregate data** from 100s or 1000s of machines.

## References

- https://github.com/Netflix/Turbine/wiki