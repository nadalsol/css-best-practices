# Hard to read media queries

1. [The "hard to read" way (common but undesirable)](#1-the-hard-to-read-way-common-but-undesirable)
2. [The "keep in context" way (pretty useful)](#2-the-keep-in-context-way-pretty-useful)
3. [Conclusions](#3-conclusions)

---

According to [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries):

> Media queries are useful when you want to modify your site or app depending on a device's general type (such as print vs. screen) or specific characteristics and parameters (such as screen resolution or browser viewport width).

## 1. The "hard to read" way (common but undesirable)

👨🏻‍💻 [View on CodePen](https://codepen.io/nadalsol/pen/NWbXeKW)

## 2. The "keep in context" way (pretty useful)

👨🏻‍💻 [View on CodePen](https://codepen.io/nadalsol/pen/wvopRMw)

## 3. Conclusions

- Write your `@media` declarations within your selectors, in sake of developer experience (readability and maintainability in Sass files).
- The "keep in context" technique is very good practise, specially for long partials.
- The "keep in context" technique is slightly less performant (more lines of CSS generated in the output), though this is not a problem if you unify, minify and gzip your CSS builds.
- If last point is an issue for you, install a plugin like [PostCSS Sort Media Queries](https://github.com/solversgroup/postcss-sort-media-queries) to combine and sort CSS media queries with "mobile-first" approach.
