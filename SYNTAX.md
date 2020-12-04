# Syntax Guide
This guide contains SDFs syntax rules.

## Comments
Comments are little lines that are not read by the parser, they (as well as empty lines) are completely scrapped during the reading process. They exist to give more information to the people looking at the SDF files.

`# This is a comment.`

## Attributes
An attribute is essentially the equivalent of a tag in other formats. It has a name and value. Each line is a separate attribute; however, there are different kinds of attributes that are for different uses. An attribute also does not have to be assigned, its value can be left blank.

`attributeName : attributeValue`

When making an unassigned attribute, you can remove the colon. The colon is also not restricted to a specific location, you can have any amount of spaces between it and the attribute name/value.
Any attribute can be assigned, but depending on what format you are converting to, the value of the attribute might not be crossed over. 
This is the case for categories and nested attributes in formats like XML.

**A new attribute MUST be on a newline.**

### Inner-Attribute
An inner-attribute is a type of attribute that is considered *inside* another attribute, it is not part of a hierarchy unlike nested elements (which will be explained later). In order to declare an inner-attribute, you must first declare an attribute that is **not** an inner-attribute.
```
attribute       : Attribute value.
.innerAttribute : Inner attribute value.
```
You can declare an infinite amount of inner-attributes.

### Category
A category is a type of attribute that holds other attributes (known as nested attributes).
```
!category : Category value.
```
Categories can also be empty, a category has officially ended when there are no longer any nested attributes within it.

### Nested Attributes
A nested attribute is a type of attribute that is part of a category, they cannot be declared outside of a category.
```
!category        : Category value.
;nestedAttribute : Nested attribute value.
```
A nested attribute is able to contain other nested attributes, a new level of nesting is created every time a semicolon is added to the start of the line.
```
!category          : Category value.
;nestedAttribute   : Nested attribute value.
;;nestedAttribute2 : Nested attribute value 2.
```

## Document Header
The document header contains the name of the document alongside the root inner-attributes, the root inner-attributes are used to declare values that are specific to the document, not any of the documents elements.
