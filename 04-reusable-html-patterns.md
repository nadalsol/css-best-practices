# Reusable HTML patterns

1. The problem: repetition
2. The solution: thinking into patterns
3. Conclusions

---

## 1. The problem: repetition

The bigger a code base is, the more likely is to contain patterns, repeated over and over.

Let's imagine an **image gallery** page –created with [Hugo](https://gohugo.io/templates/introduction/)– using responsive images:

[View in CodePen](https://codepen.io/nadalsol/pen/YzpYRYe)

## 2. The solution: thinking into patterns

As you can see, every `<img srcset="..." src="..." alt="..." class="..." />` might be a reusable pattern.

In "partials/retina-img@3x.html":

[View in CodePen](https://codepen.io/nadalsol/pen/PobExQy)

In "pages/image-gallery.html":

[View in CodePen](https://codepen.io/nadalsol/pen/dyOJQeJ)

## 3. Conclusions

- Repetition makes your front-end code more error prone (the more instances to edit, the worse). [DRY](https://cssguidelin.es/#dry)!
- Don't be greedy: use "patterns/partials/components…". They're free of charge!
- Reusing chunks of code ensures design and code consistency, as well as maintainability and scalability.
- Thinking into components reduce hundreds of lines of code, while makes your code more readable.
