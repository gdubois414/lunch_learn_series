# Intro to Front-End Development Part 1

## The Basics

A web page is typically made up of the following parts:

* HTML is used to make the structure of the page, and house the content
* CSS is used to style the page per the files provided by the designer
* Javascript is used to provide interaction on the page, whether it is through clicking, scrolling, or resizing (just to name a few)

If we make the analogy of a web page to a house we can say the following:

* HTML would be things like walls, floors, ceiling, and furniture
* CSS would control things like the color of the walls, decorations, and style of furniture
* Javascript would control functions like turning on water faucets, opening doors, and turning on the TV

For this series we will just be going over HTML and CSS

## HTML

HTML (Hypertext Markup Language) is a standard that incorporates tags. A tag is meant to show structure. There are quite a few, but some of the most common ones are:

* <p></p>
* <div></div>
* <h1></h1>
* <a></a>

You can see in the above examples that they follow a general format. This is opening bracket "<", the name of the tag "p, h1, div, etc", closing bracket ">". The content would go after what is known as the "opening tag". Once the content is complete, you follow the same pattern, but include a "/" to signify that you are closing the tag. There are some exceptions to this format, but we will cover those later.

Tags can go inside other tags almost indefinitely. For example we can have the following structure:

`<p>This is a paragraph with a <a>link</a> inside of it</p>`

Tags can have attributes, and some of them require specific attributes to exist. An `<img>` tag needs a "src" attribute to define the file name. Not all attributes apply to every type of tag. The "src" attribute will mean nothing in a tag like `<p>`. It might seem like a lot to remember, but you will catch on pretty quickly.

## CSS

CSS (Cascading StyleSheets) is how we control the look and feel of a page. While we can apply css directly onto an element using the "style" attribute (ex: `<p style="css_goes_here"></p>`), it is typically frowned upon. We want to avoid using inline style attributes because eventually they become unmanageable, and we will end up repeating ourselves a lot. Developers hate repeating themselves, in fact there is an acroynm for it - DRY (Don't Repeat Yourself) - that any developer will live by.

To keep everything DRY we use attributes called "class" or "id". So now our above example becomes `<p class="css_class_name"></p>`. The class attribute will correlate with a matching definition in a CSS file. Now, any element that uses the class name "css_class_name" will look the same. If we need to update how it looks we need to only make the change in one place, rather than several, keeping our code DRY.

When we write CSS in a separate file it will typically look like this:

```CSS
.class_name {
    color: white;
    font-size: 16px;
}
```

Breaking the above down, we get the following:

* ".class_name" is our identifier that matches with the class attribute in our HTML. This is known as a "selector".
* That is followed by an opening curly brace.
* Inside the curly braces we have a set of "declarations", one on each line.
* Declarations are comprised of a "Property" and a "Property Value".
* At the end of the declrations we use a closing curly brace.