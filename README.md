# SASS Color Range
Calculate a random colour within a range of an input colour.

Bonus: Apply the most contrasting text colour for the element.

## Usage
There are two files included in the project.

### color-range.scss

This is a Sass function which returns a randomised colour within a narrow range of a given input colour.

Call it in your SCSS via:

    .element
    {
        background: color_range($color);
    }

where `$color` is the input colour you want to base the range upon.

### color-range-contrast.scss

This is a set of mixins & a function which use [voxpelli's SASS Color Contrast](https://gist.github.com/voxpelli/6304812) ratio scripts.
Given an input colour (as before) and a selection of two or more text colours (eg. a primary and secondary colour), it will set the background colour to a randomised colour & ensure that the text above is of a high enough contrast to be easily read. 

**_Note: You must include the color-range.scss file & both of voxpelli's SASS Color Contrast files for the code to compile._**

Call it in your SCSS via:

    .element
    {
        @include color-range($color, ($primary-text, $alternate-text[, $alternate-text2, ...]));
    }

where `$primary-text` is the colour you would like your text to be and `$alternate-text` is an alternative colour for the text. Further alternate text colours can optionally be added.

In addition, this file also includes a second mixin which introduces a second input colour. This is an optional parameter - if it is not entered then a complementary colour will be chosen by the system. The output of the mixin will randomly choose between the primary and the secondary colours.

Call it in your SCSS via:

    .element
    {
        @include color-range($color, ($primary-text, $alternate-text[, $alternate-text2, ...])[, $secondary-color]);
    }

where `$secondary-color` is an optional second input colour.
