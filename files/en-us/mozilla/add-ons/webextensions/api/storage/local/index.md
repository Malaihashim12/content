---
title: storage.local
slug: Mozilla/Add-ons/WebExtensions/API/storage/local
page-type: webextension-api-property
browser-compat: webextensions.api.storage.local
sidebar: addonsidebar
---

Represents the `local` storage area. Items in `local` storage are local to the machine the extension is installed on.

The browser may restrict the amount of data that an extension can store in the local storage area. For example:

- In Chrome, an extension is limited to storing 5MB of data using this API unless it has the [`"unlimitedStorage"` permission](/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json/permissions#unlimited_storage).
- In Firefox, the amount of data an extension can store is subjected to the same [storage limits](/en-US/docs/Web/API/Storage_API/Storage_quotas_and_eviction_criteria#how_much_data_can_be_stored) as applied to IndexedDB databases. Extensions that intend to store more data than this limit need the ["unlimitedStorage"](/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json/permissions#unlimited_storage) permission. However, extensions with the "unlimitedStorage" permission may get a quota exceeded error when the disk space used by storage exceeds the global limit.

When the extension is uninstalled, its associated local storage is cleared.

Also, in Firefox, you can prevent the browser from clearing local storage on uninstall by visiting `about:config` and setting these browser preferences to `true`: `"keepUuidOnUninstall"` and `"keepStorageOnUninstall"`. This feature is provided to help developers test their extensions. Extensions themselves are not able to change these preferences.

Although this API is similar to {{domxref("Window.localStorage")}}, it is recommended that you don't use `Window.localStorage` in extension code. Firefox clears data stored by extensions using the localStorage API in various scenarios where users clear their browsing history and data for privacy reasons. Data saved using the `storage.local` API is correctly persisted in these scenarios.

## Methods

The `local` object implements the methods defined on the {{WebExtAPIRef("storage.StorageArea")}} type:

- {{WebExtAPIRef("storage.StorageArea.get()", "storage.local.get()")}}
  - : Retrieves one or more items from the storage area.
- {{WebExtAPIRef("storage.StorageArea.getBytesInUse()", "storage.local.getBytesInUse()")}}
  - : Gets the amount of storage space (in bytes) used for one or more items in the storage area.
- {{WebExtAPIRef("storage.StorageArea.getKeys()", "storage.local.getKeys()")}}
  - : Retrieves the keys of all items in the storage area.
- {{WebExtAPIRef("storage.StorageArea.set()", "storage.local.set()")}}
  - : Stores one or more items in the storage area. If the item exists, its value is updated.
- {{WebExtAPIRef("storage.StorageArea.remove()", "storage.local.remove()")}}
  - : Removes one or more items from the storage area.
- {{WebExtAPIRef("storage.StorageArea.clear()", "storage.local.clear()")}}
  - : Removes all items from the storage area.

## Events

The `local` object implements the events defined on the {{WebExtAPIRef("storage.StorageArea")}} type:

- {{WebExtAPIRef("storage.StorageArea.onChanged", "storage.local.onChanged")}}
  - : Fires when one or more items in the storage area change.

{{WebExtExamples}}

## Browser compatibility

{{Compat}}

> [!NOTE]
> This API is based on Chromium's [`chrome.storage`](https://developer.chrome.com/docs/extensions/reference/api/storage#property-local) API. This documentation is derived from [`storage.json`](https://chromium.googlesource.com/chromium/src/+/master/extensions/common/api/storage.json) in the Chromium code.

<!--
// Copyright 2015 The Chromium Authors. All rights reserved.
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
-->
