# Long files

Long stylesheets are a pain in the ass: harder to mantain, harder to read, more error prone…

To prevent this problem, avoid writing your styles in an endless/single CSS file.

MISSING IMG (long CSS file)

MISSING IMG (Sass partial)

## What to do?

- Split your stylesheets into smaller parts with [Sass partials](https://sass-lang.com/documentation/at-rules/import#partials), in sake of readability and maintainability. Sass **partials** are basically a way to split your stylesheets into **smaller, reusable chunks of code**. They're free of charge!
- Think into reusable code patterns.
- [Atomic Design](https://atomicdesign.bradfrost.com/table-of-contents/) to the rescue!
