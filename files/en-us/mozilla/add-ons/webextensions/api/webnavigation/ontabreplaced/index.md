---
title: webNavigation.onTabReplaced
slug: Mozilla/Add-ons/WebExtensions/API/webNavigation/onTabReplaced
tags:
  - API
  - Add-ons
  - Event
  - Extensions
  - Non-standard
  - Reference
  - WebExtensions
  - onTabReplaced
  - webNavigation
browser-compat: webextensions.api.webNavigation.onTabReplaced
---
{{AddonSidebar()}}

Fired when the contents of the tab is replaced by a different (usually previously pre-rendered) tab.

## Syntax

```js
browser.webNavigation.onTabReplaced.addListener(
  listener,                   // function
  filter                      // optional object
);
browser.webNavigation.onTabReplaced.removeListener(listener)
browser.webNavigation.onTabReplaced.hasListener(listener)
```

Events have three functions:

- `addListener(callback)`
  - : Adds a listener to this event.
- `removeListener(listener)`
  - : Stop listening to this event. The `listener` argument is the listener to remove.
- `hasListener(listener)`
  - : Check whether `listener` is registered for this event. Returns `true` if it is listening, `false` otherwise.

## addListener syntax

### Parameters

- `callback`

  - : Function that will be called when this event occurs. The function will be passed the following arguments:

    - `details`
      - : [`object`](#details).

## Additional objects

### details

- `replacedTabId`
  - : `integer`. The ID of the tab that was replaced.
- `tabId`
  - : `integer`. The ID of the tab that replaced the old tab.
- `timeStamp`
  - : `number`. The time when the replacement happened, in [milliseconds since the epoch](https://en.wikipedia.org/wiki/Unix_time).

## Browser compatibility

{{Compat}}

## Examples

```js
function logOnTabReplaced(details) {
  console.log(`onTabReplaced ${details}`);
}

browser.webNavigation.onTabReplaced.addListener(logOnTabReplaced);
```

{{WebExtExamples}}

> **Note:** This API is based on Chromium's [`chrome.webNavigation`](https://developer.chrome.com/extensions/webNavigation#event-onTabReplaced) API. This documentation is derived from [`web_navigation.json`](https://chromium.googlesource.com/chromium/src/+/master/chrome/common/extensions/api/web_navigation.json) in the Chromium code.
>
> Microsoft Edge compatibility data is supplied by Microsoft Corporation and is included here under the Creative Commons Attribution 3.0 United States License.

<div class="hidden"><pre>// Copyright 2015 The Chromium Authors. All rights reserved.
//
// Redistribution and use in source and binary forms, with or without
// modification, are permitted provided that the following conditions are
// met:
//
//    * Redistributions of source code must retain the above copyright
// notice, this list of conditions and the following disclaimer.
//    * Redistributions in binary form must reproduce the above
// copyright notice, this list of conditions and the following disclaimer
// in the documentation and/or other materials provided with the
// distribution.
//    * Neither the name of Google Inc. nor the names of its
// contributors may be used to endorse or promote products derived from
// this software without specific prior written permission.
//
// THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
// "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
// LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
// A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
// OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
// SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
// LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
// DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
// THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
// (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
// OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
</pre></div>