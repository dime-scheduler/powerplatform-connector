<p align="center">
    <img src="assets/connector.svg?raw=true" height=250>
</p>

</p>
<h1 align="center">Dime.Scheduler <br /> PowerApps Custom Connector</h1>

Connect to the [Dime.Scheduler Azure Function](https://github.com/dime-scheduler/azurefunctions) through a PowerApps custom connector.

## Adding an action

A simple action looks like this:

```json
"/api/timemarker": {
  "post": {
    "responses": {
      "default": {
        "description": "default",
        "schema": {}
      }
    },
    "summary": "Add or update time marker",
    "description": "Add or update time marker",
    "operationId": "crud-timemarker",
    "parameters": [
      {
        "name": "body",
        "in": "body",
        "required": false,
        "schema": {
          "type": "object",
          "properties": {
            "name": {
              "type": "string",
              "description": "name"
            },
            "color": {
              "type": "string",
              "description": "color"
            }
          }
        }
      }
    ]
  }
}
```

For starters, copy, paste and modify the following metadata:
- Summary
- Description
- Operation ID

Next is the endpoint of the Azure function that you'll need to specify. The naming convention is `api/entity`.
Finally, you'll need to specify the entity type in the body.

## Creating a custom connector

In the src directory, run the following [paconn](https://docs.microsoft.com/en-us/connectors/custom-connectors/paconn-cli) command:

```cmd
paconn create --api-prop apiProperties.json --api-def apiDefinition.swagger.json --icon icon.png
```

If the app already exists, you may want to run this command:

```cmd
paconn update --api-prop apiProperties.json --api-def apiDefinition.swagger.json
```

To validate the OpenAPI definition, run the following command in the src directory:

```cmd
paconn validate --api-def apiDefinition.swagger.json
```

## Contributing

We welcome contributions. Please check out the contribution and code of conduct guidelines first.

To contribute:

1. Fork the project
2. Create a feature branch (`git checkout -b feature/mynewfeature`)
3. Commit your changes (`git commit -m 'Add mynewfeature'`)
4. Push to the branch (`git push origin feature/mynewfeature`)
5. Open a pull request
