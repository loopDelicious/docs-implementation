---
categories:
  - "pro"
  - "integrations"
title: "Microsoft Flow"
page_id: "microsoft_flow"
tags: 
  - "pro"
warning: false
---

Microsoft Flow is a cloud-based service provided by Microsoft which allows you to automate workflows between your favorite apps and services to get notifications, synchronize files, collect data, and more. It has over 140 services listed with predefined flows as well that you can start using directly.

We offer a number of ways through which you can connect your Postman account with Microsoft Flow.

### Monitor Run Results to Microsoft Flow

Postman Monitors allows you to run your collections on a schedule without any manual intervention. With the Microsoft Flow integration, you have the freedom to use those results in whatever way possible and connect to any service available.

### Team and Collection Activity Feed

The activity feed is the place where you can see all the changes that are happening to your collections and within the team. It is the place where you can track any updates made to your APIs and monitor what all is happening within the team. Integrating with Flow gives you the freedom to connect email services like Outlook, Gmail or even the custom SMTP service, or you can use Twilio to get the feed as a text message.

### Backup Collections

Collections are a very important part of Postman so it is necessary to have a backup a backup of them. Microsoft Flow gives you the ability to connect your collection with a service like Box, which is a cloud based storage solution, or you can even connect to your custom DB2 instance and store your collections there.

### Fetch the webhook URL from Microsoft Flow

Log in to [Microsoft Flow](https://flow.microsoft.com/), and go to `My Flows`. Select `Create from Blank` in the top-right corner. 

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/58858272.png)  

To add the first step, type `request` in the search bar, and select `Request / Response - Request` from the `Triggers` list.

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/58858278.png)  

For different types of integrations, the JSON schema varies. Based on the type of integration, the schemas are mentioned below.

##### Monitor Run Results

```
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "definitions": {},
  "id": "http://example.com/example.json",
  "properties": {
    "collection_name": {
      "id": "/properties/collection_name",
      "type": "string"
    },
    "collection_uid": {
      "id": "/properties/collection_uid",
      "type": "string"
    },
    "environment_name": {
      "id": "/properties/environment_name",
      "type": "string"
    },
    "environment_uid": {
      "id": "/properties/environment_uid",
      "type": "string"
    },
    "metrics": {
      "id": "/properties/metrics",
      "properties": {
        "errors": 
          "id": "/properties/metrics/properties/errors",
          "type": "integer"
        },
        "failedTests": {
          "id": "/properties/metrics/properties/failedTests",
          "type": "integer"
        },
        "passedTests": {
          "id": "/properties/metrics/properties/passedTests",
          "type": "integer"
        },
        "requestCount": {
          "id": "/properties/metrics/properties/requestCount",
          "type": "integer"
        },
        "totalLatency": {
          "id": "/properties/metrics/properties/totalLatency",
          "type": "integer"
        },
        "warnings": {
          "id": "/properties/metrics/properties/warnings",
          "type": "integer"
        }
      },
      "type": "object"
    },
    "monitor_name": {
      "id": "/properties/monitor_name",
      "type": "string"
    },
    "monitor_uid": {
      "id": "/properties/monitor_uid",
      "type": "string"
    },
    "user_id": {
      "id": "/properties/user_id",
      "type": "string"
    },
    "user_name": {
      "id": "/properties/user_name",
      "type": "string"
    }
  },
  "type": "object"
}
```

[https://gist.github.com/ankitjaggi/e1677fd463df2d2142f138a0d44d630d](https://gist.github.com/ankitjaggi/e1677fd463df2d2142f138a0d44d630d)

### Collection and Team Activity Feed

```
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "definitions": {},
  "id": "http://example.com/example.json",
  "properties": {
    "action": {
      "id": "/properties/action",
      "type": "string"
    },
    "collection_name": {
      "id": "/properties/collection_name",
      "type": "string"
    },
    "collection_uid": {
      "id": "/properties/collection_uid",
      "type": "string"
    },
    "message": {
      "id": "/properties/message",
      "type": "string"
    },
    "model": {
      "id": "/properties/model",
      "type": "string"
    },
    "model_name": {
      "id": "/properties/model_name",
      "type": "string"
    },
    "model_uid": {
      "id": "/properties/model_uid",
      "type": "string"
    },
    "user_id": {
      "id": "/properties/user_id",
      "type": "string"
    },
    "user_name": {
      "id": "/properties/user_name",
      "type": "string"
    }
  },
  "type": "object"
}
```

[https://gist.github.com/ankitjaggi/b4d90f72c9fdd41dd2e4e0421eca249f](https://gist.github.com/ankitjaggi/b4d90f72c9fdd41dd2e4e0421eca249f)

### Backup Collections

```
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "definitions": {},
  "id": "http://example.com/example.json",
  "properties": {
    "collection": {
      "id": "/properties/collection",
      "properties": {},
      "type": "object"
    }
  },
  "type": "object"
}
```

[https://gist.github.com/ankitjaggi/7ebe8208fe520739e3ab931ffc6c54a7](https://gist.github.com/ankitjaggi/7ebe8208fe520739e3ab931ffc6c54a7)

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/58858289.png)

Once that is done, click on `New Step → Add an Action` and configure your specific service. For this demo, let's connect your Postman Monitor to the Microsoft Flow mobile app. So, on every Monitor Run, you will receive an in-app notification in the Microsoft Flow mobile app. Select `Notifications` from the list of services, and choose the `Send me a mobile notification` action.

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/58858298.png)

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/58858309.png)  

You can enter you own text that you want to be displayed and also use the content that will be sent by the Postman Monitors.

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/58858318.png)  

Once this is done, click on `Create Flow` on the top-right corner. Once your flow has been created, you will be needing the webhook URL generated by Flow. To obtain that, click on the `Request` trigger and you will find your generated webhook URL.

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/58858329.png)

### Configure Postman Integrations

Head over to [Postman Integrations](https://app.getpostman.com/dashboard/integrations) and select the Microsoft Flow Integration. Select the Monitor Run Results Integration.

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/58858339.png)

Enter the webhook URL you generated from Microsoft Flow and select the Monitor. Additionally, you can also configure how frequently you want to be notified about the monitor run.

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/58858349.png)

And you're done! Your Integration has been setup successfully. So, now whenever a monitor would run, you would get a notification something like this on your Flow mobile app.

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/58858362.png)
