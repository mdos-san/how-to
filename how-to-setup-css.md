# CSS

### BEM

Use BEM methodology: https://css-tricks.com/bem-101/

### PostCSS

Use PostCSS : https://postcss.org/

### CSS Class variables

When using a CSS Variable to allow customisation and reusablitity, respect the following:

  * Variable name should be inspired from the BEM format `--<bem-block>__<bem-element>--<bem-modifier>--<css-attribute>`
    * Ex: `--card--box-shadow`, `--card__actions__action--background-color`, `--card__title--big--font-size`,

### CSS Design system variables

Sometimes CSS variables are not bound to a specific class, in those cases, respect the following:
  
  * Use modifier from BEM to define multiple related element from a design system
    * Ex: `--color--accent`, `--color--sucess`, `--border--default`, `--border--light`
  * Try to simplify as much as possible variable name, the more it's close to CSS already present attribute, the better
    * Ex DO NOT: `--text-paragraph-color`, `--size-of-page`
    * Ex Do instead: `--color--paragraph`, `--width--page`
  * Sometimes a variable is not really a `Design System` variable
    * Ex : In previous point `page` can be a standalone CSS class, and by be customisable via CSS variable `--page--width`
    * Here's some design system variable: `--color`, `--font-family`, `--box-shadow` ...

### CSS Reusability

When developping your CSS classes, you may want to allow reusability. You should respect the following :

  * Avoid as much as possible layout style in your component
    * Ex: A `.card` class should not define a `margin` style, instead use a wrapper to do this.
  * Use as much as possible CSS variable to allow customisation.
    * Ex: Your `.card` class may use a CSS Variable for `background-color`, `height`, `width`, etc...
  * Specificity of you component should be reduced as much as possible to allow override when used.
    * Ex: We have a custom CSS lib and a **TodoAPP**. In **TodoAPP** we add the class `.todo-app` on the `<body>` tag, and override the `.card` class with `.todo-app .card`
