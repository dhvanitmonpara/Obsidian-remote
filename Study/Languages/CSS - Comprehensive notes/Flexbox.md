## Flex Container

- **Display:**
  - Explanation: Defines a flex container.
  - Example Code:
    ```css
    display: flex;
    ```

- **Flex Direction:**
  - Explanation: Sets the direction of the main axis.
  - Example Code:
    ```css
    flex-direction: row;
    ```

- **Justify Content:**
  - Explanation: Aligns items on the main axis.
  - Example Code:
    ```css
    justify-content: space-between;
    ```

- **Align Items:**
  - Explanation: Aligns items on the cross axis.
  - Example Code:
    ```css
    align-items: center;
    ```

- **Align Content:**
  - Explanation: Aligns content when there is extra space in the cross axis.
  - Example Code:
    ```css
    align-content: space-around;
    ```

## Flex Items

- **Order:**
  - Explanation: Controls the order in which items appear.
  - Example Code:
    ```css
    order: 2;
    ```

- **Flex Grow:**
  - Explanation: Specifies how much an item should grow relative to others.
  - Example Code:
    ```css
    flex-grow: 1;
    ```

- **Flex Shrink:**
  - Explanation: Specifies how much an item should shrink relative to others.
  - Example Code:
    ```css
    flex-shrink: 0;
    ```

- **Flex Basis:**
  - Explanation: Sets the initial size of an item.
  - Example Code:
    ```css
    flex-basis: 20%;
    ```

- **Flex:**
  - Explanation: A shorthand for flex-grow, flex-shrink, and flex-basis.
  - Example Code:
    ```css
    flex: 1 0 30%;
    ```

## Align Self

- **Explanation:**
  Aligns a flex item along the cross axis, overriding the align-items value of the flex container.

- **Example Code:**
  ```css
  align-self: flex-end;
  ```

## Responsive Design with Flexbox

- **Media Queries:**
  - Explanation: Use media queries to apply flexbox styles based on screen size.

- **Example Code:**
  ```css
  @media screen and (max-width: 600px) {
    flex-direction: column;
  }
  ```

## Tips and Best Practices

- **Use Cases:**
  - Understand common use cases for flexbox layouts.

- **Nesting Flex Containers:**
  - Flex containers can be nested for more complex layouts.

## Resources

- **Documentation:**
  - MDN Web Docs - CSS Flexible Box Layout

- **Interactive Learning:**
  - Flexbox Froggy (flexboxfroggy.com)