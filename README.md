SALT CSS/HTML Syntax + Style Guide {
==================

SALT is a "mobile-first" site.  The user experience on a mobile device should feel as seamless as on a desktop.  We also want to load only the static resources needed.
Our ability to create changable layouts is based on "The Grid".  Please see the following for an explanation.

http://foundation.zurb.com/docs/components/grid.html

## <a name='TOC'>Table of Contents</a>

  1. [HTML5 Support](#html5)
  2. [General Rules](#general)
  3. [Whitespace](#whitespace)
  4. [!important](#important)
  5. [Selector Naming](#naming)
  6. [File Size and Structure](#structure)
  7. [Available Modules](#modules)
  8. [Creating Buttons](#buttons)
  9. [Understanding SASS](#sass)
  10. [Automated Testing](#testing)

## <a name='html5'>HTML5 Support</a>

In order to provide a consistent experience, we use a plugin "Webshims lib" to provide fallback support for browsers that don't support certain features of HTML5. This allows you to use HTML5 standard markup and validation patterns that will work in these non-compliant browsers (IE9, Safari, etc) out of the box.

For a full list of the features and more info please refer to:

http://afarkas.github.io/webshim/demos/

## <a name='general'>General Rules</a>

No inline styles -- all styles should belong in an external stylesheet

If you are unfamiliar with the box model, do not pass GO, read this: https://developer.mozilla.org/en-US/docs/Web/CSS/box_model

Rule Precedence -- Should be alphabetical

```css
.foo {
  border: 1px solid black;
  color: black;
}
```

## <a name='whitespace'>Whitespace</a>

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

## <a name='important'>!important</a>
Avoid the use of !important.  If you feel you must use it, document the heck out of why you did.

## <a name='naming'>Selector Naming</a>

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

## <a name='structure'>File Size and Structure</a>
Files should be no more than 500 lines, logic permitting
Modules should be organized into files based on their function.
For example, the buttons module can be seen at: http://foolink.com

"If two modules are very similar with only barely noticable changes to stuff like the shadow, padding and colours combine them into one."


## <a name='modules'>SALT CSS Module Structure</a>

  SALT's CSS files are in a modular structure.


  1. Components -- contains modules that should be global to the SALT Site.
      * utilityClasses.css -- helpful classes to ease CSS positioning, alignment, Foundation's hide-for-x classes
      * icons.css -- site-wide CSS code for creating icons
      * typography.css -- web fonts
      * forms.css -- site-wide styling for form elements
      * panels.css -- site-wide CSS for panel styling
      * tiles.css
      * deprecated.css -- legacy code that most likely isn't being used in any HTML, or was being overwritten by other styles. Keeping for now to be safe.
      * toRefactor.css -- Old CSS that should really be refactored along with its HTML and Dust. Most of what's in this file can be re-created with proper use of column nesting, panels, and other Foundation classes.
      * docs.css -- should be refactored into more semantic global modules
      * tooltips.css
      * overlays.css
      * buttons.css
      * orbit.css

  3. Navigation -- CSS for navigation elements
      * header.css
      * navigation.css
      * breadcrumbs.css
  
  5. Themes -- CSS for different sections of the site that have distinct "look and feel", and individual/one-off styling
      * alerts.css -- homepage / Special Alerts
      * alertsOverlay.css -- the old code for when we used to have alerts available as an overlay from the old welcome menu in the header. This can probably be defuncted but it's unclear at this point if we'll want these alerts in an overlay again at some point.
      * basicPage.css -- Default page styling
      * KWYO.css
      * liveChat.css
      * glossary.css
      * lessonsPage.css
      * pressPage.css
      * tools.css
      * vlc.css
      * unauthHomepage.css -- creates styling for all the content sort pages

  Modules yet to be sorted:
    1. colorbox.css -- CSS still used by remaining colorbox modals. Please don't change this unless absolutely necessary. The Login Overlay in the Lessons still needs this CSS.
    2. featuredHeadline.css -- Module for creating the FEATURED section header on the homepage, the Content Type Sort pages, etc.

  

## <a name='buttons'>How To Create Buttons</a>

All basic buttons need to have this basic HTML and CSS structure:

```html
<a class="button base-btn main-btn">See My Loans</a>
```

In this example:
  * .button includes some needed Foundation CSS and provides some overriding of ugly Foundation styles. 
  * .base-btn provides the basic structure and size, font styling
  * .main-btn provides the background color, box shadow, and adds the ">>" characters to make a standard SALT button.

You can include different classes to create variations:
```html
<a class="button base-btn black-btn">See My Loans</a>
```

In this example:
  * .button still provides necessary overrides
  * .base-btn still provides the basic structure and size, font styling
  * .black-btn provides the background color to make a black button.

NOTE: All of the arrows/chevrons in SALT buttons are added through CSS :before and :after pseudo-classes. This means you never have to type the '&lt;' or '&gt;' characters in your HTML for your buttons. Also, the text in SALT buttons is supposed to be lettercase (The First Letter Of Every Word Capitalized). We also do this with CSS, so you should just have your button text HTML following normal English capitalization rules.

**Following these class names and HTML structure will keep all buttons standard and will ease any transitions in any design changes to them in the future**

## <a name='sass'>SASS</a>
  * Pragmatic Sass: http://insideasa.amsa.com/sites/FnctAreas/InfoSvcs/SaltyDawgz/Site%20Documents/pragmatic-guide-to-sass_p1_0.pdf

## <a name='testing'>Integration with Automated Testing</a>
  * In order to make automated testing easier:
    All Buttons, Links, Input Fields, and Dropdowns should have an ID or Class. (TODO add link to naming conventions for classes and ID's)

*Based on the excellent work done by Richard Powell [here](https://github.com/byrichardpowell/CSS-Style)*

}
=
