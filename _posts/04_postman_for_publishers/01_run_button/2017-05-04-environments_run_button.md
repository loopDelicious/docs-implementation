---
categories:
  - "postman_for_publishers"
  - "run_button"
title: "Environments in Run in Postman"
page_id: "environments_run_button"
warning: false
redirect_from:
  - /docs/env_run_button
---

There are 2 ways to include an environment with the shared collection using the Run in Postman button.

### While generating the embed code

![select environment](https://www.getpostman.com/img/v2/docs/environments/share_select_env.png)

Select the environment name from the dropdown, as shown in the screenshot above. The environment is now embedded within the generated HTML/Markdown and will be imported when your user clicks the button.

### On page load using Run in Postman’s JavaScript API

Postman also provides an API to programmatically generate an environment client-side.

```javascript
_pm('env.create', 'Spotify', {
  user_id: 'spotifyuser',
  authorization: 'Bearer 1234xyzd'
});
```

A possible application for this would be to pass your signed in user’s access credentials to Postman, as illustrated in the example above.

Note that this method works only with the CSS button, and not the Markdown button. The `_pm()` method can be used anywhere on the page, after the embedded script tag.
