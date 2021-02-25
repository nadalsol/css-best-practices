# BEM methodology

1. What is BEM?
2. Writting BEM with Sass
3. Conclusions
4. Recommended reads

---

## 1. What is BEM?

For larger, more interrelated pieces of UI that require a number of classes, BEM-like naming convention is helpful. BEM, stands for _Block, Element, Modifier_.

BEM splits components’ classes into three groups:

- **Block:** The sole root of the component.
- **Element:** A component part of the Block.
- **Modifier:** A variant or extension of the Block.

We can take back our previous card as an example:

👨🏻‍💻 [View on CodePen](https://codepen.io/nadalsol/pen/vYypRgp)

It is important to know when BEM scope starts and stops. As a rule, **BEM applies to self-contained, discrete parts of the UI.**

### Incorrect notation

<!--prettier-ignore-->
```scss
.page {}
  .page__header {}
  .page__content {}
  .page__footer {}
    .page__copyright {}
```

👨🏻‍💻 [View on CodePen](https://codepen.io/nadalsol/pen/bGBavZX)

### Good notation

<!--prettier-ignore-->
```scss
.page {}
.header {}
.content {}
.footer {}
  .footer__copyright {}
```

👨🏻‍💻 [View on CodePen](https://codepen.io/nadalsol/pen/XWNVqgV)

## 2. Writting BEM with Sass

Make use of Sass’ parent selector, to avoid writing our block over and over (which is error prone):

### Not ideal

👨🏻‍💻 [View on CodePen](https://codepen.io/nadalsol/pen/RwoxyLz)

### Much better

👨🏻‍💻 [View on CodePen](https://codepen.io/nadalsol/pen/zYopjVm)

This is general good practice when dealing with nested code: keep all of your context (e.g. all `.card__title {}` code) encapsulated in one location:

### Not ideal

👨🏻‍💻 [View on CodePen](https://codepen.io/nadalsol/pen/yLVpEej)

### Much better

👨🏻‍💻 [View on CodePen](https://codepen.io/nadalsol/pen/XWNVYXy)

The CSS output will be the same as in the previous example, but keeping `.card__title {}` context encapsulated in our Sass file.

## 3. Conclusions

- BEM is a smart way of naming your CSS classes, to give them more transparency and meaning to other developers.
- BEM makes code easier to maintain by teams, or even just by yourself a few months down the line.
- BEM helps identifying different HTML patterns at a glance.

> BEM is a highly useful, powerful and simple naming convention to make your front-end code easier to read and understand, easier to work with, easier to scale, more robust and explicit and a lot more strict.
> – Harry Roberts

## 4. Recommended reads

- [MindBEMding – getting your head ’round BEM syntax](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
- [cssguidelin.es > BEM-like Naming](https://cssguidelin.es/#bem-like-naming)
