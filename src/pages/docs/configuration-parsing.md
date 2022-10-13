---
title: Content & Parsing
description: Control how content is processed and parsed for transcription
---

All textual content has its specifc contexts that uses its own abbreviations, acronyms, and idioms. So you should be able to make sure our solution is meeting your needs to the fullest extent. To better handle this we automatically handle most needs like abbreviations and commonly found acronyms, but sometimes for specific publications a little more control is needed on both the raw Html be processed before consumption and post-processing after the text has been extracted. We offer both methods for maximum flexibility.

---

## Setting the target content

If you want to control what content is read for that page you can set the `contentElement` property on the plugin. Allowing full control over what needs to be transcribed in the document. You can also set the content headline to be said at the beginning of the article via the `contentHeadlineElement`.

## Controlling the pre-processing html

You may provide an array of handler functions via the `processElements` to handle the the html which will be called after the DOM has loaded. This will be a raw HTML Element from there the text is extracted and sent to post-processing. You can also ignore elements which will be ignore in the content via the `ignoreElements`

## Handling post-processing

Post-processing is after the text has been extract from the html and there's changes that need to be made such as replacing words or acronyms. You can set the `processText` property to a function or array of functions.

{% callout title="Doing post-processing through Beset" %}
You can handle simple replacements through our lexicons which allows sinple replacements our the Beset side of things protecting your application from bad client side code.
{% /callout %}

```js
<script type="module">
      import('https://beset-js.s3.amazonaws.com/BesetJS.es.js').then(async ({BesetWidget}) => {
          const widget = new BesetWidget({
            // ...
            // Set content targets
            contentElement: document.getElementById("article"),
            contentHeadlineElement: document.getElementById("headline"),
            // Pre-processing - Ignore elements
            ignoreElements: (element: HTMLElement): boolean => {
              return element.classList.contains("code-example")
            },
            // Post-Processing - Replace words
            processText: (textCorpus: string): string => {
              return string.replace('ostrich', 'dog')
            }
          })
          await widget.mount();
      })
</script>
```
