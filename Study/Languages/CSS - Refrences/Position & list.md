# Position

| Property value | Description | Positioning according to | Inner properties | Document flow |
|----|----|----|----|---|
| `position: static;` | Default value | Root element |No| Yes |
| `position: relative;` | Same as `static` | Root element |All values except `z-index` | Yes |
| `position: absolute;`| No access to outer part of Parent element | Parent element | Yes | No |
| `position: fixed;`| Fixed at a perticular position, even not move on scrolling the webpage| Root element | Yes | No|
| `position: sticky;`| combination of `relative` and `fixed`| Root element | Yes | No |

**Position properties:**

```css
left: 2px;
right: 1px;
top: 9px;
bottom: 4px;
z-index: 3;
```

# List styles


`liststyle: circle;` represents circle type bullet point

**Important:**

`lisgtstyle: inside/outside;` represents list icon position.

**Shorthand:**

```css
Liststyle: "circle"  inside url('    ');
```
