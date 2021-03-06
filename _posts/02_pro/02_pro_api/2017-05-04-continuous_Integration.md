---
categories:
  - "pro"
  - "pro_api"
title: "Continuous Integration"
page_id: "continuous_integration"
tags: 
  - "pro"
warning: false
---

Let's access collections using the Postman Pro API to run inside your CI/CD environments.

Before we get started:

*   Ensure you have a CI system setup which can run shell commands and that you have access to modify the same.
*   If you don't already have a [Postman Pro API key](https://docs.api.getpostman.com/#authentication), get one now.
*   Make sure you have a Postman Collection that tests your localhost server, and note the UID of the collection.

### Step 1: Install Node

You may skip this step if your CI already has Node installed.

Follow the [steps to download Node](https://nodejs.org/en/download/package-manager/) which is specific to your CI's platform. Otherwise, some CI has configuration which simply pre-installs Node. Ensure you are using NodeJS v4 or above.

### Step 2: Install Newman

[Newman](/docs/postman/collection_runs/command_line_integration_with_newman) is a command-line tool that allows you to run a collection in your system. The following command installs Newman in your CI.

```bash
npm i newman -g;
```

### Step 3: Run Newman

Run the following Newman command with the appropriate parameters:

{% raw %}
```bash
newman run https://api.getpostman.com/collections/{{collection_uid}}?apikey={{postman-api-key-here}}
```
{% endraw %}


If you need to provide an environment to the collection, change the above command to the following:

{% raw %}
```bash
newman run https://api.getpostman.com/collections/{{collection_uid}}?apikey={{postman-api-key-here}} --environment https://api.getpostman.com/environments/{{environment_uid}}?apikey={{postman-api-key-here}}
```
{% endraw %}
