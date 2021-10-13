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

## Contributing

We welcome contributions. Please check out the contribution and code of conduct guidelines first.

To contribute:

1. Fork the project
2. Create a feature branch (`git checkout -b feature/mynewfeature`)
3. Commit your changes (`git commit -m 'Add mynewfeature'`)
4. Push to the branch (`git push origin feature/mynewfeature`)
5. Open a pull request
