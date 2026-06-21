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
