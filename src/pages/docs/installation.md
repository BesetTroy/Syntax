---
title: Installation & Setup
description: Install your plugin and setup your account
---

By the end of this walkthrough you will have setup your account, generated and API key and installed your plugin.

---

## Account setup

[Login to your account](https://beset.io/login) and navigate to your settings, where your api keys live. Click generate API Key, you will be presented with two different keys. One is your **private** key which is your personal secret that you store somewhere safe and **public** api key. This is the one you will be using for your plugin. Make sure for your newly created api_key that you set up any additional domains besides your organizational domain are assigned to that api key.

### Installation

Installing your plugin is as simple as dropping in this snippet in your website.

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

If you refresh your page your integration will appear. And Hooray like that your pages will start to be transcribed. 

### How our transcription works

We batch transcribe all your content on first load, we aim for fast transcriptions. Once transcribed your content will be available in multiple languages for a global audience. If you have any questions feel free to reach out to us!

---

[Move on to Configuration ->](/docs/configuration-basics)