---
title: Use a Webhook
description:  A webhook integration enables uploading anything to anywhere as long as webhooks are supported.
layout: ../../layouts/MainLayout.astro
---
> This integration is part of the [Pro edition](https://kubeshark.co/pricing).

The webhook helper [`vendor.webhook`](/en/automation_helpers#vendorwebhookmethod-string-url-string-body-string) enables uploading anything to anywhere as long as webhooks are supported. It does an HTTP request to the WebHook (the HTTP endpoint) that’s defined by HTTP method and URL in the url argument with the HTTP body as the string in the body argument.

The following example calls a webhook for each health check:

```js
function onItemCaptured(data) {
  if (data.request.path === "/health")
    vendor.webhook("POST", env.WEBHOOK_URL, data);
}
```

> You can read more about the Webhook helper in the [Scripting API Reference](/en/automation_helpers) section.