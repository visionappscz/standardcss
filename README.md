# standardcss
##CSS Standard Style

###Rules
1. Use 4 spaces for indentation.
  ```css
  h1 {
      color: lime;
  }
  ```

2. Use single quotes.
  ```css
  h1:after {
      content: ' ';
  }
  ```
  
3. Write urls without quotes.
  ```css
  div {
      background-image: url(background.jpg);
  }
  ```
  
4. In attribute selectors, enclose attribute value in quotes.
  ```css
  a[target='_blank'] {
      color: lime;
  }
  ```
  
5. Don’t select via IDs.
  ```css
  // ✓ ok 
  .element {
      color: lime;
  }
  ```
  ```css
  // ✗ avoid 
  #element {
      color: lime;
  }
  ```
  
6. Add a space after selector.
  ```css
  // ✓ ok 
  h1 {
      color: lime;
  }
  ```
  ```css
  // ✗ avoid 
  h1{
      color: lime;
  }
  ```
  
7. Add a space after property name.
  ```css
  // ✓ ok 
  h1 {
      color: lime;
  }
  ```
  ```css
  // ✗ avoid 
  h1 {
      color:lime;
  }
  ```
  
8. Commas should have a space after them.
  ```css
  p {
      font-family: 'Times New Roman', Times, serif;
  }
  ```
  
9. Add a semicolon after every declaration.
  ```css
  h1 {
      color: lime;
      text-align: center // ✗ avoid 
  }
  ```
  
10. Put each declaration on a line.
  ```css
  h1 {
      color: lime;text-align: center; // ✗ avoid
  }
  ```
  
11. Put multiple values on one line each.
  ```css
  h1,
  h2,
  h3 {
      color: lime;
  }
  ```
12. Always put a blank line between rules.
  ```css
  // ✓ ok 
  h1 {
      color: lime;
  }

  p {
      font-family: 'Times New Roman', Times, serif;
  }
  ```
  ```css
  // ✗ avoid
  h1 {
      color: lime;
  }
  p {
      font-family: 'Times New Roman', Times, serif;
  }
  ```
13. Multiple blank lines are not allowed.
  ```css
  // ✓ ok 
  h1 {
      color: lime;
  }

  p {
      font-family: 'Times New Roman', Times, serif;
  }
  ```
  ```css
  // ✗ avoid
  h1 {
      color: lime;
  }


  p {
      font-family: 'Times New Roman', Times, serif;
  }
  ```
