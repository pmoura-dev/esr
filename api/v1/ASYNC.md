# ESR Service 1.0.0 documentation

Async API for the ESR Service.

## Table of Contents

* [Operations](#operations)
  * [RECEIVE esr/v1/entities/{entity_id}/reports/state](#receive-esrv1entitiesentity_idreportsstate-operation)
  * [RECEIVE esr/v1/entities/{entity_id}/reports/telemetry](#receive-esrv1entitiesentity_idreportstelemetry-operation)
  * [SEND esr/v1/entities/{entity_id}/commands/update_state](#send-esrv1entitiesentity_idcommandsupdate_state-operation)
  * [SEND esr/v1/entities/{entity_id}/events/state_updated](#send-esrv1entitiesentity_ideventsstate_updated-operation)
  * [SEND esr/v1/entities/{entity_id}/events/telemetry_reported](#send-esrv1entitiesentity_ideventstelemetry_reported-operation)
  * [SEND esr/v1/commands/{command_id}/result](#send-esrv1commandscommand_idresult-operation)

## Operations

### RECEIVE `esr/v1/entities/{entity_id}/reports/state` Operation

* Operation ID: `receiveEntitiesReportsState`

#### Parameters

| Name | Type | Description | Value | Constraints | Notes |
|---|---|---|---|---|---|
| entity_id | string | The ID of the entity. | - | - | **required** |


#### Message `StateReport`

##### Payload

| Name | Type | Description | Value | Constraints | Notes |
|---|---|---|---|---|---|
| (root) | object | - | - | - | **additional properties are allowed** |
| state | object | Current state of the entity. | - | - | **additional properties are allowed** |
| timestamp | string | Timestamp of the state report. | - | format (`date-time`) | - |

> Examples of payload _(generated)_

```json
{
  "state": {},
  "timestamp": "2019-08-24T14:15:22Z"
}
```



### RECEIVE `esr/v1/entities/{entity_id}/reports/telemetry` Operation

* Operation ID: `receiveEntitiesReportsTelemetry`

#### Parameters

| Name | Type | Description | Value | Constraints | Notes |
|---|---|---|---|---|---|
| entity_id | string | The ID of the entity. | - | - | **required** |


#### Message `TelemetryReport`

##### Payload

| Name | Type | Description | Value | Constraints | Notes |
|---|---|---|---|---|---|
| (root) | object | - | - | - | **additional properties are allowed** |
| metrics | object | Metrics values reported by the entity. | - | - | **additional properties are allowed** |
| timestamp | string | Timestamp of the telemetry report. | - | format (`date-time`) | - |

> Examples of payload _(generated)_

```json
{
  "metrics": {},
  "timestamp": "2019-08-24T14:15:22Z"
}
```



### SEND `esr/v1/entities/{entity_id}/commands/update_state` Operation

* Operation ID: `sendEntitiesCommandsUpdateState`

#### Parameters

| Name | Type | Description | Value | Constraints | Notes |
|---|---|---|---|---|---|
| entity_id | string | The ID of the entity. | - | - | **required** |


#### Message `CommandUpdateState`

##### Payload

| Name | Type | Description | Value | Constraints | Notes |
|---|---|---|---|---|---|
| (root) | object | - | - | - | **additional properties are allowed** |
| state | object | Desired state properties to update. | - | - | **additional properties are allowed** |

> Examples of payload _(generated)_

```json
{
  "state": {}
}
```



### SEND `esr/v1/entities/{entity_id}/events/state_updated` Operation

* Operation ID: `sendEntitiesEventsStateUpdated`

#### Parameters

| Name | Type | Description | Value | Constraints | Notes |
|---|---|---|---|---|---|
| entity_id | string | The ID of the entity. | - | - | **required** |


#### Message `StateReport`

##### Payload

| Name | Type | Description | Value | Constraints | Notes |
|---|---|---|---|---|---|
| (root) | object | - | - | - | **additional properties are allowed** |
| state | object | Current state of the entity. | - | - | **additional properties are allowed** |
| timestamp | string | Timestamp of the state report. | - | format (`date-time`) | - |

> Examples of payload _(generated)_

```json
{
  "state": {},
  "timestamp": "2019-08-24T14:15:22Z"
}
```



### SEND `esr/v1/entities/{entity_id}/events/telemetry_reported` Operation

* Operation ID: `sendEntitiesEventsTelemetryReported`

#### Parameters

| Name | Type | Description | Value | Constraints | Notes |
|---|---|---|---|---|---|
| entity_id | string | The ID of the entity. | - | - | **required** |


#### Message `TelemetryReport`

##### Payload

| Name | Type | Description | Value | Constraints | Notes |
|---|---|---|---|---|---|
| (root) | object | - | - | - | **additional properties are allowed** |
| metrics | object | Metrics values reported by the entity. | - | - | **additional properties are allowed** |
| timestamp | string | Timestamp of the telemetry report. | - | format (`date-time`) | - |

> Examples of payload _(generated)_

```json
{
  "metrics": {},
  "timestamp": "2019-08-24T14:15:22Z"
}
```



### SEND `esr/v1/commands/{command_id}/result` Operation

* Operation ID: `sendCommandsResult`

#### Parameters

| Name | Type | Description | Value | Constraints | Notes |
|---|---|---|---|---|---|
| command_id | string | The ID of the command. | - | - | **required** |


#### Message `CommandResult`

##### Payload

| Name | Type | Description | Value | Constraints | Notes |
|---|---|---|---|---|---|
| (root) | object | - | - | - | **additional properties are allowed** |
| status | string | Status of the command | allowed (`"success"`, `"failed"`) | - | - |

> Examples of payload _(generated)_

```json
{
  "status": "success"
}
```



