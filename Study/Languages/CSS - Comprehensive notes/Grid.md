## Grid Container

- **Display:**
  - Explanation: Defines a grid container.
  - Example Code:
    ```css
    display: grid;
    ```

- **Grid Template Columns:**
  - Explanation: Specifies the size of columns in the grid.
  - Example Code:
    ```css
    grid-template-columns: repeat(3, 1fr);
    ```

- **Grid Template Rows:**
  - Explanation: Specifies the size of rows in the grid.
  - Example Code:
    ```css
    grid-template-rows: 100px auto 50px;
    ```

- **Grid Gap:**
  - Explanation: Sets the gap between rows and columns.
  - Example Code:
    ```css
    grid-gap: 10px;
    ```

- **Justify Items:**
  - Explanation: Aligns grid items along the inline (row) axis.
  - Example Code:
    ```css
    justify-items: center;
    ```

- **Align Items:**
  - Explanation: Aligns grid items along the block (column) axis.
  - Example Code:
    ```css
    align-items: center;
    ```

## Grid Items

- **Grid Column / Row:**
  - Explanation: Determines on which track an item will be placed.
  - Example Code:
    ```css
    grid-column: 2 / span 3;
    grid-row: 1 / 3;
    ```

- **Place Self:**
  - Explanation: A shorthand for align-self and justify-self.
  - Example Code:
    ```css
    place-self: end center;
    ```

## Grid Auto Flow

- **Explanation:**
  Specifies how the auto-placement algorithm works.

- **Example Code:**
  ```css
  grid-auto-flow: row dense;
  ```

## Responsive Design with Grid

- **Media Queries:**
  - Explanation: Use media queries to apply grid styles based on screen size.

- **Example Code:**
  ```css
  @media screen and (max-width: 600px) {
    grid-template-columns: 1fr;
  }
  ```

## Grid Areas

- **Explanation:**
  Defines named grid areas for item placement.

- **Example Code:**
  ```css
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  ```

## Tips and Best Practices

- **Fractional Units:**
  - Utilize fractional units for flexible grid layouts.

- **Alignment Techniques:**
  - Learn various alignment techniques for grid items.

## Resources

- **Documentation:**
  - MDN Web Docs - CSS Grid Layout

- **Interactive Learning:**
  - Grid Garden (cssgridgarden.com)