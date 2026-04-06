---
Title: Cloud Trace Format
---

# Cloud Trace Format

## Version: 0.3
**Date:** November 1, 2019

### Major Changes

We adapted the trace format from the last version, so that the new format can be used for both virtual machine and bare-metal instances.

### Anonymization Techniques

*(No change from the last version)*

For confidentiality reasons, we have anonymized certain fields in the traces. Different anonymization methods were applied to different fields.

*Hashed*: We applied keyed cryptographic hash to the fields INSTANCE_UUID, INSTANCE_NAME, USER_ID, PROJECT_ID and HOST_NAME (PHYSICAL). The same key and hashed method were applied to the HOST_NAME (PHYSICAL) fields in both tables, so the two tables can reference each other.

*Ordered*: This technique is applied to RACK field in the machine events table. The list of observed unique RACK values is sorted. Then, we assigned sequential numbers starting with 0 to the items of the RACK list, and the observed values are mapped onto these numbers.

### Time and Timestamps

*(No change from the last version)*

For instance events, we provided two times — the event start time and the event finish time, but for machine events, we only provide one time — the event time. We present all time fields in two ways. The actual time in UTC and the time difference in seconds between the actual time and the trace period start time. For the event times that were before the trace period start time, we marked the time difference field -1.

### Data Tables

#### Machine Events

File Name: `machine_events.csv`

| Trace Field Name | Database Fields | Description |
|---|---|---|
| EVENT_TIME | **vm:** nova.compute_nodes.created_at, nova.compute_nodes.updated_at, nova.compute_nodes.deleted_at, nova.services.updated_at **bare-metal:** ironic.nodes.created_at, blazar.computehosts.updated_at, blazar.computehost_extra_capabilities.created_at, blazar.computehost_extra_capabilities.updated_at | The time when the event happened in UTC. |
| EVENT_TIME_SEC | N/A | The time difference in seconds between the EVENT_TIME and the trace epoch time. |
| HOST_NAME (PHYSICAL) | **vm:** nova.compute_nodes.host **bare-metal:** ironic.nodes.uuid | Name/ID of the physical machine. Reference the instance events table using this field. |
| EVENT | N/A | CREATE, UPDATE, DELETE, DISABLE, ENABLE |
| PROPERTIES | **vm:** compute_nodes.vcpus, compute_nodes.memory_mb, compute_nodes.local_gb **bare-metal:** blazar.computehost_extra_capabilities.capability_name, blazar.computehost_extra_capabilities.capability_value | The properties of the machine. (JSON formatted field.) |

#### Instance Events

File Name: `instance_events.csv`

| Trace Field Name | Nova Database Fields | Description |
|---|---|---|
| INSTANCE_UUID | instances.uuid | The unique id for each instance created by OpenStack. |
| EVENT | instance_actions_events.event | The event corresponds to the type of action performed on an OpenStack instance. |
| START_TIME | instance_actions_events.start_time | The time when a related event started executing. |
| START_SEC | N/A | The time difference, in seconds, between the START_TIME and the trace epoch time. |
| FINISH_TIME | instance_actions_events.finish_time | The time when a related event completed. |
| FINISH_SEC | N/A | The time difference, in seconds, between the FINISH_TIME and the trace epoch time. |
| EVENT_DURATION | N/A | The time difference between START_TIME and FINISH_TIME. |
| RESULT | instance_actions_events.result | Status of each action event. If the result is not success or null, then this action event was not successfully. |
| INSTANCE_NAME | instances.hostname | The name provided by the user while creating the instance. This name is not unique. Many instances can have the same instance name. |
| USER_ID | instances.user_id | The user identifier of the account from which the instance was created. |
| PROJECT_ID | instances.project_id | The project identifier of the account from which the instance was created. |
| HOST_NAME (PHYSICAL) | instances.host | Name/ID of the physical computer hosting the instance. Reference the machine events table using this field. |
| PROPERTIES | **vm:** instances.memory_mb, instances.root_gb, instances.vcpus **bare-metal:** N/A | The properties of the instance. (JSON formatted field.) |

---

## Version: 0.2
**Date:** December 17, 2018

### Major Changes

Along with the instance events table, a new machine events table is added to the cloud traces. Each machine (physical host) is described by one or more records in the machine events table.

### Anonymization Techniques

For confidentiality reasons, we have anonymized certain fields in the traces. Different anonymization methods were applied to different fields.

*Hashed*: We applied keyed cryptographic hash to the fields INSTANCE_UUID, INSTANCE_NAME, USER_ID, PROJECT_ID and HOST_NAME (PHYSICAL). The same key and hashed method were applied to the HOST_NAME (PHYSICAL) fields in both tables, so the two tables can reference each other.

*Ordered*: This technique is applied to RACK field in the machine events table. The list of observed unique RACK values is sorted. Then, we assigned sequential numbers starting with 0 to the items of the RACK list, and the observed values are mapped onto these numbers.

### Time and Timestamps

For instance events, we provided two times — the event start time and the event finish time, but for machine events, we only provide one time — the event time. We present all time fields in two ways. The actual time in UTC and the time difference in seconds between the actual time and the trace period start time. For the event times that were before the trace period start time, we marked the time difference field -1.

