---
title: AudioBuffer.length
slug: Web/API/AudioBuffer/length
page-type: web-api-instance-property
tags:
  - API
  - AudioBuffer
  - Property
  - Reference
  - Web Audio API
  - length
browser-compat: api.AudioBuffer.length
---

{{ APIRef("Web Audio API") }}

The **`length`** property of the {{ domxref("AudioBuffer") }}
interface returns an integer representing the length, in sample-frames, of the PCM data
stored in the buffer.

## Value

An integer.

## Examples

```js
// Stereo
const channels = 2;

// Create an empty two second stereo buffer at the
// sample rate of the AudioContext
const frameCount = audioCtx.sampleRate * 2.0;
const myArrayBuffer = audioCtx.createBuffer(2, frameCount, audioCtx.sampleRate);

button.onclick = () => {
  // Fill the buffer with white noise;
  // just random values between -1.0 and 1.0
  for (let channel = 0; channel < channels; channel++) {
    // This gives us the actual ArrayBuffer that contains the data
    const nowBuffering = myArrayBuffer.getChannelData(channel);
    for (let i = 0; i < frameCount; i++) {
      // Math.random() is in [0; 1.0]
      // audio needs to be in [-1.0; 1.0]
      nowBuffering[i] = Math.random() * 2 - 1;
    }
  }

  console.log(myArrayBuffer.length);
}
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Using the Web Audio API](/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API)
