# CSS

- #### margin

  `margin` is a shorthand property and accepts up to **four values**,shown here:

  .box {
  margin: <margin-top> || <margin-right> || <margin-bottom> || <margin-left>
  }

  

  If fewer than four values are set, **the missing values are assumed based on the ones that are defined**. For example, the following two rule sets would get identical results:
  
  ```css
  .box {
    margin: 0 1.5em;
  }
  
  .box {
    margin: 0 1.5em 0 1.5em;
}
  ```

  Thus, **if only one value is defined, this sets all four margins to the same value**. **If three values are declared, it is** `margin: [top] [left-and-right] [bottom];`.

  
  
  Any of the individual margins can be declared using longhand, in which case you would define only one value per property:
  
  ```css
  .box {
    margin-top: 20px;
    margin-right: 10px;
  margin-bottom: 20px;
    margin-left: 10px;
}
  ```
  
  
  
  Each of the margin properties can also accept a value of `auto`. A value of `auto` basically tells the browser to define the margin for you. In most cases, a value of `auto` will be equivalent to a value of `0` (which is the initial value for each margin property) or else whatever space is available on that side of the element. However, `auto` **is handy for horizontal centering**:
  
```css
  .container {
    width: 980px;
      margin: 0 auto;
}
  ```
  
  In this example, two things are done to center this element horizontally within the available space:
  
  - The element is given a specified width
  
  - The left and right margins are set to `auto`
  
    
  
  **Without the specified width, the** `auto` **values would essentially have no effect**, setting the left and right margins to `0` or else to whatever is the available space inside the parent element.
  
  It should also be pointed out that `auto` **is useful only for horizontal centering**, and so using `auto` for top and bottom margins will not center an element vertically, which can be confusing for beginners.
  
  
  
- #### Collapsing margins
  Vertical margins on different elements that touch each other (thus have no content, padding, or borders separating them) will collapse, forming a single margin that is equal to the **greater** of the adjoining margins. This does **not happen on horizontal margins (left and right),** **only vertical (top and bottom).**

   Although collapsing margins may seem unintuitive at first glance, they are actually useful for a few reasons.

  - First, they prevent empty elements from adding extra, usually undesirable, vertical margin space.

  - Second, they allow for a more consistent approach to declaring universal margins across page elements. For example, headings commonly have vertical margin space, and so do paragraphs. If margins didn't collapse, headings that follow paragraphs (or vice-versa) would often require resetting the margins on one of the elements in order to achieve a consistent amount of vertical spacing.

  - Third, margin collapse also applies to nested elements.