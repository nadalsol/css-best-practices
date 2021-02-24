# Hard to Read Media Queries

1. The "hard to read" way (common but undesirable)
2. The "keep in context" way (pretty useful)
3. Conclusions

---

According to [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries):

> Media queries are useful when you want to modify your site or app depending on a device's general type (such as print vs. screen) or specific characteristics and parameters (such as screen resolution or browser viewport width).

## 1. The "hard to read" way (common but undesirable)

```scss
body {
  background: red;
}

.first-class {
  color: blue;
}

.second-class {
  color: orange;
}

.third-class {
  color: purple;
}

@media (min-width: 600px) {
  body {
    background: green;
  }

  .first-class {
    color: beige;
  }

  .second-class {
    color: yellow;
  }

  .third-class {
    color: pink;
  }
}
```

### CSS output

Same as in Scss file above.

## 2. The "keep in context" way (pretty useful)

```scss
body {
  background: red;

  @media (min-width: 600px) {
    background: green;
  }
}

.first-class {
  color: blue;

  @media (min-width: 600px) {
    color: beige;
  }
}

.second-class {
  color: orange;

  @media (min-width: 600px) {
    color: yellow;
  }
}

.third-class {
  color: purple;

  @media (min-width: 600px) {
    color: pink;
  }
}
```

### CSS output

```css
body {
  background: red;
}

@media (min-width: 600px) {
  body {
    background: green;
  }
}

.first-class {
  color: blue;
}

@media (min-width: 600px) {
  .first-class {
    color: beige;
  }
}

.second-class {
  color: orange;
}

@media (min-width: 600px) {
  .second-class {
    color: yellow;
  }
}

.third-class {
  color: purple;
}

@media (min-width: 600px) {
  .third-class {
    color: pink;
  }
}
```

## 3. Conclusions

- Write your `@media` declarations within your selectors, in sake of developer experience (readability and maintainability in Sass files).
- The "keep in context" technique is very good practise, specially for long partials.
- The "keep in context" technique is slightly less performant (more lines of CSS generated in the output), though this is not a problem if you unify, minify and gzip your CSS builds.
- If last point is an issue for you, install a plugin like [PostCSS Sort Media Queries](https://github.com/solversgroup/postcss-sort-media-queries) to combine and sort CSS media queries with "mobile-first" approach.
