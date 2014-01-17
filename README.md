SALT CSS Syntax + Style Guide {
==================

SALT is a "mobile-first" site.  The user experience on a mobile device should feel as seamless as on a desktop.  We also want to load only the static resources needed.
Our ability to create changable layouts is based on "The Grid".  Please see the following for an explanation.

http://foundation.zurb.com/docs/components/grid.html

## General Rules

No inline styles -- all styles should belong in an external stylesheet

If you are unfamiliar with the box model, do not pass GO, read this: https://developer.mozilla.org/en-US/docs/Web/CSS/box_model

Rule Precedence -- Should be alphabetical

```css
.foo {
  border: 1px solid black;
  color: black;
}
```

##Whitespace

* _Never_ mix spaces and tabs for indentation.
* Use tabs (set to a size of 4 spaces)
* One space after selector before opening curly bracket
* After colon, one space before rule
* No one liners

```css
//GOOD
.foo {
  border: 1px solid black;
}

//BAD
.foo{border :1px solid black; color: black;}
```

Tip: configure your editor to "show invisibles" or to automatically remove
end-of-line whitespace.

Tip: use an [EditorConfig](http://editorconfig.org/) file (or equivalent) to
help maintain the basic whitespace conventions that have been agreed for your
code-base.

### !important
Avoid the use of !important.  If you feel you must use it, document the heck out of why you did.

### Selector Naming

Selectors should use dashes in favor of underscores
All words in a selector should be lower case

```css
//GOOD
.foo-bar {
  border: 1px solid black;
}

//BAD
.FOO_bar {
  border: 1px solid black;
}
```

### File Size + Structure
Files should be no more than 500 lines, logic permitting
Modules should be organized into files based on their function.
For example, the buttons module can be seen at: http://foolink.com

"If two modules are very similar with only barely noticable changes to stuff like the shadow, padding and colours combine them into one."


### Available Modules

  In use for Foundation 5 projects:

  1. docs.css contains any of the site-wide CSS overrides
  2. fonts.css contains all of the web fonts in use on SALT. If you ever need to add a font to SALT, create its CSS here.
  3. icons.css -- CSS needed for icons across the site.
  4. colorbox.css -- CSS still used by remaining colorbox modals. Please don't change this unless absolutely necessary
  5. header.css -- CSS for the sitewide header
  6. navigation.css -- code for the footer and mobile footer. Should be split into two modules soon.
  7. buttons.css -- button code. See below for how to use the button classes
  8. KWYO.css -- Styles that are currently specific only to the Know What You Owe tool. As these styles move into the rest of the site design, this CSS file should be refactored into a module that is shared across the site, rather than including KWYO.css on every page of the site.
  

#### How to create buttons on SALT

All basic buttons need to have this basic HTML and CSS structure:

```html
<a class="button base-btn pink-btn">See My Loans &gt;</a>
```

In this example:
  * .button includes some needed Foundation CSS and provides some overriding of ugly Foundation styles. 
  * .base-btn provides the basic structure and size, border radius, font styling
  * .pink-btn provides the background gradient and text shadow to make a standard SALT pink button.

You can include different classes to create variations:
```html
<a class="button base-btn larger-btn black-btn">See My Loans &gt;</a>
```

In this example:
  * .button still provides necessary overrides
  * .base-btn still provides the basic structure and size, border radius, font styling
  * .larger-btn creates a... well, a larger button with padding, font-size and border-radius changes
  * .black-btn provides the background gradient and text shadow to make a black button.
   

  


*Based on the excellent work done by Richard Powell [here](https://github.com/byrichardpowell/CSS-Style)*

}
=
