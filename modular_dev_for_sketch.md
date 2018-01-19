# Applying Modular CSS Architecture to Sketch Symbols

As we venture into this crazy thing called Sketch, I want to make sure that we make the absolute most out of it. Sketch has the ability to mimic some concepts that are well known in the development community, and I want to take those concepts and transform them into how they might work in Sketch.

## DRY is one of the most important concepts in development

DRY stands for Don't Repeat Yourself. The guidelines on this vary, some developers will take it to heart and make a specific task repeatable after one instance of copy/pasting, some are a little more lenient. Typically because of the size and short-term development nature of our projects I am a bit more lenient and wait until a second instance of copy/pasting.

To achieve this concept in Sketch we use symobls and text styles. Symbols are pretty flexible and do accept certain properties as overrides. For instance if we create a button symbol with generic text in it, and need one that looks similar, just with different text, we can override the text field.

Common elements that qualify for DRY almost immedietely and should always be made into symbols upon creating.

* Buttons
* Form elements
* Masthead
* Footer
* If there are accompanying chevrons/arrows in many link elements

Sketch also lets us set text styles on any text element in the document. This will save everything, including color, typeface, weight, etc. Almost all text should either be the basis of a text style, or use an existing one. I can't really come up for a reason why a set of text on a page would not use one, unless it was truly a one off usage.

Common use cases for setting a text style

* Body copy
* Non-menu links
* Menu items
* Various levels of page or section headers/titles
* Hero copy - all levels (headline, sub-head, description)
* Have an intro paragraph that needs to pop? Text style.

## Atomic Design

Atomic design is essentially breaking down a page to it's smallest parts. Here is an example:

Full Page
|__ Masthead
   |__ Logo
   |__ Navigation
      |__ Top level items
      |__ Dropdown
          |__ Repeat
   |__ Search Field
      |__ Search Input
      |__ Search Button

Once we have the base theme for the page/website we should be thinking of things in terms of components - or in Sketch, symbols/text styles.

Atomic design lets us create modular components that can be dropped inside other components/containers. An example would be a form. Your smallest components would be your form elements - inputs, submit button, dropdowns, etc. All those would make up a larger form component/symbol. Now we can not only drop a generic form wherever we want, but also individual form elements.

## BEM Syntax

One way that developers keep their CSS under control is not only by using the above techniques, but also implementing a naming syntax known as BEM. It stands for Block Element Modifier.

Block is the base of the component, the outermost wrapper. An element is a child of the base, and a modifier is a variation of the base. For an example, let's take a look at a button that has an icon inside it.

Our Block would be `.button`. Elements extend the block by appending two underscores to the Block. Our icon might have a class of `.button__icon`, and our text might have a class of `.button__text`.

What if we have a variation of our button that is a little larger? That is where the Modifier comes in. This class name is placed at the same level that the modification is occuring. A Modifier extends be base by appending two dashes to the Block. For an overall larger button our wrapping element class would become `.button .button--large`. If we want just the icon bigger then our icon class becomes `.button__icon .button__icon--large`.

This may seem like a lot of typing, but a little bit of extra work up front will prevent a lot of headaches in the future as a project grows or changes.

## General Naming Tips

When naming symbols and text styles we want to avoid these common mistakes

* Naming based on presentation. "Orange Button" sounds kind of silly when all of a sudden it becomes blue. A better name might be "Button Primary".
* Naming based on location. "Home Page Testimonial" makes no sense if the same design pattern is used on pages outside of the home page. A different name might be "Featured Testimonial"
* Another example of location mis-naming would be "Search Input" when the same design style is used in non-search forms.

In general you want to name components based off of the function or purpose that they serve. We can get creative with naming as long as it makes sense. In one talk at the Smahing Conference that I went to an example they used was for a section that's purpose was to really stand out in the middle or end of the page promoting something else. Their organization decided to call it a "Boombox" because it is supposed to be loud and catch your attention.

Naming things does not have to rely solely on the developer or an individual. It can be a group effort. Over time we will have common components across websites that do not need a discussion (for instance, hero or masthead), but new components should be open to discussion.