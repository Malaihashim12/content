---
title: "ServiceWorkerGlobalScope: canmakepayment event"
short-title: canmakepayment
slug: Web/API/ServiceWorkerGlobalScope/canmakepayment_event
page-type: web-api-event
status:
  - experimental
browser-compat: api.ServiceWorkerGlobalScope.canmakepayment_event
---

{{APIRef("Payment Handler API")}}{{SeeCompatTable}}{{SecureContext_Header}}{{AvailableInWorkers("service")}}

The **`canmakepayment`** event of the {{domxref("ServiceWorkerGlobalScope")}} interface is fired on a payment app's service worker to check whether it is ready to handle a payment. Specifically, it is fired when the merchant website calls the {{domxref("PaymentRequest.PaymentRequest", "PaymentRequest()")}} constructor.

## Syntax

Use the event name in methods like {{domxref("EventTarget.addEventListener", "addEventListener()")}}, or set an event handler property.

```js-nolint
addEventListener("canmakepayment", (event) => { })

oncanmakepayment = (event) => { }
```

## Event type

A {{domxref("CanMakePaymentEvent")}}. Inherits from {{domxref("ExtendableEvent")}}.

{{InheritanceDiagram("CanMakePaymentEvent")}}

## Examples

The `canmakepayment` event is fired on a payment app's service worker to check whether it is ready to handle a payment. Specifically, it is fired when the merchant website calls the {{domxref("PaymentRequest.PaymentRequest", "PaymentRequest()")}} constructor. The service worker can then use the {{domxref("CanMakePaymentEvent.respondWith()")}} method to respond appropriately:

```js
self.addEventListener("canmakepayment", (e) => {
  e.respondWith(
    new Promise((resolve, reject) => {
      someAppSpecificLogic()
        .then((result) => {
          resolve(result);
        })
        .catch((error) => {
          reject(error);
        });
    }),
  );
});
```

`respondWith()` returns a {{jsxref("Promise")}} that resolves with a boolean value to signal that the service worker is ready to handle a payment request (`true`), or not (`false`).

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("Payment Handler API", "Payment Handler API", "", "nocode")}}
- [Web-based payment apps overview](https://web.dev/articles/web-based-payment-apps-overview)
- [Setting up a payment method](https://web.dev/articles/setting-up-a-payment-method)
- [Life of a payment transaction](https://web.dev/articles/life-of-a-payment-transaction)
- [Using the Payment Request API](/en-US/docs/Web/API/Payment_Request_API/Using_the_Payment_Request_API)
- [Payment processing concepts](/en-US/docs/Web/API/Payment_Request_API/Concepts)
