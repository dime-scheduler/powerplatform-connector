![Dime.Scheduler](https://cdn.dimescheduler.com/dime-scheduler/Dime.Scheduler-Black.png)

# Dime.Scheduler Connector

Dime.Scheduler, a Dime Software product, is a resource and project planning solution for the Microsoft Dynamics product suite.

## Prerequisites

In order to use the connector, you'll need:

- A Microsoft Power Apps or Power Automate plan with custom connector feature
- A running instance of Dime.Scheduler on-premise or in the cloud, and must be accessible by the app that uses this connector.

## Supported operations

The custom connector provides all the capabilities that the Dime.Scheduler SDK and the Dime.Scheduler Azure Functions expose.
The following entities can be managed through the custom connector:

| Entity               | Create/Update | Delete |
| -------------------- | ------------- | ------ |
| Action URI           | ✅            | ✅     |
| Appointment          | ✅            | ✅     |
| Assignment           | ✅            | ✅     |
| Caption              | ✅            | ✅     |
| Category             | ✅            | ✅     |
| Time marker          | ✅            | ✅     |
| Pin                  | ✅            | ✅     |
| Filter Group         | ✅            | ✅     |
| Filter Value         | ✅            | ✅     |
| Job                  | ✅            | ✅     |
| Notification         | ✅            | ✅     |
| Resource             | ✅            | ✅     |
| Task                 | ✅            | ✅     |

The following operations are supported to manipulate certain properties of the entities:

| Entity      | Property          |
| ----------- | ----------------- |
| Appointment | Category          |
| Appointment | Time marker       |
| Appointment | Importance        |
| Appointment | Locked            |
| Appointment | Olanning quantity |
| Appointment | URL               |
| Task        | Container         |
| Task        | Filter value      |
| Task        | Locked            |
| Resource    | Calendar          |
| Resource    | Capacity          |
| Resource    | Certificate       |
| Resource    | Filter Value      |
| Resource    | GPS Tracking      |
| Resource    | URL               |
