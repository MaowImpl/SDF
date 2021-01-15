**Header**<br>
```
<header elements>
-
```
Must be at the top, header is stopped by the header break symbol ( - ), can only contain annotations, header elements, attributes, and nested elements.

**Header Element**<br>
`^headerElement : "value"`
Same as an element, must be inside of a header, can have attributes and nested elements.

**Element**<br>
`element : "value"`<br>
Value is optional, assignment operator ( : ) is also optional if value is not assigned.

**Attribute**<br>
`.attribute : "value"`<br>
Same as an element, must go underneath an element. An attribute is considered to be a property of an element, not a child to it, attributes can't have their own attributes.

**Nested Element**<br>
`>nested : "value"`<br>
Same as an element, must also go underneath an element or other nested element. Number of nesting operators ( > ) increases based on the level of nesting, e.g. `>>` is nested in a `>` nested element. Nested elements can have attributes.

**Annotation**<br>
`@annotation`<br>
Must go above an element/nested element, cannot have a value and cannot be assigned to attributes.
