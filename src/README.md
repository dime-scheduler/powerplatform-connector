![Dime.Scheduler](https://cdn.dimescheduler.com/dime-scheduler/Dime.Scheduler-Black.png)

# Dime.Scheduler

Dime.Scheduler, a Dime Software product, is a resource and project planning solution for the Microsoft Dynamics product suite.

## Prerequisites

In order to use the connector, you'll need:

- A Microsoft Power Apps or Power Automate plan with custom connector feature
- A Dime.Scheduler tenant and an API key that you can generate inside the app.

## Supported operations

The custom connector provides all the capabilities that the Dime.Scheduler SDK and the Dime.Scheduler Azure Functions expose.
The following entities can be managed through the custom connector:

| Entity       | Create/Update | Delete |
| ------------ | ------------- | ------ |
| Action URI   | ✅            | ✅     |
| Appointment  | ✅            | ✅     |
| Assignment   | ✅            | ✅     |
| Caption      | ✅            | ✅     |
| Category     | ✅            | ✅     |
| Time marker  | ✅            | ✅     |
| Pin          | ✅            | ✅     |
| Filter Group | ✅            | ✅     |
| Filter Value | ✅            | ✅     |
| Job          | ✅            | ✅     |
| Notification | ✅            | ✅     |
| Resource     | ✅            | ✅     |
| Task         | ✅            | ✅     |

The following operations are supported to manipulate certain properties of the entities:

- **Appointment**
  - Category
  - Time marker
  - Importance
  - Locked
  - Planning Quantity
  - URL
- **Task**
  - Container
  - Filter Value
  - Locked
- **Resource**
  - Container
  - Filter Value
  - Locked
  - Calendar
  - Capacity
  - Certificate
  - Filter Value
  - GPS Tracking
  - URL
