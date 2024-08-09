# Css Selectors

```
<apple class='small'>
<apple class='small'>
<orange class='small'>
<orange class='small'>

```
to select only the small orange- `orange.small` will work.
- `class selector can be combined with type selector.`.
- `keep the type selector first then the type selector`.

```
<bento>
<apple class='small'>
<apple class='small'>
<orange class='small'>
<orange class='small'>
</bento>

<plate>
<apple class='small'>
<apple class='small'>
<orange class='small'>
<orange class='small'>
</plate>
```
to select only the small oranges from the bento, 
- `bento orange.small`
- `again keep the type selector first, then the class selector`

## To select multiple type selectors

- `plate,bento`

To get all the items
- `*`

To get all the items from the plates
- `plates *`

## Adjacent sibling selector

