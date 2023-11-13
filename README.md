<div align="center">
<img src="https://cdn.dimescheduler.com/dime-scheduler/v2/logo.svg" height="100px" />
</div>

<p align="center">
    <img src="assets/connector.svg?raw=true" height=250>
</p>

<p align="center">
  <a href="https://docs.dimescheduler.com">Documentation</a> |
  <a href="https://docs.dimescheduler.com/history">Changelog</a> |
  <a href="https://docs.dimescheduler.com/roadmap">Roadmap</a>
</p>

<div align="center">
<img src="https://img.shields.io/badge/license-MIT-brightgreen?style=flat-square" />
</div>
<h1 align="center">⚡Power Platform Connector ⚡</h1>

Connect to Dime.Scheduler through a PowerApps custom connector.

## Getting started

### Creating the custom connector

In the src directory, run the following [paconn](https://docs.microsoft.com/en-us/connectors/custom-connectors/paconn-cli) command:

```cmd
paconn create --api-prop apiProperties.json --api-def apiDefinition.swagger.json --icon icon.png
```

If the connector already exists, you may want to run this command:

```cmd
paconn update --api-prop apiProperties.json --api-def apiDefinition.swagger.json --icon icon.png
```

Follow the instructions in the terminal. You'll need to select an environment, and when updating a connector, select the connector to overwrite the changes.

> You may have to login, which you can do by running `paconn login` and follow the instructions in the terminal.

To validate the OpenAPI definition, run the following command in the src directory:

```cmd
paconn validate --api-def apiDefinition.swagger.json
```

### Creating a connection

When the connector has been added to your environment, you should create a connection. These variables are essential to the succesful integration between the Power Platform and Dime.Scheduler:

<img src="assets/connection.png?raw=true" height="250px">

| Parameter      | Value                                                                                                                                                                                                                                            |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Environment    | The Dime.Scheduler environment                                                                                                                                                                                                                   |
| API Key        | this is the key of the subscription that allows you to use Dime.Scheduler's connect hub. You can register [here](https://connect.dimescheduler.com). Once enrolled, navigate to your user profile and copy the primary key of your subscription. |

### Using the connector

The connector can be used in any PowerApp or Flow. The connector will be available under the "Custom" section.

<img src="assets/flow.png?raw=true" height="250px">

## Development

Adding an action is done by simple OpenAPI management through the `apiDefinition.swagger.json` file in the src directory:

```json
"/timeMarker": {
  "post": {
    "summary": "Add, update or remove a time marker",
    "description": "Add, update or remove a time marker.",
    "operationId": "Timemarker",
    "tags": ["indicator"],
    "parameters": [
      {
        "name": "timeMarker",
        "in": "body",
        "schema": {
          "$ref": "#/definitions/timeMarker"
        },
        "description": "JSON request body containing the contents of the requested entity to be imported."
      }
    ],
    "consumes": ["application/json"],
    "produces": ["application/json"],
    "responses": {
      "200": {
        "$ref": "#/responses/200"
      },
      "400": {
        "$ref": "#/responses/400"
      },
      "500": {
        "$ref": "#/responses/500"
      },
      "default": {
        "$ref": "#/responses/default"
      }
    }
  }
},
```

For starters, copy, paste and modify the following metadata:

- Summary
- Description
- Operation ID

Next is the endpoint of the Azure function that you'll need to specify. The naming convention is `Entity`. Finally, you'll need to specify the entity type in the body.

## Contributing

We welcome contributions. Please check out the contribution and code of conduct guidelines first.
