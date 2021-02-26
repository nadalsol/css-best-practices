# BEM methodology

1. [What is BEM?](#1-what-is-bem)
2. [Writting BEM with Sass](#2-writting-bem-with-sass)
3. [Conclusions](#3-conclusions)
4. [Recommended reads](#4-recommended-reads)

---

## 1. What is BEM?

<img src="./img/bem.png" alt="BEM" />

**BEM**, stands for **Block, Element, Modifier**.

For larger, more interrelated pieces of UI that require a number of classes, BEM-like naming convention is helpful, sppliting components’ classes into three groups:

- **Block:** The sole root of the component.
- **Element:** A component part of the Block.
- **Modifier:** A variant or extension of the Block.

<!--prettier-ignore-->
```scss
.block {}
.block__element {}
.block--modifier {}
```

### Example 01

We can take back our previous card as an example:

👨🏻‍💻 [Example 01 (CodePen)](https://codepen.io/nadalsol/pen/vYypRgp)

### Example 02a (incorrect notation)

<!--prettier-ignore-->
```scss
.page {}
  .page__header {}
  .page__content {}
  .page__footer {}
    .page__copyright {}
```

👨🏻‍💻 [Example 02a (CodePen)](https://codepen.io/nadalsol/pen/bGBavZX)

### Example 02b (good notation)

<!--prettier-ignore-->
```scss
.page {}
.header {}
.content {}
.footer {}
  .footer__copyright {}
```

👨🏻‍💻 [Example 02b (CodePen)](https://codepen.io/nadalsol/pen/XWNVqgV)

> It is important to know when BEM scope starts and stops. As a rule, **BEM applies to self-contained, discrete parts of the UI.**
>
> – Harry Roberts

## 2. Writting BEM with Sass

### Example 03

Make use of **Sass’ parent selector**, to avoid writing our block over and over (which is error prone):

- not ideal: 👨🏻‍💻 [Example 03a (CodePen)](https://codepen.io/nadalsol/pen/RwoxyLz)
- much better: 👨🏻‍💻 [Example 03b (CodePen)](https://codepen.io/nadalsol/pen/zYopjVm)

### Example 04

This is general good practice when dealing with nested code: **keep all of your context encapsulated in one location**:

- not ideal: 👨🏻‍💻 [Example 04a (CodePen)](https://codepen.io/nadalsol/pen/yLVpEej)
- much better: 👨🏻‍💻 [Example 04b (CodePen)](https://codepen.io/nadalsol/pen/XWNVYXy)

The CSS output will be the same in both cases, but keeping `.card__title {}` context encapsulated in our Sass file is better!

## 3. Conclusions

> BEM is a highly useful, powerful and simple naming convention to make your front-end code easier to read and understand, easier to work with, easier to scale, more robust and explicit and a lot more strict.
>
> – Harry Roberts

BEM is also…

- A smart way of naming your CSS classes, to give them more transparency and meaning to other developers.
- Makes code easier to maintain by teams, or even just by yourself a few months down the line.
- Helps identifying different HTML patterns at a glance.

## 4. Recommended reads

- [Get BEM > Naming](http://getbem.com/naming/)
- [MindBEMding – getting your head ’round BEM syntax](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
- [cssguidelin.es > BEM-like Naming](https://cssguidelin.es/#bem-like-naming)
