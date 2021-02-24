# Repeating yourself

This is another common mistake: writing HTML & CSS quickly, repeating a lot of code.

This is bad practise because:

1. Not taking time to identify common patterns, results in redundant HTML patterns and CSS declarations.
2. Not making use of Sass variables and mixins, results in less consistent, optimised and harder to mantain code.

## What to do?

1. Identify patterns with [Atomic Design](https://atomicdesign.bradfrost.com/table-of-contents/).
2. [DRY](https://cssguidelin.es/#dry)! (use Sass variables and mixins, to promote reusability and keep code redundancy lower).
