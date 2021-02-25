# Relying on tags rather than classes

1. [The tags approach](#1-the-tags-approach)
2. [The classes approach](#2-the-classes-approach)
3. [Conclusions](#3-conclusions)

---

## 1. The tags approach

Taking this component as an example, replace `button` for `a` and see what happens…

👨🏻‍💻 [View on CodePen](https://codepen.io/nadalsol/pen/jOVYXqq)

### Result

Button styles would be broken :(

## 2. The classes approach

Let's imagine we had used classes rather than tags, to edit the same component…

👨🏻‍💻 [View on CodePen](https://codepen.io/nadalsol/pen/PobEVpW)

### Result

No line of Sass has to be updated :)

## 3. Conclusions

- Relying on tag or id selectors, rather than classes, might cause styling issues.
- Higher specificity (no good!).
- Bad scalability.
- Less performant.
- More error prone.
