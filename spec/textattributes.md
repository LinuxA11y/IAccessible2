# IAccessible2 Text Attributes

## General Information

### Referenced Specifications

  * [CSS 2.1](http://www.w3.org/TR/CSS21/)
  * [CSS2](http://www.w3.org/TR/CSS2/)
  * [IETF RFC 4646](http://tools.ietf.org/html/rfc4646)
  * [IETF RFC 4647](http://tools.ietf.org/html/rfc4647)
  * [ODF v1.1](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html)
  * [WAI-ARIA 1.0](http://www.w3.org/TR/wai-aria)
  * [XSL 1.1](http://www.w3.org/TR/xsl11)

### CSS 2.1 values information

  * [\<color\>](http://www.w3.org/TR/CSS21/syndata.html#value-def-color)
  * [\<integer\>](http://www.w3.org/TR/CSS21/syndata.html#numbers)
  * [\<length\>](http://www.w3.org/TR/CSS21/syndata.html#value-def-length)
  * [\<percentage\>](http://www.w3.org/TR/CSS21/syndata.html#percentage-units)
  * [\<string\>](http://www.w3.org/TR/CSS21/syndata.html#strings)

### Formatting

  * The proper format for the attributes is `"attribute:value;attribute:value,value;"`
  * The format of `attribute:value,value;` is currently only used for the invalid attribute, e.g. `invalid:spelling,grammar;`
  * These characters need to be escaped with a backslash: backslash, colon, comma, equals, and semicolon.
  * Attribute strings must always end with a semicolon, i.e. there needs to be a semicolon at the very end of the string of the full set of attribute:value pairs.
  * Series of attribute values, as shown in the examples above, must not end with a comma.

### Object Attributes

Some text attributes are on a paragraph by paragraph basis and are documented in the [Object Attributes Specification](./objectattributes.md).

## Attributes

The following attributes can change on a character by character basis. They are retrieved via the IAccessibleText::attributes method. If an attribute is not specified and if the table shows that there is a default value, the default value should be assumed.

|Name|Values|Default|Comments|Reference|
|---|---|---|---|---|
|auto-generated|true, false|false|This attribute is used in Firefox but not in IBM Lotus Symphony. Symphony uses the list object attribute for bulleted and numbered lists. In Firefox, this attribute's value is "true" for list bullet/numbering prefix text or layout-inserted text such as via the CSS pseudo styles :before or :after.| |
|background-color|transparent, [\<color\>](http://www.w3.org/TR/CSS21/syndata.html#value-def-color)|transparent|[\<color\>](http://www.w3.org/TR/CSS21/syndata.html#value-def-color) as rgb(n,n,n) where n is 0-255|[CSS 2.1 Specification 14.2.1](http://www.w3.org/TR/CSS21/colors.html#background-properties)
|color|[\<color\>](http://www.w3.org/TR/CSS21/syndata.html#value-def-color)|rgb(0,0,0)|[\<color\>](http://www.w3.org/TR/CSS21/syndata.html#value-def-color) as rgb(n,n,n) where n is 0-255|[CSS 2.1 Specification 14.1](http://www.w3.org/TR/CSS21/colors.html#colors)
|font-family|[\<string\>](http://www.w3.org/TR/CSS21/syndata.html#strings)|no default| |[CSS 2.1 Specification 15.3](http://www.w3.org/TR/CSS21/fonts.html#font-family-prop)|
|font-size|[\<length\>](http://www.w3.org/TR/CSS21/syndata.html#value-def-length)|no default|font size in points, e.g. font-size:12pt;<br/><br/>Note: When the application's native attribute is not in pts the application accessibility code should convert to pt. The conversion doesn't have to be exact. The intent is to give the user a feel for the size of the text.|[CSS 2.1 Specification 15.7](http://www.w3.org/TR/CSS21/fonts.html#font-size-props)|
|font-style|normal, italic, oblique|normal| |[CSS 2.1 Specification 15.4](http://www.w3.org/TR/CSS21/fonts.html#font-styling)|
|font-weight|normal, bold, [\<integer\>](http://www.w3.org/TR/CSS21/syndata.html#numbers)|normal (400)|100, 200, 300, 400, 500, 600, 700, 800, 900; normal = 400, bold = 700|[CSS 2.1 Specification 15.6](http://www.w3.org/TR/CSS21/fonts.html#font-boldness)|
|invalid|true, false, spelling, grammar|false| |[WAI-ARIA Specification 5.6](http://www.w3.org/TR/wai-aria/#aria-invalid)|
|language|language in IETF [RFC 4646](http://www.ietf.org/rfc/rfc4646.txt) format|en-US|Examples are en-US and de-DE.<br/>Also refer to [Language tags in HTML and XML](http://www.w3.org/International/articles/language-tags/).|[IETF RFC 4646](http://tools.ietf.org/html/rfc4646)<br/><br/>[IETF RFC 4647](http://tools.ietf.org/html/rfc4647)|
|text-line-through-mode|continuous, skip-white-space|continuous| |[ODF Specification 15.4.34](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.34.Text_Line-Through_Word_Mode)|
|text-line-through-style|none, solid, dotted, dash, long-dash, dot-dash, dot-dot-dash, wave|none|Either text-line-through-style or text-line-through-type or both can be used. If text-line-through-type is not used the line is a single line.|[ODF Specification 15.4.7](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.7.Line-Through_Style)|
|text-line-through-text|[\<string\>](http://www.w3.org/TR/CSS21/syndata.html#strings)|an empty string|Typical values are / and X, e.g. text-line-through-text:/;|[ODF Specification 15.4.10](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.10.Line-Through_Text)|
|text-line-through-type|none, single, double|none|Either text-line-through-type or text-line-through-style or both can be used. If text-line-through-style is not used the line is solid.|[ODF Specification 15.4.6](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.6.Line-Through_Type)|
|text-line-through-width|auto, normal, bold, thin, dash, medium, thick, [\<integer\>](http://www.w3.org/TR/CSS21/syndata.html#numbers), [\<length\>](http://www.w3.org/TR/CSS21/syndata.html#value-def-length), [\<percentage\>](http://www.w3.org/TR/CSS21/syndata.html#percentage-units)|auto|[\<integer\>](http://www.w3.org/TR/CSS21/syndata.html#numbers) and [\<length\>](http://www.w3.org/TR/CSS21/syndata.html#value-def-length) must be positive.|[ODF Specification 15.4.8](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.8.Line-Through_Width)|
|text-outline|true, false|false| |[ODF Specification 15.4.5](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.5.Text_Outline)|
|text-position|baseline, super, sub|baseline|When the text is not positioned on the baseline and the application's native attribute is not specified as super or sub the application should provide the value super when the text is above the baseline and sub when the text is below the baseline.<br/>Also consider the case of the html snippet, x<sup>a<sub>i</sub></sup>. A super or sub text attribute refers to the base line of the prior character which in turn may itself be offset from the baseline of the character in front of it.|[CSS 2.1 Specification 10.8](http://www.w3.org/TR/CSS21/visudet.html#propdef-vertical-align)|
|text-shadow|see reference|none|Inherit is not a valid value.<br/> Note that this attribute was removed from the CSS2 spec. The link in the reference column is to an archived version of the CSS2 spec.|[CSS2 Specification 16.3.2](http://www.w3.org/TR/1998/REC-CSS2-19980512/text.html#text-shadow-props)|
|text-underline-mode|continuous, skip-white-space|continuous| |[ODF Specification 15.4.33](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.33.Text_Underline_Word_Mode)|
|text-underline-style|none, solid, dotted, dash, long-dash, dot-dash, dot-dot-dash, wave|none|Either text-underline-style or text-underline-type or both can be used. If text-underline-type is not used the line is a single line.|[ODF Specification 15.4.29](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.29.Underlining_Style)|
|text-underline-type|none, single, double|none|Either text-underline-type or text-underline-style or both can be used. If text-underline-style is not used the line is solid.|[ODF Specification 15.4.28](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.28.Underlining_Type)|
|text-underline-width|auto, normal, bold, thin, dash, medium, thick, [\<integer\>](http://www.w3.org/TR/CSS21/syndata.html#numbers), [\<length\>](http://www.w3.org/TR/CSS21/syndata.html#value-def-length), [\<percentage\>](http://www.w3.org/TR/CSS21/syndata.html#percentage-units)|auto|[\<integer\>](http://www.w3.org/TR/CSS21/syndata.html#numbers) and [\<length\>](http://www.w3.org/TR/CSS21/syndata.html#value-def-length) must be positive.|[ODF Specification 15.4.30](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.30.Underling_Width)|
|writing-mode|lr, rl, tb|lr|tb is top-to-bottom, i.e. text flows from top-to-bottom then left-to-right.|[XSL 1.1 Specification 7.29.7](http://www.w3.org/TR/xsl11/#writing-mode)|