### Data Tables

#### Machine Events

File Name: `machine_events.csv`

| Trace Field Name | Nova Database Fields | Description |
|---|---|---|
| EVENT_TIME | compute_nodes.created_at, compute_nodes.updated_at, compute_nodes.deleted_at, services.updated_at | The time when the event happened in UTC. |
| EVENT_TIME_SEC | N/A | The time difference in seconds between the EVENT_TIME and the trace period start time. |
| HOST_NAME (PHYSICAL) | compute_nodes.host | Name of the physical machine hosting the KVM instance. Reference the instance events table using this field. |
| RACK | N/A | The rack number which the machine belongs to. Extracted from the host name. |
| EVENT | N/A | CREATE, UPDATE, DELETE, DISABLE, ENABLE |
| VCPU_CAPACITY | compute_nodes.vcpus | The available number of virtual CPUs. |
| MEMORY_CAPACITY_MB | compute_nodes.memory_mb | The available memory in MB. |
| DISK_CAPACITY_GB | compute_nodes.local_gb | The available disk in GB. |

#### Instance Events

File Name: `instance_events.csv`

| Trace Field Name | Nova Database Fields | Description |
|---|---|---|
| INSTANCE_UUID | instances.uuid | The unique id for each KVM instance created by OpenStack. |
| EVENT | instance_actions_events.event | The event corresponds to the type of action performed on an OpenStack instance. |
| START_TIME | instance_actions_events.start_time | The time when a related event started executing. |
| START_SEC | N/A | The time difference, in seconds, between the START_TIME and the trace period start time. |
| FINISH_TIME | instance_actions_events.finish_time | The time when a related event completed. |
| FINISH_SEC | N/A | The time difference, in seconds, between the FINISH_TIME and the trace period start time. |
| EVENT_DURATION | N/A | The time difference between START_TIME and FINISH_TIME. |
| RESULT | instance_actions_events.result | Status of each action event. If the result is not success or null, then this action event was not successfully. |
| MEMORY_MB | instances.memory_mb | Amount of RAM assigned to an instance at creation. |
| DISK_GB | instances.root_gb | Amount of disk assigned to an instance at creation. |
| VCPUS | instances.vcpus | The number of virtual CPUs assigned to an instance at creation. |
| INSTANCE_NAME | instances.hostname | The name provided by the user while creating the VM. This name is not unique. Many instances can have the same instance name. |
| USER_ID | instances.user_id | The user identifier of the account from which the VM was created. |
| PROJECT_ID | instances.project_id | The project identifier of the account from which the VM was created. |
| HOST_NAME (PHYSICAL) | instances.host | Name of the physical computer hosting the KVM instance. Reference the machine events table using this field. |

---

## Version: 0.1
**Date:** July 31, 2017

| Trace Field Name | Nova Database Fields |
|---|---|
| INSTANCE_UUID | instances.uuid |
| EVENT | instance_actions_events.event |
| START_TIME | instance_actions_events.start_time |
| START_SEC | *derived from START_TIME* |
| FINISH_TIME | instance_actions_events.finish_time |
| FINISH_SEC | *derived from FINISH_TIME* |
| EVENT_DURATION | *derived from START_TIME and FINISH_TIME* |
| RESULT | instance_actions_events.result |
| MEMORY_MB | instances.memory_mb |
| DISK_GB | instances.root_gb |
| VCPUS | instances.vcpus |
| INSTANCE_NAME | instances.hostname |
| USER_ID | instances.user_id |
| PROJECT_ID | instances.project_id |
| HOST_NAME (PHYSICAL) | instances.host |

### Field Descriptions

- **INSTANCE_UUID** – This is unique for each KVM instance created by OpenStack.
- **EVENT** – Event corresponds to the type of action performed on an OpenStack instance, such as Create, Stop, Start, Delete etc.
- **START_TIME** `(yyyy-MM-dd HH:mm:ss.SSS)` – This field identifies the time when a related event started executing, such as when an instance creation started or an instance deletion operation started.
- **START_SEC** – Time difference, in seconds, between the recorded time of the first event and the start of the current event.
- **FINISH_TIME** `(yyyy-MM-dd HH:mm:ss.SSS)` – This field identifies the time when a related event completed.
- **FINISH_SEC** – Time difference, in seconds, between the recorded time of the first event and the finish time of the current event.
- **EVENT_DURATION** – This is the required time, in seconds, for each action event, i.e. the difference between START_TIME and FINISH_TIME.
- **RESULT** – Status of each action event. If the result is not success or null, then this action event was not successfully.
- **MEMORY_MB** – Amount of RAM assigned to an instance at creation.
- **DISK_GB** – Amount of disk assigned to an instance at creation.
- **VCPUS** – Number of virtual CPUs assigned to an instance at creation.
- **INSTANCE_NAME** – This is the name provided by the user while creating the VM. This name is not unique. Many instances can have the same instance name.
- **USER_ID** – The user identifier of the account from which the VM was created.
- **PROJECT_ID** – The project identifier of the account from which the VM was created.
- **HOST_NAME (PHYSICAL)** – Name of the physical computer hosting the KVM instance.