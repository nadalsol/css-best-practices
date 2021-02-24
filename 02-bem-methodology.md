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

<!--prettier-ignore-->
```html
<div class="card">
  <div class="card__title">
    <h2>Hello card!</h2>
  </div>

  <div class="card__content">
    <img class="avatar" src="https://placekitten.com/200/200" alt="Kitten" />
  </div>

  <div class="card__actions">
    <button class="btn">Submit<button>
  </div>
</div>
```

<!--prettier-ignore-->
```scss
.card {} // block
.card__title {} // element 1
.card__content {} // element 2
.card__actions {} // element 3...
.card--prominent { background-color: pink; } // modifier
```

It is important to know when BEM scope starts and stops. As a rule, **BEM applies to self-contained, discrete parts of the UI.**

### Incorrect notation

<!--prettier-ignore-->
```scss
.page {}
  .page__content {}
  .page__sub-content {}
  .page__footer {}
    .page__copyright {}
```

### Good notation

<!--prettier-ignore-->
```scss
.page {}
.content {}
.sub-content {}
.footer {}
  .footer__copyright {}
```

## 2. Writting BEM with Sass

Make use of Sass’ parent selector, to avoid writing our block over and over (which is error prone):

### Not ideal

<!--prettier-ignore-->
```scss
// block
.card {
  padding: 2rem;
  background-color: beige;
}

// element/s
.card__title {}
.card__content {}
.card__actions {}

// modifier/s
.card--prominent {
  background-color: pink;
}
```

### Much better

<!--prettier-ignore-->
```scss
// block
.card {
  padding: 2rem;
  background-color: beige;

  // element/s
  &__title {}
  &__content {}
  &__actions {}

  // modifier/s
  &--prominent {
    background-color: pink;
  }
}
```

This is general good practice when dealing with nested code: keep all of your context (e.g. all `.card__title {}` code) encapsulated in one location:

### Not ideal

<!--prettier-ignore-->
```scss
.card {
  padding: 2rem;
  background-color: beige;

  &__title {
    color: black;
  }
}

.card--prominent {
  background-color: pink;

  &__title {
    color: red;
  }
}
```

### Much better

```scss
.card {
  padding: 2rem;
  background-color: beige;

  &--prominent {
    background-color: pink;
  }

  &__title {
    color: black;

    &--prominent & {
      color: red;
    }
  }
}
```

The CSS output will be the same as in the previous example, but keeping `.card__title {}` context encapsulated in our Sass file.

### CSS output

```css
.card {
  padding: 2rem;
  background-color: beige;
}

.card__title {
  color: black;
}

.card--prominent {
  background-color: pink;
}

.card--prominent .card__title {
  color: red;
}
```

## 3. Conclusions

- BEM is a smart way of naming your CSS classes, to give them more transparency and meaning to other developers.
- BEM makes code easier to maintain by teams, or even just by yourself a few months down the line.
- BEM helps identifying different HTML patterns at a glance.

> BEM is a highly useful, powerful and simple naming convention to make your front-end code easier to read and understand, easier to work with, easier to scale, more robust and explicit and a lot more strict.
> – Harry Roberts

## 4. Recommended reads

- [MindBEMding – getting your head ’round BEM syntax](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
- [cssguidelin.es > BEM-like Naming](https://cssguidelin.es/#bem-like-naming)
