# Nesting selectors with no reason

This is pretty common, specially when using CSS preprocessors like Sass or Less.

As we mentioned in the CSS Specificity section, this is bad practise because:

- Increments our selectors specificity, with no reason.
- Makes CSS harder to mantain, difficult to read and to debug, leading to errors and incosistencies.
- This is how the **specificity wars begins** and trust me, it never ends!

## What to do?

- Don’t nest selectors unless absolutely necessary.
