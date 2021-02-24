# Styles copied from design tools

Some devs just copy & paste CSS styles from Zeplin, Figma, or any other design tools.

This is bad practise because:

1. Code is not optimised (no use of short-hand properties, use of absolute values like `px`, etc…).
2. Code is not aimed to be reused (no use of Sass vars for colors, spacing, fonts, etc…)
3. Redundant CSS declarations (i.e. font-family, font-size, etc…) for inherited properties.

## What to do?

1. Write your own optimised CSS code (don't copy & paste!).
2. Use Sass vars and mixins.
3. Use the cascade wisely, for inherited properties.
