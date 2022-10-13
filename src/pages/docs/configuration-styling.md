---
title: Styling
description: Customize the look and feel of your integration.
---

Customize the look and feel of your integration fine-tuned for your audience.

---

## Customizing styling

For customizing colors and styles, we allow you to inject custom CSS for each element in the configuration using the styles property.

This property represents an object where each property is the property name of an element and the value is in React.js's CSS-in-JS format. An example and tables of styleable elements and their property names are below.



{% callout title="You should know!" %}
Note: since the Beset API runs in a shadow DOM, CSS variables defined in your site's DOM cannot be used in the Speechify API since they will be out of scope.
{% /callout %}

### Example

Here's a quick example that makes the background color of the play button represented by `playButton` a shade of light green and the playback position dot represented by `playbackPosition` to orange:

```js
<script type="module">
      import('https://beset-js.s3.amazonaws.com/BesetJS.es.js').then(async ({BesetWidget}) => {
          const widget = new BesetWidget({
            publicKey: "YOUR_API_KEY",
            inlinePlayerElement: document.getElementById("target-dom_element")
            customStyles: {
              playButton: {
                backgroundColor: "#25a43a",
              },
              playbackPosition: {
                backgroundColor: "#dc8326",
              }
            }
          })
          await widget.mount();
      })
</script>
```


### Customizable Elements

{% table %}
* Element name
* Property name
---
* Play button
* `playButton`
---
* Playback position dot
* `playbackPosition`
---
* widget container
* `widget`
{% /table %}

