# Mobile vs desktop first approach

1. The "mobile-first" approach
2. The "desktop-first" approach
3. Why Code "mobile-first"?
4. Conclusions
5. Recommended reads

---

## 1. The "mobile-first" approach

A "mobile-first" approach to styling means that styles are applied first to mobile devices. Advanced styles and other overrides for larger screens are then added into the stylesheet via media queries.

This approach uses `min-width` media queries.

Here’s a quick example:

[View in CodePen](https://codepen.io/nadalsol/pen/WNodLvv)

## 2. The "desktop-first" approach

On the flipside, a "desktop-first" approach means that styles are applied first to desktop devices. Advanced styles and overrides for smaller screens are then added into the stylesheet via media queries.

This approach uses `max-width` media queries.

Here’s a quick example:

[View in CodePen](https://codepen.io/nadalsol/pen/rNWpoWz)

## 3. Why Code "mobile-first"?

Code for larger screens is usually more complicated than the codes for smaller screens. This is why **coding "mobile-first" helps simplify your code**.

If we go with the desktop-first approach instead, we will have to restore the default properties for smaller viewports most of the time (not good!).

## 4. Conclusions

- Follow the "mobile-first" approach, using `min-width` media queries, for more performant and scalable stylesheets.
- A lot of developers still use the `max-width` ("desktop-first") approach in 2021. Please, don't do that!

## 5. Recommended reads

- [Mobile First, by Luke Wroblewski](http://mobile-first.abookapart.com/)
- [How To Write Mobile-first CSS](https://zellwk.com/blog/how-to-write-mobile-first-css/)
