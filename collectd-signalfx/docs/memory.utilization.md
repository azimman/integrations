---
title: Memory utilization
brief: Percent of memory in use on this host. 
metric_type: gauge
---
### Memory utilization

This metric shows the amount of memory in use on this machine, as a percent of total memory available. The SignalFx metadata plugin computes this metric based on the metrics output by the `memory` plugin for collectd. First, compute the ratio of `memory.free` to the sum of all memory metrics. Next, subtract that number from 1 to yield the ratio of memory that is not free, and multiply by 100 to display as percent, as follows: 

```
100 * [1 - memory.free / sum(memory.*)]
```
