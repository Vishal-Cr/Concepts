# Key concepts on Flexbox :gift: :sparkles:

## start vs flex-start vs self-start

The above also applies to end vs flex-end vs self-end.

- for `justify-content`. `With flex-direction: row` it appears that flex-start and start do the `same thing`, likewise for flex-end and end.

```- By default the flexbox model's main start and main end runs from left to right
- The start and flex-start property remains same by default
- when the row-reverse property is used. It reverses the main start and main end of the page flow.
- By this the flex-start property will still position the element to the right, which is now the main start(after reversing). and flex-end will position it to left which is now the main-end.
! The flex-start/end keywords are part of the Flexible Box Layout Module Level 1 specification.
! The start/end keywords are part of the Box Alignment Module Level 3 specification.
```    
The above applies to end,flex-end as well.
##### To manually set the position of any element in the flexbox use: `order` property.

- by default the order is 0.
- set it to positive or negative integer according to requirement.
- Order of 1 sets the element to right.
- :exclamation: When you set the order property, justify-content, align-items property does'nt work. Only align-self works. 

#### Align-self

- This property acts a normal align-items property, only it works for specific element.
#### Flex-Wrap
- The flex-wrap CSS property sets whether flex items are forced onto one line or can wrap onto multiple lines.
- :warning: To wrap the elements in reverse. Use wrap-reverse.

#### Flex-flow
- Addition of flex-direction and flex-wrap. 

#### Align Content

This can be confusing, but align-content determines the spacing between lines, while align-items determines how the items as a whole are aligned within the container. When there is only one line, align-content has no effect.

:sparkler: Learn to use wrap and align-items combined