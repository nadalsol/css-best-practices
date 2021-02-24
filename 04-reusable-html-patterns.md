# Reusable HTML patterns

1. The problem: repetition
2. The solution: thinking into patterns
3. Conclusions

---

## 1. The problem: repetition

The bigger a code base is, the more likely is to contain patterns, repeated over and over.

Let's imagine an **image gallery** page –created with [Hugo](https://gohugo.io/templates/introduction/)– using responsive images:

```html
<section>
  <div class="bx--grid">
    <div class="bx--row">
      <div class="bx--col-md-4 bx--col-lg-4">
        <img
          srcset="
            /images/gallery/01.jpg    1x,
            /images/gallery/01@2x.jpg 2x,
            /images/gallery/01@3x.jpg 3x
          "
          src="/images/gallery/01.jpg"
          alt="01"
          class="o-img-responsive-full"
        />
      </div>

      <div class="bx--col-md-4 bx--col-lg-4">
        <img
          srcset="
            /images/gallery/02.jpg    1x,
            /images/gallery/02@2x.jpg 2x,
            /images/gallery/02@3x.jpg 3x
          "
          src="/images/gallery/02.jpg"
          alt="02"
          class="o-img-responsive-full"
        />
      </div>

      <div class="bx--col-md-4 bx--col-lg-4">
        <img
          srcset="
            /images/gallery/03.jpg    1x,
            /images/gallery/03@2x.jpg 2x,
            /images/gallery/03@3x.jpg 3x
          "
          src="/images/gallery/03.jpg"
          alt="03"
          class="o-img-responsive-full"
        />
      </div>

      <div class="bx--col-md-4 bx--col-lg-4">
        <img
          srcset="
            /images/gallery/04.jpg    1x,
            /images/gallery/04@2x.jpg 2x,
            /images/gallery/04@3x.jpg 3x
          "
          src="/images/gallery/04.jpg"
          alt="04"
          class="o-img-responsive-full"
        />
      </div>

      <div class="bx--col-md-4 bx--col-lg-4">
        <img
          srcset="
            /images/gallery/05.jpg    1x,
            /images/gallery/05@2x.jpg 2x,
            /images/gallery/05@3x.jpg 3x
          "
          src="/images/gallery/05.jpg"
          alt="05"
          class="o-img-responsive-full"
        />
      </div>

      <div class="bx--col-md-4 bx--col-lg-4">
        <img
          srcset="
            /images/gallery/06.jpg    1x,
            /images/gallery/06@2x.jpg 2x,
            /images/gallery/06@3x.jpg 3x
          "
          src="/images/gallery/06.jpg"
          alt="06"
          class="o-img-responsive-full"
        />
      </div>
    </div>
  </div>
</section>
```

## 2. The solution: thinking into patterns

As you can see, every `<img srcset="..." src="..." alt="..." class="..." />` might be a reusable pattern.

In "partials/retina-img@3x.html":

<!-- prettier-ignore -->
```html
<img
  srcset="
    {{ with .path }}{{ .| urlize }}{{ end }}{{ with .name }}{{ .| urlize }}{{ end }}.{{ with .ext }}{{ . }}{{ end }}    1x,
    {{ with .path }}{{ .| urlize }}{{ end }}{{ with .name }}{{ .| urlize }}{{ end }}@2x.{{ with .ext }}{{ . }}{{ end }} 2x,
    {{ with .path }}{{ .| urlize }}{{ end }}{{ with .name }}{{ .| urlize }}{{ end }}@3x.{{ with .ext }}{{ . }}{{ end }} 3x
  "
  src="{{ with .path }}{{ .| urlize }}{{ end }}{{ with .name }}{{ .| urlize }}{{ end }}.{{ with .ext }}{{ . }}{{ end }}"
  {{ with .name }}alt="{{ . }}"{{ end }}
  {{ with .class }}class="{{ . }}"{{ end }}
/>
```

In "pages/image-gallery.html":

<!-- prettier-ignore -->
```html
<section>
  <div class="bx--grid">
    <div class="bx--row">
      <div class="bx--col-md-4 bx--col-lg-4">
        {{ partial "retina-img@3x.html" (dict "path" "/images/gallery/" "name" "01" "ext" "jpg" "class" "o-img-responsive-full" ) }}
      </div>

      <div class="bx--col-md-4 bx--col-lg-4">
        {{ partial "retina-img@3x.html" (dict "path" "/images/gallery/" "name" "02" "ext" "jpg" "class" "o-img-responsive-full" ) }}
      </div>

      <div class="bx--col-md-4 bx--col-lg-4">
        {{ partial "retina-img@3x.html" (dict "path" "/images/gallery/" "name" "03" "ext" "jpg" "class" "o-img-responsive-full" ) }}
      </div>

      <div class="bx--col-md-4 bx--col-lg-4">
        {{ partial "retina-img@3x.html" (dict "path" "/images/gallery/" "name" "04" "ext" "jpg" "class" "o-img-responsive-full" ) }}
      </div>

      <div class="bx--col-md-4 bx--col-lg-4">
        {{ partial "retina-img@3x.html" (dict "path" "/images/gallery/" "name" "05" "ext" "jpg" "class" "o-img-responsive-full" ) }}
      </div>

      <div class="bx--col-md-4 bx--col-lg-4">
        {{ partial "retina-img@3x.html" (dict "path" "/images/gallery/" "name" "06" "ext" "jpg" "class" "o-img-responsive-full" ) }}
      </div>
    </div>
  </div>
</section>
```

## 3. Conclusions

- Repetition makes your front-end code more error prone (the more instances to edit, the worse). [DRY](https://cssguidelin.es/#dry)!
- Don't be greedy: use "patterns/partials/components…". They're free of charge!
- Reusing chunks of code ensures design and code consistency, as well as maintainability and scalability.
- Thinking into components reduce hundreds of lines of code, while makes your code more readable.
