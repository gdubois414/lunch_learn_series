# Creating Maintainable and Optimized CSS

CSS is one of those things that I always say is easy to learn, but hard to master. When dealing with very small websites or single pages a developer can get away with being careless and making poor decisions to their overall CSS architecture. Unfortunately as projects grow, or are intended to be large-scale these habits can quickly become unmanageable and create issues.

Common pitfalls that happen to inexperienced or careless developers:

* Repeating unnecessary styling options
* Create css selectors that are too specific to the content/design of the page
* Create css selectors that are too narrow in focus
* Create css selectors that are too broad in focus (I know this kind of contradicts the above statement, but it's about finding a balance)
* Relying on !important too much

## Repeating unnecessary styling options

There is an acronym in development known as DRY, or Don't Repeat Yourself. As the phrase suggests, we want to avoid copying/pasting or re-typing as much as possible.

CSS by its very nature is a repetitive language, but there are techniques and patterns that we can use to reduce this. Take the following example:

```css
h2{
	color: blue;
	font-size: 20px;
	text-decoration: underline;		
}
p{
	color: blue;
	font-size: 16px;
	text-decoration: underline;
}
```

We can reduce this by combining the similar properties into the following:

```css
h2, p{
	color: blue;
	text-decoration: underline;
}
h2{
	font-size: 20px;
}
p{
	font-size: 16px;
}
```

## Create css selectors that are too specific to the content/design of the page

At first it is very tempting to look at a design and start writing html/css that is related to the content. This can very quickly get out of hand and become unsemantic. Good designers will want to try and reuse patterns to create a consistent user experience across a website. If we look at beginner developers, we can often times see html that looks like this: `<div class="product-bucket">`, and all child elements are named similarly, e.g "product-title", "product-link", etc. This is often because the first time they saw this particular design element was on a PSD for the product page.

Another common pitfall is creating html/css related to the content, so for a section like "About Us" we might see `<div class="about-us-container">`.

They write all their HTML and CSS too specific on the content or the design of the element in question. They usually start experiencing problems when they find the same design patterns associated with a different section. Now they are faced with potentially three options:

1. Use unsemantic class names, so if we take our "about-us-container" example they repeat that on the Contact or Careers page. This is confusing for developers that might join the project later.
2. Copy/paste all of their CSS into a new class name like "contact-us-container". This is by far the worst option, and ties into the point above. It will not only be confusing, but cause increased bloat in the CSS file, and be impossible to maintain as new pages are created with the same design pattern, or a tweak needs to be made inside the section.
3. Realize their errors and work on refactoring their code to accomodate the different use cases. Unfortunately, not a lot of developers will opt for this path.

A developer must think about the function or purpose of a design element and use that for their naming purposes.

##  Create css selectors that are too narrow/broad in focus

## Relying on !important too much
