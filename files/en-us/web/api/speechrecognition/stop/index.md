---
title: SpeechRecognition.stop()
slug: Web/API/SpeechRecognition/stop
tags:
  - API
  - Method
  - Reference
  - SpeechRecognition
  - Web Speech API
  - recognition
  - speech
  - stop
browser-compat: api.SpeechRecognition.stop
---
{{APIRef("Web Speech API")}}

The **`stop()`** method of the [Web Speech API](/en-US/docs/Web/API/Web_Speech_API) stops the speech
recognition service from listening to incoming audio, and attempts to return a
{{domxref("SpeechRecognitionResult")}} using the audio captured so far.

## Syntax

```js
stop()
```

### Return value

{{jsxref('undefined')}}.

### Parameters

None.

## Examples

```js
var grammar = '#JSGF V1.0; grammar colors; public <color> = aqua | azure | beige | bisque | black | blue | brown | chocolate | coral | crimson | cyan | fuchsia | ghostwhite | gold | goldenrod | gray | green | indigo | ivory | khaki | lavender | lime | linen | magenta | maroon | moccasin | navy | olive | orange | orchid | peru | pink | plum | purple | red | salmon | sienna | silver | snow | tan | teal | thistle | tomato | turquoise | violet | white | yellow ;'
var recognition = new SpeechRecognition();
var speechRecognitionList = new SpeechGrammarList();
speechRecognitionList.addFromString(grammar, 1);
recognition.grammars = speechRecognitionList;

var diagnostic = document.querySelector('.output');
var bg = document.querySelector('html');

document.body.onclick = function() {
  recognition.start();
  console.log('Ready to receive a color command.');
}

abortBtn.onclick = function() {
  recognition.abort();
  console.log('Speech recognition aborted.');
}

recognition.onspeechend = function() {
  recognition.stop();
  console.log('Speech recognition has stopped.');
}
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Web Speech API](/en-US/docs/Web/API/Web_Speech_API)
