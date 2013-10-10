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


*Based on the excellent work done by Richard Powell [here](https://github.com/byrichardpowell/CSS-Style)*

}
=
