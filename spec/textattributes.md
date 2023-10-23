======iaccessible2/textattributes======

 **Text Attributes**
=====Contents=====

  * [[https://www.linuxfoundation.org/#General_Information|1 General Information]]
    * [[https://www.linuxfoundation.org/#Referenced_Specifications|1.1 Referenced Specifications]]
    * [[https://www.linuxfoundation.org/#CSS_2.1_values_information|1.2 CSS 2.1 values information]]
    * [[https://www.linuxfoundation.org/#Formatting|1.3 Formatting]]
    * [[https://www.linuxfoundation.org/#Object_Attributes|1.4 Object Attributes]]
  * [[https://www.linuxfoundation.org/#Attributes|2 Attributes]]

=====General Information=====


====Referenced Specifications====





  * [[http://www.w3.org/TR/CSS21/|CSS 2.1]]
  * [[http://www.w3.org/TR/CSS2/|CSS2]]
  * [[http://tools.ietf.org/html/rfc4646|IETF RFC 4646]]
  * [[http://tools.ietf.org/html/rfc4647|IETF RFC 4647]]
  * [[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html|ODF v1.1]]
  * [[http://www.w3.org/TR/wai-aria|WAI-ARIA 1.0]]
  * [[http://www.w3.org/TR/xsl11|XSL 1.1]]
====CSS 2.1 values information====

  * [[http://www.w3.org/TR/CSS21/syndata.html#value-def-color|<color>]]
  * [[http://www.w3.org/TR/CSS21/syndata.html#numbers|<integer>]]
  * [[http://www.w3.org/TR/CSS21/syndata.html#value-def-length|<length>]]
  * [[http://www.w3.org/TR/CSS21/syndata.html#percentage-units|<percentage>]]
  * [[http://www.w3.org/TR/CSS21/syndata.html#strings|<string>]]
====Formatting====



  * The proper format for the attributes is\\  ''"attribute:value;attribute:value,value;"''
  * The format of ''attribute:value,value;'' is currently only used for the invalid attribute, e.g. ''invalid:spelling,grammar;''
  * These characters need to be escaped with a backslash: backslash, colon, comma, equals, and semicolon.
  * Attribute strings must always end with a semicolon, i.e. there needs to be a semicolon at the very end of the string of the full set of attribute:value pairs.
  * Series of attribute values, as shown in the examples above, must not end with a comma.
====Object Attributes====



Some text attributes are on a paragraph by paragraph basis and are documented in the [[:accessibility:iaccessible2:objectattributes|Object Attributes Specification]].
=====Attributes=====



The following attributes can change on a character by character basis. They are retrieved via the IAccessibleText::attributes method. If an attribute is not specified and if the table shows that there is a default value, the default value should be assumed.
^Name^Values^Default^Comments^Reference^
|auto-generated|true, false|false|This attribute is used in Firefox but not in IBM Lotus Symphony. Symphony uses the list object attribute for bulleted and numbered lists. In Firefox, this attribute's value is "true" for list bullet/numbering prefix text or layout-inserted text such as via the CSS pseudo styles :before or :after.| |
|background-color|transparent, [[http://www.w3.org/TR/CSS21/syndata.html#value-def-color|<color>]]|transparent|[[http://www.w3.org/TR/CSS21/syndata.html#value-def-color|<color>]] as rgb(n,n,n) where n is 0-255|[[http://www.w3.org/TR/CSS21/colors.html#background-properties|CSS 2.1 Specification 14.2.1]]|
|color|[[http://www.w3.org/TR/CSS21/syndata.html#value-def-color|<color>]]|rgb(0,0,0)|[[http://www.w3.org/TR/CSS21/syndata.html#value-def-color|<color>]] as rgb(n,n,n) where n is 0-255|[[http://www.w3.org/TR/CSS21/colors.html#colors|CSS 2.1 Specification 14.1]]|
|font-family|[[http://www.w3.org/TR/CSS21/syndata.html#strings|<string>]]|no default| |[[http://www.w3.org/TR/CSS21/fonts.html#font-family-prop|CSS 2.1 Specification 15.3]]|
|font-size|[[http://www.w3.org/TR/CSS21/syndata.html#value-def-length|<length>]]|no default|font size in points, e.g. font-size:12pt;\\  \\  Note: When the application's native attribute is not in pts the application accessibility code should convert to pt. The conversion doesn't have to be exact. The intent is to give the user a feel for the size of the text.|[[http://www.w3.org/TR/CSS21/fonts.html#font-size-props|CSS 2.1 Specification 15.7]]|
|font-style|normal, italic, oblique|normal| |[[http://www.w3.org/TR/CSS21/fonts.html#font-styling|CSS 2.1 Specification 15.4]]|
|font-weight|normal, bold, [[http://www.w3.org/TR/CSS21/syndata.html#numbers|<integer>]]|normal (400)|100, 200, 300, 400, 500, 600, 700, 800, 900; normal = 400, bold = 700|[[http://www.w3.org/TR/CSS21/fonts.html#font-boldness|CSS 2.1 Specification 15.6]]|
|invalid|true, false, spelling, grammar|false| |[[http://www.w3.org/TR/wai-aria/#aria-invalid|WAI-ARIA Specification 5.6]]|
|language|language in IETF [[http://www.ietf.org/rfc/rfc4646.txt|RFC 4646]] format|en-US|Examples are en-US and de-DE.\\ Also refer to [[http://www.w3.org/International/articles/language-tags/|Language tags in HTML and XML]].\\ |[[http://tools.ietf.org/html/rfc4646|IETF RFC 4646]]\\  \\  [[http://tools.ietf.org/html/rfc4647|IETF RFC 4647]]|
|text-line-through-mode|continuous, skip-white-space|continuous| |[[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.34.Text_Line-Through_Word_Mode|ODF Specification 15.4.34]]|
|text-line-through-style|none, solid, dotted, dash, long-dash, dot-dash, dot-dot-dash, wave|none|Either text-line-through-style or text-line-through-type or both can be used. If text-line-through-type is not used the line is a single line.|[[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.7.Line-Through_Style|ODF Specification 15.4.7]]|
|text-line-through-text|[[http://www.w3.org/TR/CSS21/syndata.html#strings|<string>]]|an empty string|Typical values are / and X, e.g. text-line-through-text:/;|[[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.10.Line-Through_Text|ODF Specification 15.4.10]]|
|text-line-through-type|none, single, double|none|Either text-line-through-type or text-line-through-style or both can be used. If text-line-through-style is not used the line is solid.|[[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.6.Line-Through_Type|ODF Specification 15.4.6]]|
|text-line-through-width|auto, normal, bold, thin, dash, medium, thick, [[http://www.w3.org/TR/CSS21/syndata.html#numbers|<integer>]], [[http://www.w3.org/TR/CSS21/syndata.html#value-def-length|<length>]], [[http://www.w3.org/TR/CSS21/syndata.html#percentage-units|<percentage>]]|auto|[[http://www.w3.org/TR/CSS21/syndata.html#numbers|<integer>]] and [[http://www.w3.org/TR/CSS21/syndata.html#value-def-length|<length>]] must be positive.|[[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.8.Line-Through_Width|ODF Specification 15.4.8]]|
|text-outline|true, false|false| |[[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.5.Text_Outline|ODF Specification 15.4.5]]|
|text-position|baseline, super, sub|baseline|When the text is not positioned on the baseline and the application's native attribute is not specified as super or sub the application should provide the value super when the text is above the baseline and sub when the text is below the baseline.\\ Also consider the case of the html snippet, x<sup>a<sub>i</sub></sup>. A super or sub text attribute refers to the base line of the prior character which in turn may itself be offset from the baseline of the character in front of it.\\ |[[http://www.w3.org/TR/CSS21/visudet.html#propdef-vertical-align|CSS 2.1 Specification 10.8]]|
|text-shadow|see reference|none|Inherit is not a valid value.\\ Note that this attribute was removed from the CSS2 spec. The link in the reference column is to an archived version of the CSS2 spec.\\ |[[http://www.w3.org/TR/1998/REC-CSS2-19980512/text.html#text-shadow-props|CSS2 Specification 16.3.2]]|
|text-underline-mode|continuous, skip-white-space|continuous| |[[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.33.Text_Underline_Word_Mode|ODF Specification 15.4.33]]|
|text-underline-style|none, solid, dotted, dash, long-dash, dot-dash, dot-dot-dash, wave|none|Either text-underline-style or text-underline-type or both can be used. If text-underline-type is not used the line is a single line.|[[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.29.Underlining_Style|ODF Specification 15.4.29]]|
|text-underline-type|none, single, double|none|Either text-underline-type or text-underline-style or both can be used. If text-underline-style is not used the line is solid.|[[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.28.Underlining_Type|ODF Specification 15.4.28]]|
|text-underline-width|auto, normal, bold, thin, dash, medium, thick, [[http://www.w3.org/TR/CSS21/syndata.html#numbers|<integer>]], [[http://www.w3.org/TR/CSS21/syndata.html#value-def-length|<length>]], [[http://www.w3.org/TR/CSS21/syndata.html#percentage-units|<percentage>]]|auto|[[http://www.w3.org/TR/CSS21/syndata.html#numbers|<integer>]] and [[http://www.w3.org/TR/CSS21/syndata.html#value-def-length|<length>]] must be positive.|[[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.4.30.Underling_Width|ODF Specification 15.4.30]]|
|writing-mode|lr, rl, tb|lr|tb is top-to-bottom, i.e. text flows from top-to-bottom then left-to-right.|[[http://www.w3.org/TR/xsl11/#writing-mode|XSL 1.1 Specification 7.29.7]]|



