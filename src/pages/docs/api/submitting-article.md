---
title: Send article via API
description: Create a transcription job via the API
---

Create transcriptions via our API.

---

## Creating a transcription 

The transcribe api reachable via the `beset/transcribe/v1/article` requires 3 variables an `article_uri`, `main_content`, and `headline_content`. For submitting a transcription job we also require your private api key instead of your public api key.

{% table %}
* Property name
* Meaning
* type
---
* article_uri
* Where this resource can be found or an artificial uri for you to be able to find and identify it.
* string
---
* main_content
* The bulk of the transcription, the main article content
* string
---
* headline_content
* The headline that will intro the main content, if an empty string it will be ignored.
* string
---
{% /table %}

## Example Request
```js

requests.post("beset/transcribe/v1/article" ,{
  // Content url or Some unique uri for it"
  article_uri: "testpage.app/look-at-my-blog",
  headline_content: "Did you hear about this?",
  main_content: "Beset is awesome and I'm going to tell my peers about it."
}, headers={ "X-API-KEY": "YOUR_PRIVATE_SECRET_API_KEY" })

```


