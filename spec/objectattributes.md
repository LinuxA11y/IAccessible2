======iaccessible2/objectattributes======

 **Object Attributes**\\
=====Contents=====

  * [[https://www.linuxfoundation.org/#General_Information|1 General Information]]
    * [[https://www.linuxfoundation.org/#Referenced_Specifications|1.1 Referenced Specifications]]
    * [[https://www.linuxfoundation.org/#CSS2_values_information|1.2 CSS2 values information]]
    * [[https://www.linuxfoundation.org/#Formating|1.3 Formating]]
  * [[https://www.linuxfoundation.org/#Attributes|2 Attributes]]
    * [[https://www.linuxfoundation.org/#List|2.1 List]]
      * [[https://www.linuxfoundation.org/#List_Subattributes|2.1.1 List Subattributes]]
    * [[https://www.linuxfoundation.org/#Paragraph|2.2 Paragraph]]

===== General Information=====
==== Referenced Specifications====

  *  [[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html|ODF v1.1]]
  *  [[http://www.w3.org/TR/REC-CSS2/|CSS2]]
==== CSS2 values information====

  *  [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]]
  *  [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-percentage|<percentage>]]
  *  [[http://www.w3.org/TR/REC-CSS2/syndata.html#strings|<string>]]
  *  [[http://www.w3.org/TR/REC-CSS2/syndata.html#q13|<integer>]]
==== Formating====

  *  The proper format for the attributes is \\  '' "attribute:value;attribute:subattribute=subvalue,subattribute=subvalue;" ''
  *  These characters need to be escaped with a backslash:  backslash, colon, comma, equals, and semicolon.
  *  Attribute strings must always end with a semicolon.
===== Attributes=====
==== List====

Bulleted and numbered lists have been implemented in two different ways in IAccessible2 implementations.

In versions 2 and later of IBM Lotus Symphony the list items are objects of role IA2_ROLE_PARAGRAPH; each of those paragraph objects implements IAccessible2::attributes; one of the attributes is the list attribute described below.  For these list items IAccessibleText exposes the contents after the non-editable prefix string.  The prefix string is in the form of a bullet character, a numbering prefix string, or an image.  The reason for this separation of access mechanisms is because the caret is movable through the list text but not through the prefix text.

In Firefox the full string including the prefix is provided via IAccessibleText::text and the "auto-generated" text attribute is used for the string of characters representing the list prefix.
^ Name^ Values^ Comments^ Reference^
| list| level=[[http://www.w3.org/TR/REC-CSS2/syndata.html#q13|<integer>]], style=[[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.3.Bullet_Level_Style|bullet]], [[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.2.Number_Level_Style|number]], [[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.4.Image_Level_Style|image]], prefix=[[http://www.w3.org/TR/REC-CSS2/syndata.html#strings|<string>]]| [[http://www.w3.org/TR/REC-CSS2/syndata.html#q13|<integer>]] must be positive.| [[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.List_Style|ODF Specification  14.10]]|
=== List Subattributes===
^ Name^ Values^ Comments^ Reference^
| level| [[http://www.w3.org/TR/REC-CSS2/syndata.html#q13|<integer>]]| [[http://www.w3.org/TR/REC-CSS2/syndata.html#q13|<integer>]] must be positive.|[[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.1.Common_List-Level_Style_Attributes|ODF Specification  14.10.1]]|
| style| [[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.3.Bullet_Level_Style|bullet]], [[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.2.Number_Level_Style|number]], [[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.4.Image_Level_Style|image]]| Specifies the style of the list.| [[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:14.10.List_Style|ODF Specification  14.10]]|
| prefix| [[http://www.w3.org/TR/REC-CSS2/syndata.html#strings|<string>]]| The prefix is inserted in front of the text.  The prefix contains a number (with any leading or trailing punctuation such as leading and/or trailing parens and/or a trailing period), or a bullet character, or the word "graphic".

\\
==== Paragraph====

Text objects such as those with role paragraph can have per paragraph object attributes as listed in the table below.
^ Name^ Values^ Comments^ Reference^
| line-height| normal, [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]], [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-percentage|<percentage>]]| [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]] is zero or positive.  This value should be specified in mm, e.g. 4mm.| [[http://www.w3.org/TR/REC-CSS2/visudet.html#propdef-line-height|CSS2 Specification 10.8.1]]|
| line-spacing| [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]]| [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]] is zero or positive.  This value should be specified in mm, e.g. 4mm.| [[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.5.3.Line_Distance|ODF Specification 15.5.3]]|
| margin-top| [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]], [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-percentage|<percentage>]]| A typical use of this attribute is to define the margin adjacent to a paragraph but it could be used on any object.  Negative values for the margin property [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]] are allowed, but there may be implementation-specific limits.  This value should be specified in mm, e.g. 4mm.| [[http://www.w3.org/TR/REC-CSS2/box.html#propdef-margin-bottom|CSS2 Specification 8.3]]|
| margin-bottom| [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]], [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-percentage|<percentage>]]| A typical use of this attribute is to define the margin adjacent to a paragraph but it could be used on any object.  Negative values for the margin property [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]] are allowed, but there may be implementation-specific limits.  This value should be specified in mm, e.g. 4mm.| [[http://www.w3.org/TR/REC-CSS2/box.html#propdef-margin-bottom|CSS2 Specification 8.3]]|
| margin-left| [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]], [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-percentage|<percentage>]]| A typical use of this attribute is to define the margin adjacent to a paragraph but it could be used on any object.  Negative values for the margin property [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]] are allowed, but there may be implementation-specific limits.  This value should be specified in mm, e.g. 4mm.| [[http://www.w3.org/TR/REC-CSS2/box.html#propdef-margin-left|CSS2 Specification 8.3]]|
| margin-right| [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]], [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-percentage|<percentage>]]| A typical use of this attribute is to define the margin adjacent to a paragraph but it could be used on any object.  Negative values for the margin property [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]] are allowed, but there may be implementation-specific limits.  This value should be specified in mm, e.g. 4mm.| [[http://www.w3.org/TR/REC-CSS2/box.html#propdef-margin-right|CSS2 Specification 8.3]]|
| tab-stop| tab-stop:position=[[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]], type=left, center, right, char, char=<character>, leader-text=<character>, leader-style=none, solid, dotted, dash, long-dash, dot-dash, dot-dot-dash, wave| Position must be 0 or positive. char and leader-text are single UNICODE characters.| [[http://docs.oasis-open.org/office/v1.1/OS/OpenDocument-v1.1-html/OpenDocument-v1.1.html#outline:15.5.11.Tab_Stops|ODF Specification 15.5.11]]|
| text-align| left, right, justify, center| [[http://www.w3.org/TR/REC-CSS2/text.html#propdef-text-align|CSS2 Specification 16.2]]|
| text-indent| [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]]| Negative values for the margin property [[http://www.w3.org/TR/REC-CSS2/syndata.html#value-def-length|<length>]] are allowed, but there may be implementation-specific limits.  This value should be specified in mm, e.g. 4mm.| [[http://www.w3.org/TR/REC-CSS2/text.html#propdef-text-indent|CSS2 Specification 16.1]]|



