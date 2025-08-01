---
title: API reference page template
slug: MDN/Writing_guidelines/Page_structures/Page_types/API_reference_page_template
page-type: mdn-writing-guide
sidebar: mdnsidebar
---

> [!NOTE]
> _Remove this whole explanatory note before publishing._
>
> ---
>
> **Page front matter:**
>
> The front matter at the top of the page is used to define "page metadata".
> The values should be updated appropriately for the particular property.
>
> ```md
> ---
> title: NameOfTheInterface
> slug: Web/API/NameOfTheInterface
> page-type: web-api-interface
> status:
>   - deprecated
>   - experimental
>   - non-standard
> browser-compat: path.to.feature.NameOfTheInterface
> ---
> ```
>
> - **title**
>   - : Title heading displayed at the top of the page. This is just the name of the interface. For example, the [Request](/en-US/docs/Web/API/Request) interface page has a _title_ of _Request_.
> - **slug**
>   - : The end of the URL path after `https://developer.mozilla.org/en-US/docs/`). This will be formatted like `Web/API/NameOfTheParentInterface`. For example, [Request](/en-US/docs/Web/API/Request) slug is "Web/API/Request".
> - **page-type**
>   - : The `page-type` key for Web/API interfaces is always `web-api-interface`.
> - **status**
>   - : Flags describing the status of this feature. An array which may contain one or more of the following: `experimental`, `deprecated`, `non-standard`. This key should not be set manually: it is set automatically based on values in the browser compatibility data for the feature. See ["How feature statuses are added or updated"](/en-US/docs/MDN/Writing_guidelines/Page_structures/Feature_status#how_feature_statuses_are_added_or_updated).
> - **browser-compat**
>   - : Replace the placeholder value `path.to.feature.NameOfTheMethod` with the query string for the method in the [Browser compat data repo](https://github.com/mdn/browser-compat-data). The toolchain automatically uses the key to populate the compatibility and specification sections (replacing the `\{{Compat}}` and `\{{Specifications}}` macros).
>
> Note that you may first need to create/update an entry for the API method in our [Browser compat data repo](https://github.com/mdn/browser-compat-data), and the entry for the API will need to include specification information.
>
> See our [guide on how to do this](/en-US/docs/MDN/Writing_guidelines/Page_structures/Compatibility_tables).
>
> ---
>
> **Top-of-page macros**
>
> A number of macro calls appear at the top of the content section (immediately below the page front matter).
>
> These macros are automatically added by the toolchain (there is no need to add/remove):
>
> - `\{{SeeCompatTable}}` — this generates a **This is an experimental technology** banner that indicates the technology is [experimental](/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental). If it is experimental, and the technology is hidden behind a pref in Firefox, you should also fill in an entry for it in the [Experimental features in Firefox](/en-US/docs/Mozilla/Firefox/Experimental_features) page.
> - `\{{Deprecated_Header}}` — this generates a **Deprecated** banner that indicates the technology is [deprecated](/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#deprecated).
> - `\{{Non-standard_Header}}` — this generates a **Non-standard** banner that indicates that the feature is not part of any specification.
>
> You should update or delete the following macros according to the advice below:
>
> - `\{{SecureContext_Header}}` — this generates a **Secure context** banner that indicates the technology is only available in a [secure context](/en-US/docs/Web/Security/Secure_Contexts). If it isn't, then you can remove the macro call. If it is, then you should also fill in an entry for it in the [Features restricted to secure contexts](/en-US/docs/Web/Security/Secure_Contexts/features_restricted_to_secure_contexts) page.
> - `\{{AvailableInWorkers}}` — this generates a **Available In Workers** note that indicates that the technology is available in [worker context](/en-US/docs/Web/API/Web_Workers_API).
>   If it is only available in window context, then you can remove the macro call.
>   If it is also available or only available in worker context, then you may also need to passing an parameter to it due to its availability (see [\\{{AvailableInWorkers}} macros source code](https://github.com/mdn/rari/blob/main/crates/rari-doc/src/templ/templs/banners.rs) for all available values), you may also need to fill in an entry for it in the [Web APIs available in workers](/en-US/docs/Web/API/Web_Workers_API/Functions_and_classes_available_to_workers#web_apis_available_in_workers) page.
> - `\{{APIRef("GroupDataName")}}` — this generates the left-hand reference sidebar showing quick reference links related to the current page. For example, every page in the [WebVR API](/en-US/docs/Web/API/WebVR_API) has the same sidebar, which points to the other pages in the API. To generate the correct sidebar for your API, you need to add a GroupData entry and include the entry's name inside the macro call in place of _GroupDataName_. See our [API reference sidebars](/en-US/docs/MDN/Writing_guidelines/Howto/Write_an_api_reference/Sidebars) guide for information on how to do this.
>
> Do not provide status header macros manually. Refer to the section ["How feature statuses are added or updated"](/en-US/docs/MDN/Writing_guidelines/Page_structures/Feature_status#how_feature_statuses_are_added_or_updated) to add these statuses to the page.
>
> Samples of the **Secure context**, **Available in workers**, **Experimental**, **Deprecated**, and **Non-standard** banners are shown right after this note block.
>
> _Remember to remove this whole explanatory note before publishing._

{{SecureContext_Header}}{{AvailableInWorkers}}{{SeeCompatTable}}{{Deprecated_Header}}{{Non-standard_Header}}

The summary paragraph — start by naming the interface, saying what API it is part of, and saying what it does. This should ideally be one or two short sentences. You could copy most of this from the Interface's summary on the corresponding API landing page.

`\{{InheritanceDiagram}}`

_To use the [domxref macro](/en-US/docs/MDN/Writing_guidelines/Page_structures/Macros/Commonly_used_macros#linking_to_pages_in_references) in the sections below, remove the backticks and backslash in the markdown file._

## Constructor

- `\{{DOMxRef("NameOfTheInterface.NameOfTheInterface", "NameOfTheInterface()")}}`
  - : Creates a new instance of the `NameOfTheInterface` object.

## Static properties

_Also inherits properties from its parent interface, `\{{DOMxRef("NameOfParentInterface")}}`._ (Note: If the interface doesn't inherit from another interface, remove this whole line.)

Include one term and definition for each property.

- `\{{DOMxRef("NameOfTheInterface.staticProperty1")}}` {{ReadOnlyInline}} {{Experimental_Inline}} {{Deprecated_Inline}} {{Non-standard_Inline}}
  - : Include a brief description of the property and what it does here. If the property is not readonly/experimental/deprecated/non-standard, remove the related macro calls.
- `\{{DOMxRef("NameOfTheInterface.staticProperty2")}}`
  - : Include a brief description of the property and what it does here. If the property is not readonly/experimental/deprecated/non-standard, remove the related macro calls.

## Instance properties

_Also inherits properties from its parent interface, `\{{DOMxRef("NameOfParentInterface")}}`._ (Note: If the interface doesn't inherit from another interface, remove this whole line.)

Include one term and definition for each property.

- `\{{DOMxRef("NameOfTheInterface.property1")}}` {{ReadOnlyInline}} {{Experimental_Inline}} {{Deprecated_Inline}} {{Non-standard_Inline}}
  - : Include a brief description of the property and what it does here. If the property is not readonly/experimental/deprecated/non-standard, remove the related macro calls.
- `\{{DOMxRef("NameOfTheInterface.property2")}}`
  - : Include a brief description of the property and what it does here. If the property is not readonly/experimental/deprecated/non-standard, remove the related macro calls.

## Static methods

_Also inherits methods from its parent interface, `\{{DOMxRef("NameOfParentInterface")}}`._ (Note: If the interface doesn't inherit from another interface, remove this whole line.)

Include one term and definition for each method.

- `\{{DOMxRef("NameOfTheInterface.staticMethod1()")}}` {{Experimental_Inline}} {{Deprecated_Inline}} {{Non-standard_Inline}}
  - : Include a brief description of the method and what it does here. If the method is not experimental/deprecated/non-standard, remove the related macro calls.
- `\{{DOMxRef("NameOfTheInterface.staticMethod2()")}}`
  - : Include a brief description of the method and what it does here. If the method is not experimental/deprecated/non-standard, remove the related macro calls.

## Instance methods

_Also inherits methods from its parent interface, `\{{DOMxRef("NameOfParentInterface")}}`._ (Note: If the interface doesn't inherit from another interface, remove this whole line.)

Include one term and definition for each method.

- `\{{DOMxRef("NameOfTheInterface.method1()")}}` {{Experimental_Inline}} {{Deprecated_Inline}} {{Non-standard_Inline}}
  - : Include a brief description of the method and what it does here. If the method is not experimental/deprecated/non-standard, remove the related macro calls.
- `\{{DOMxRef("NameOfTheInterface.method2()")}}`
  - : Include a brief description of the method and what it does here. If the method is not experimental/deprecated/non-standard, remove the related macro calls.

## Events

_Also inherits events from its parent interface, `\{{DOMxRef("NameOfParentInterface")}}`._ (Note: If the interface doesn't inherit from another interface, remove this whole line.)

Listen to these events using {{DOMxRef("EventTarget.addEventListener", "addEventListener()")}} or by assigning an event listener to the `oneventname` property of this interface.

- `\{{DOMxRef("NameOfTheInterface.event1", "event1")}}` {{Experimental_Inline}} {{Deprecated_Inline}} {{Non-standard_Inline}}
  - : Fired when (include the description of when the event fires).
    Also available via the `oneventname1` property.
    If the event is not experimental/deprecated/non-standard, remove the related macro calls.
- `\{{DOMxRef("NameOfTheInterface.event2", "event2")}}`
  - : Fired when (include the description of when the event fires).
    Also available via the `oneventname2` property.
    If the event is not experimental/deprecated/non-standard, remove the related macro calls.

## Examples

Note that we use the plural "Examples" even if the page only contains one example.

### A descriptive heading

Each example must have an H3 heading (`###`) naming the example. The heading should be descriptive of what the example is doing. For example, "A simple example" does not say anything about the example and therefore, not a good heading. The heading should be concise. For a longer description, use the paragraph after the heading.

See our guide on how to add [code examples](/en-US/docs/MDN/Writing_guidelines/Page_structures/Code_examples) for more information.

> [!NOTE]
> Sometimes you will want to link to examples given on another page.
>
> **Scenario 1:** If you have some examples on this page and some more examples on another page:
>
> Include an H3 heading (`###`) for each example on this page and then a final H3 heading (`###`) with the text "More examples", under which you can link to the examples on other pages. For example:
>
> ```md
> ## Examples
>
> ### Using the fetch API
>
> Example of Fetch
>
> ### More examples
>
> Links to more examples on other pages
> ```
>
> **Scenario 2:** If you _only_ have examples on another page and none on this page:
>
> Don't add any H3 headings; just add the links directly under the H2 heading "Examples". For example:
>
> ```md
> ## Examples
>
> For examples of this API, see [the page on fetch()](https://example.org/).
> ```

## Specifications

`\{{Specifications}}`

_To use this macro, remove the backticks and backslash in the markdown file._

## Browser compatibility

`\{{Compat}}`

_To use this macro, remove the backticks and backslash in the markdown file._

## See also

Include links to reference pages and guides related to the current API. For more guidelines, see the [See also section](/en-US/docs/MDN/Writing_guidelines/Writing_style_guide#see_also_section) in the _Writing style guide_.

- link1
- link2
- external_link (year)
