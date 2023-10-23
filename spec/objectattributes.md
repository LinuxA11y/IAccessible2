<!--
SPDX-License-Identifier: CC-BY-NC-SA-4.0
-->

# IAccessible2 Object Attributes

## General Information

### Referenced Specifications

  *  [ODF v1.1](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html)
  *  [CSS2](http://www.w3.org/TR/REC-CSS2/)

### CSS2 values information

  *  [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length)
  *  [\<percentage\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-percentage)
  *  [\<string\>](http://www.w3.org/TR/REC-CSS2/syndata.html#strings)
  *  [\<integer\>](http://www.w3.org/TR/REC-CSS2/syndata.html#q13)

### Formating

  *  The proper format for the attributes is `"attribute:value;attribute:subattribute=subvalue,subattribute=subvalue;"`
  *  These characters need to be escaped with a backslash:  backslash, colon, comma, equals, and semicolon.
  *  Attribute strings must always end with a semicolon.

## Attributes

### List

Bulleted and numbered lists have been implemented in two different ways in IAccessible2 implementations.

In versions 2 and later of IBM Lotus Symphony the list items are objects of role IA2_ROLE_PARAGRAPH; each of those paragraph objects implements IAccessible2::attributes; one of the attributes is the list attribute described below.  For these list items IAccessibleText exposes the contents after the non-editable prefix string.  The prefix string is in the form of a bullet character, a numbering prefix string, or an image.  The reason for this separation of access mechanisms is because the caret is movable through the list text but not through the prefix text.

In Firefox the full string including the prefix is provided via IAccessibleText::text and the "auto-generated" text attribute is used for the string of characters representing the list prefix.

|Name|Values|Comments|Reference|
|---|---|---|---|
| list| level=[\<integer\>](http://www.w3.org/TR/REC-CSS2/syndata.html#q13), style=[bullet](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.3.Bullet_Level_Style), [number](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.2.Number_Level_Style), [image](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.4.Image_Level_Style), prefix=[\<string\>](http://www.w3.org/TR/REC-CSS2/syndata.html#strings)| [\<integer\>](http://www.w3.org/TR/REC-CSS2/syndata.html#q13) must be positive.| [ODF Specification  14.10](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.List_Style)|

#### List Subattributes

|Name|Values|Comments|Reference|
|---|---|---|---|
| level| [\<integer\>](http://www.w3.org/TR/REC-CSS2/syndata.html#q13)| [\<integer\>](http://www.w3.org/TR/REC-CSS2/syndata.html#q13) must be positive.|[ODF Specification  14.10.1](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.1.Common_List-Level_Style_Attributes)|
| style| [bullet](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.3.Bullet_Level_Style), [number](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.2.Number_Level_Style), [image](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.4.Image_Level_Style)| Specifies the style of the list.| [ODF Specification  14.10](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.List_Style)|
| prefix| [\<string\>](http://www.w3.org/TR/REC-CSS2/syndata.html#strings)| The prefix is inserted in front of the text.  The prefix contains a number (with any leading or trailing punctuation such as leading and/or trailing parens and/or a trailing period), or a bullet character, or the word "graphic".


### Paragraph

Text objects such as those with role paragraph can have per paragraph object attributes as listed in the table below.

|Name|Values|Comments|Reference|
|---|---|---|---|
| line-height| normal, [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length), [\<percentage\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-percentage)| [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length) is zero or positive.  This value should be specified in mm, e.g. 4mm.| [CSS2 Specification 10.8.1](http://www.w3.org/TR/REC-CSS2/visudet.html#propdef-line-height)|
| line-spacing| [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length)| [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length) is zero or positive.  This value should be specified in mm, e.g. 4mm.| [ODF Specification 15.5.3](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.5.3.Line_Distance)|
| margin-top| [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length), [\<percentage\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-percentage)| A typical use of this attribute is to define the margin adjacent to a paragraph but it could be used on any object.  Negative values for the margin property [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length) are allowed, but there may be implementation-specific limits.  This value should be specified in mm, e.g. 4mm.| [CSS2 Specification 8.3](http://www.w3.org/TR/REC-CSS2/box.html#propdef-margin-bottom)|
| margin-bottom| [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length), [\<percentage\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-percentage)| A typical use of this attribute is to define the margin adjacent to a paragraph but it could be used on any object.  Negative values for the margin property [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length) are allowed, but there may be implementation-specific limits.  This value should be specified in mm, e.g. 4mm.| [CSS2 Specification 8.3](http://www.w3.org/TR/REC-CSS2/box.html#propdef-margin-bottom)|
| margin-left| [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length), [\<percentage\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-percentage)| A typical use of this attribute is to define the margin adjacent to a paragraph but it could be used on any object.  Negative values for the margin property [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length) are allowed, but there may be implementation-specific limits.  This value should be specified in mm, e.g. 4mm.| [CSS2 Specification 8.3](http://www.w3.org/TR/REC-CSS2/box.html#propdef-margin-left)|
| margin-right| [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length), [\<percentage\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-percentage)| A typical use of this attribute is to define the margin adjacent to a paragraph but it could be used on any object.  Negative values for the margin property [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length) are allowed, but there may be implementation-specific limits.  This value should be specified in mm, e.g. 4mm.| [CSS2 Specification 8.3](http://www.w3.org/TR/REC-CSS2/box.html#propdef-margin-right)|
| tab-stop| tab-stop:position=[\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length), type=left, center, right, char, char=<character>, leader-text=<character>, leader-style=none, solid, dotted, dash, long-dash, dot-dash, dot-dot-dash, wave| Position must be 0 or positive. char and leader-text are single UNICODE characters.| [ODF Specification 15.5.11](http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.5.11.Tab_Stops)|
| text-align| left, right, justify, center| [CSS2 Specification 16.2](http://www.w3.org/TR/REC-CSS2/text.html#propdef-text-align)|
| text-indent| [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length)| Negative values for the margin property [\<length\>](http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length) are allowed, but there may be implementation-specific limits.  This value should be specified in mm, e.g. 4mm.| [CSS2 Specification 16.1](http://www.w3.org/TR/REC-CSS2/text.html#propdef-text-indent)|



