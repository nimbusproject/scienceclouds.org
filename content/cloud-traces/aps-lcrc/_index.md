---
Title: APS/LCRC
---

# APS/LCRC

The traces shared here are HPC cluster traces, instead of cloud traces. Two types of traces are included — the traces from a small Sun Grid Engine cluster in the [Advanced Photon Source](https://www.aps.anl.gov/) (APS) and the traces from a general purpose mid-scale cluster in [Laboratory Computing Resource Center](https://www.lcrc.anl.gov/) (LCRC) at Argonne National Laboratory (ANL). Both traces contain data from 2013-10-06 to 2015-09-05.

- Owner: Kate Keahey (keahey@mcs.anl.gov)
- Source: APS/LCRC
- Release Date: Jan 11, 2019
- Publications
  - [Liu, Feng, Kate Keahey, Pierre Riteau, and Jon Weissman. “Dynamically negotiating capacity between on-demand and batch clusters.” In Proceedings of the International Conference for High Performance Computing, Networking, Storage, and Analysis, p. 38. IEEE Press, 2018](https://dl.acm.org/citation.cfm?id=3291707).

## APS trace format

- submit_time: Timestamp when job submitted
- start_time: Timestamp when job started
- end_time: Timestamp when job ended
- run_time: Time difference between start_time and end_time
- wait_time: Time difference between submit_time and start_time

## LCRC trace format

- SubmitTime: Timestamp when job submitted
- StartTime: Timestamp when job started
- EndTime: Timestamp when job ended
- QueuedTime: Time difference between SubmitTime and StartTime
- RunTime: Time difference between StartTime and EndTime
- NodeRequested: Number of nodes requested by the job
- Walltime: Actual running time
- Bslowdown: Batch slow down

[Download the trace](/traces/aps_lcrc_traces.zip) (39.6 MB ZIP file, 206 MB uncompressed files)

Please contact the data owner for using this data for any research purpose prior to release and acknowledge the source of the data in any published material based on it.
