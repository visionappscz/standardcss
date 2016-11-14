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
### Implementation with Stylelint, PostCSS and Grunt
We are using [stylelint](https://github.com/stylelint/stylelint) for easiest implementation 
of standardcss rules. This linter is powered by [PostCSS](https://github.com/postcss/postcss). 
In this example we are going to use [Grunt](http://gruntjs.com/), however you can choose 
any task runner that supports PostCSS. 

You need these npm packages: _stylelint_, _grunt_, _grunt-postcss_ and if you are using any 
CSS preprocessor, you might need supporting PostCSS package. In our example _postcss-less_.

Best practice is to check your CSS before any other tasks process it.

####Installation
1. Install npm packages
2. Include `.stylelintrc` in the root of your directory
3. Prepare Grunt PostCSS task
4. If you are using preprocessor include it in PostCSS task
5. Add stylelint and postcss-reporter (at least with _clearMessages_ option, 
but we recommend _throwError_ also)
6. Add other Grunt tasks to process your CSS
7. Lint your CSS!
8. (Optional) Cry over errors and inconsistencies in your stylesheet
```
lint: {
  options: {
    syntax: require('postcss-less'),
    processors: [
      require('stylelint'),
      require('postcss-reporter')({
        clearMessages: true,
        throwError: true,
      }),
    ],
  },
  src: 'resources/less/**/*.less',
  dest: '.tmp/main.less',
},
  ```