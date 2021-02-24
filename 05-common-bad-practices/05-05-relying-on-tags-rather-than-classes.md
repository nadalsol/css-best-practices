# Relying on tags rather than classes

1. The tags approach
2. The classes approach
3. Conclusions

---

## 1. The tags approach

<!--prettier-ignore-->
```html
<section>
  ...

  <a href="#">
    <h3>Benefits</h3>
    <img src="your-img.png" alt="Your image" />
  </a>
</section>
```

<!--prettier-ignore-->
```scss
section {
  ...

  a {
    ...
  }

  h3 {
    ...
  }

  img {
    ...
  }
}
```

Replaced for…

<!--prettier-ignore-->
```html
<section>
  ...

  <div>
    <a href="#">Benefits</a>
    <img src="your-img.png" alt="Your image" />
  </div>
</section>
```

### Result

Styles would have to be updated as well, to…

<!--prettier-ignore-->
```scss
section {
  ...

  div {
    ...
  }

  a {
    ...
  }

  img {
    ...
  }
}
```

## 2. The classes approach

Let's imagine we had used classes rather than tags, to edit the same component:

<!--prettier-ignore-->
```html
<section class="favs">
  ...

  <a class="favs__card" href="#">
    <h3 class="favs__card-title">Benefits</h3>
    <img class="favs__card-thumb" src="your-img.png" alt="Your image" />
  </a>
</section>
```

<!--prettier-ignore-->
```scss
.favs {
  ...

  &__card {
    ...
  }

  &__card-title {
    ...
  }

  &__card-thumb {
    ...
  }
}
```

Replaced for…

<!--prettier-ignore-->
```html
<section class="favs">
  ...

  <div class="favs__card">
    <a class="favs__card-title" href="#">Benefits</a>
    <img class="favs__card-thumb" src="your-img.png" alt="Your image" />
  </div>
</section>
```

### Result

No line of Sass had to be updated :)

## 3. Conclusions

- Relying on tag or id selectors, rather than classes, might cause styling issues.
- Higher specificity (no good!).
- Bad scalability.
- Less performant.
- More error prone.
