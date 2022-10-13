---
title: Getting started
pageTitle: Beset - A sound for any text
description: Versatile Text to Speech for anyone
---

Learn how to get Beset set up in your project in under five minutes or it's free. {% .lead %}

{% quick-links %}

{% quick-link title="Installation" icon="installation" href="/docs/installation" description="Step-by-step guides to setting up your system and installing the library." /%}

{% quick-link title="Customization" icon="plugins" href="/docs/configuration-styling" description="Customize your plugin with ease." /%}

{% quick-link title="Content Control" icon="presets" href="/docs/configuration-parsing" description="Control your content via our processing api" /%}

{% quick-link title="API reference" icon="theming" href="/docs/api/submitting-article" description="Learn how to submit transcription jobs from your servers." /%}

{% /quick-links %}

---

## Quick start

Installing Beset is as simple import which instantiates an floating player that will auto-detect the content on the page using the html.

```js
<script type="module">
      import('https://beset-js.s3.amazonaws.com/BesetJS.es.js').then(async ({BesetWidget}) => {
          const widget = new BesetWidget({
            publicKey: "YOUR_API_KEY",
            inlinePlayerElement: document.getElementById("target-dom_element")
          })
          await widget.mount();
      })
</script>
```

### Configuring the library

Configuration is simple you can pass a bunch of configuration options for styling and detecting events like below. Read about it in the [Configuration section](/docs/configuration) 

```js
<script type="module">
      import('https://beset-js.s3.amazonaws.com/BesetJS.es.js').then(async ({BesetWidget}) => {
          const widget = new BesetWidget({
            // ...
            handlers: {
              onPlay: () => { /** your code */ }
            }
            notifiers: {
              onStartPlayback: () => { /** your code */ }
            }
          })
          await widget.mount();
      })
</script>
```

## Getting help

The Beset team is here to make sure you succeed and can get your issues solved ASAP! If you're having any problems at all don't be afraid to reach out
[our support team](mailto:support@beset.io). We promise the feedback will be speedy!

### Submit an issue

Found a bug or need more functionality? Submit a ticket by email to [our support staff](mailto:support@beset.io).
