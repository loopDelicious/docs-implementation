---
categories:
  - "postman"
  - "collection_runs"
title: "Running multiple iterations"
page_id: "running_multiple_iterations"
warning: false
---

##### Download the collection used in this example:

   * [collection.json](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/59037885.json)

The iterations of a collection run reflect how many times the collection will run. Here we have a collection that is run with 5 iterations.

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/59039044.png)![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/59039058.png)

### Switching between iterations

To quickly jump between iterations, you can click on one of the numbers on the right sidebar, each of which represents one iteration.

### Using green and red filters

The left sidebar contains three filters, which can be used to show all, passed, or failed tests. This is super useful when trying to look for tests that failed so that you can quickly find bugs in your API.

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/59039741.png)

### Debugging with multiple iterations

When working with multiple iterations, it can quickly become tedious to switch between them to check if everything worked as you'd expect. For this reason, there's a third screen in the collection runner, which is the **Run Summary** screen. When a run is finished (or stopped), you can open up the **Run Summary** screen by hitting the orange button that says `Run Summary`.

![](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/59039072.png)

This screen is, as the name suggests, an overview of your run. Here, you can see each request, and its pass/fail status as a timeline. A request is treated as `Passed` if all tests inside it pass. Similarly, if one or more tests fail, the request is marked as `Failed`.

The numbers in the header represent the iteration you are working with. It becomes very easy to pinpoint the test that is misbehaving. Clicking on an iteration in the header will take you to that iteration, so you can further investigate what might be going wrong. Read more about [debugging collection runs](/docs/postman/collection_runs/debugging_a_collection_run).
