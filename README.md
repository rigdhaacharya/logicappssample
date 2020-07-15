## Sample Logic Apps
This repository contains few sample logic apps for registering and monitoring users.

Logic Apps are a great integration platform and are very useful for quick POCs and for integrating steps across multiple data sources / applications.

They can also be used for automating business processes, especially the ones that require semi-manual steps for approvals etc.

While they're not suited for complex conditional logic, we can set them up for some conditions and iterations.

## Demo Files

### Register Users
This is the simplest logic App. It has an HTTP trigger and registers the users specified in the payload to an Azure table.

Here's a sample JSON payload for running this LogicApps. The logic app runs 1 instance per request and we loop through the users using a simple for-each loop.

```json
{
  "users": [
    {
      "userName": "paidUser1",
      "firstName": "foo",
      "lastName": "bar",
      "billingTier":"paid"
    },
    {
      "userName": "paidUser2",
      "firstName": "foo3",
      "lastName": "bar",
      "billingTier":"paid"
    }
  ]
}
```
### Register Users Split On
This is a slight modification to the above logic app where we split the request and create multiple instances of the logic app to process each user.

```json
{
  "users": [
    {
      "userName": "paidUser1",
      "firstName": "foo",
      "lastName": "bar",
      "billingTier":"paid"
    },
    {
      "userName": "paidUser2",
      "firstName": "foo3",
      "lastName": "bar",
      "billingTier":"paid"
    }
  ]
}
```
