Use `display: grid;` to.declare the container as a grid.

# Grid gap

It defines gap or space between grid items.
```css
grid-row-gap: 9px;
grid-column-gap: 6px;
```

Use shorthand if you want to define different values: 

```css
grid-gap: 4px 6px;
```
Use shorthand if you want to use same value for both:
```css
grid-gap: 9px;
```

# Grid template column

It defines horizontal grid item size.
```css
grid-templet-column: auto auto auto;
```
It will automatically create columns and defines size, you can also give a specific value of you want.
```css
grid-templete-cloumn: auto 40px auto auto;
```
The given code will execute 4 columns in which 2nd one has pre-define size and others will follow parent element size.

Same thing goes with `grid-template-row` property.

**Note:** `justify-content`, `align-item` and `align-content` is same as flex-box.

# Span items

It will span grid items according to given value.
```css
grid-row: 1/5;
```

It defines that row will start from 1st grid-line and end at 5th grid-line.

Same thing goes with `grid-column` property.
