# clock
This simple project uses html css and js.


## Topic:
- id and class
- display:flex;
- setInterval() method



# id and class 
In HTML, both `id` and `class` attributes are used to identify elements, but they serve different purposes and have distinct rules for their usage.

### Use `id` when:
1. **Uniqueness**: The element must have a unique identifier on the page. An `id` should only be assigned to one element.
2. **Specific Targeting**: You want to style or manipulate a single, specific element using JavaScript or CSS.
   - Example: 
     ```html
     <div id="header">Header Content</div>
     ```

   In CSS:
   ```css
   #header {
     background-color: blue;
   }
   ```

   In JavaScript:
   ```javascript
   document.getElementById('header').style.backgroundColor = 'blue';
   ```

3. **Anchor Links**: `id` can be used for linking to specific sections on the page.
   - Example:
     ```html
     <a href="#section1">Go to Section 1</a>
     <div id="section1">Section 1 Content</div>
     ```

### Use `class` when:
1. **Reusability**: Multiple elements can share the same class, which allows you to apply the same style or behavior to all of them.
2. **Grouping Elements**: You want to apply CSS styles or JavaScript actions to multiple elements of the same type.
   - Example: 
     ```html
     <div class="content-box">Box 1</div>
     <div class="content-box">Box 2</div>
     ```

   In CSS:
   ```css
   .content-box {
     border: 1px solid black;
   }
   ```

   In JavaScript:
   ```javascript
   let boxes = document.getElementsByClassName('content-box');
   for (let i = 0; i < boxes.length; i++) {
     boxes[i].style.border = '1px solid black';
   }
   ```

### Key Differences:
- **`id`** is unique and can only be used once per page.
- **`class`** can be applied to multiple elements to apply shared styling or behavior.

Use `id` for unique elements and `class` for grouping and styling multiple elements.


# display: flex

In CSS, `display: flex` is used to apply the **flexbox** layout to a container, allowing for more dynamic and responsive designs. Flexbox makes it easier to align and distribute space among items in a container, especially when their size is unknown or dynamic.

### Key Featvures of `display: flex`
1. **Main Axis and Cross Axis**: 
   - The *main axis* is defined by the `flex-direction` property (default is horizontal left to right).
   - The *cross axis* is perpendicular to the main axis.

2. **Flex Container and Flex Items**:
   - The parent element that has `display: flex` is called the **flex container**.
   - The child elements within it are called **flex items**.

### Example
```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.container {
  display: flex; /* Makes container a flexbox */
  justify-content: space-between; /* Aligns items along the main axis */
  align-items: center; /* Aligns items along the cross axis */
}

.item {
  padding: 10px;
  background-color: lightblue;
}
```

### Common Properties for Flexbox
1. **`flex-direction`**: Defines the direction of the flex items (row, column, etc.).
   ```css
   flex-direction: row; /* default, horizontal */
   flex-direction: column; /* vertical */
   ```

2. **`justify-content`**: Aligns flex items along the main axis.
   - `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, etc.

3. **`align-items`**: Aligns items along the cross axis.
   - `stretch` (default), `flex-start`, `flex-end`, `center`, etc.

4. **`flex-wrap`**: Controls whether flex items should wrap or stay in one line.
   ```css
   flex-wrap: wrap; /* Allows items to wrap */
   ```

5. **`align-content`**: Controls the alignment of multiple rows of flex items.
   - Useful when flex items wrap.

### Advantages
- Simplifies layout for responsive design.
- Easy to vertically and horizontally center items.
- Dynamically adjusts the size and position of items based on available space.

Would you like help with a specific flexbox layout or more examples?



# css units

|Unit|Description||
|---|---|---|
|em|Relative to the font-size of the element (2em means 2 times the size of the current font)|[Try it](https://www.w3schools.com/cssref/tryit.php?filename=trycss_unit_em)|
|ex|Relative to the x-height of the current font (rarely used)|[Try it](https://www.w3schools.com/cssref/tryit.php?filename=trycss_unit_ex)|
|ch|Relative to the width of the "0" (zero)|[Try it](https://www.w3schools.com/cssref/tryit.php?filename=trycss_unit_ch)|
|rem|Relative to font-size of the root element|[Try it](https://www.w3schools.com/cssref/tryit.php?filename=trycss_unit_rem)|
|vw|Relative to 1% of the width of the viewport*|[Try it](https://www.w3schools.com/cssref/tryit.php?filename=trycss_unit_vw)|
|vh|Relative to 1% of the height of the viewport*|[Try it](https://www.w3schools.com/cssref/tryit.php?filename=trycss_unit_vh)|
|vmin|Relative to 1% of viewport's* smaller dimension|[Try it](https://www.w3schools.com/cssref/tryit.php?filename=trycss_unit_vmin)|
|vmax|Relative to 1% of viewport's* larger dimension|[Try it](https://www.w3schools.com/cssref/tryit.php?filename=trycss_unit_vmax)|
|%|Relative to the parent element|



# js 



## setInterval() method

[JS Doc](https://developer.mozilla.org/en-US/docs/Web/API/setInterval).

The **`setInterval()`** method, offered on the [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) and [`WorkerGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope) interfaces, repeatedly calls a function or executes a code snippet, with a fixed time delay between each call.

This method returns an interval ID which uniquely identifies the interval, so you can remove it later by calling [`clearInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/clearInterval "clearInterval()").


```js
setInterval(code)
setInterval(code, delay)

setInterval(func)
setInterval(func, delay)
setInterval(func, delay, arg1)
setInterval(func, delay, arg1, arg2)
setInterval(func, delay, arg1, arg2, /* …, */ argN)

```

### [Parameters](https://developer.mozilla.org/en-US/docs/Web/API/setInterval#parameters)

[`func`](https://developer.mozilla.org/en-US/docs/Web/API/setInterval#func)

A [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) to be executed every `delay` milliseconds. The first execution happens after `delay` milliseconds.

[`code`](https://developer.mozilla.org/en-US/docs/Web/API/setInterval#code)

An optional syntax allows you to include a string instead of a function, which is compiled and executed every `delay` milliseconds. This syntax is _not recommended_ for the same reasons that make using [`eval()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval) a security risk.

[`delay`](https://developer.mozilla.org/en-US/docs/Web/API/setInterval#delay) Optional

The time, in milliseconds (thousandths of a second), the timer should delay in between executions of the specified function or code. Defaults to 0 if not specified. See [Delay restrictions](https://developer.mozilla.org/en-US/docs/Web/API/setInterval#delay_restrictions) below for details on the permitted range of `delay` values.

[`arg1`](https://developer.mozilla.org/en-US/docs/Web/API/setInterval#arg1), …, `argN` Optional

Additional arguments which are passed through to the function specified by _func_ once the timer expires.

### [Return value](https://developer.mozilla.org/en-US/docs/Web/API/setInterval#return_value)

The returned `intervalID` is a numeric, non-zero value which identifies the timer created by the call to `setInterval()`; this value can be passed to [`clearInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/clearInterval) to cancel the interval.

It may be helpful to be aware that `setInterval()` and [`setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/setTimeout) share the same pool of IDs, and that `clearInterval()` and [`clearTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/clearTimeout "clearTimeout()") can technically be used interchangeably. For clarity, however, you should try to always match them to avoid confusion when maintaining your code.
