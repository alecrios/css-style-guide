# CSS Style Guide

&nbsp;

[**General**](#general)
* [Tab indentation](#tab-indentation)
* [No whitespace at ends of lines](#no-whitespace-at-ends-of-lines)
* [Newline at end of file](#newline-at-end-of-file)

[**Rules**](#rules)
* [One space before opening brace](#one-space-before-opening-brace)
* [Closing brace on new line](#closing-brace-on-new-line)
* [One blank line between rules](#one-blank-line-between-rules)
* [Condensed format for alignment](#condensed-format-for-alignment)

[**Selectors**](#selectors)
* [One selector per line](#one-selector-per-line)
* [Class names in kebab-case](#class-names-in-kebab-case)
* [No tags or IDs in selectors](#no-tags-or-ids-in-selectors)
* [Meaningful and generic class names](#meaningful-and-generic-class-names)

[**Properties**](#properties)
* [One property per line](#one-property-per-line)
* [LSB property ordering](#lsb-property-ordering)
* [No space before colon, one space after](#no-space-before-colon-one-space-after)
* [Semicolon after every property value](#semicolon-after-every-property-value)

[**Values**](#values)
* [Double-quoted strings](#single-quoted-strings)
* [Unitless zero values](#unitless-zero-values)
* [RGBA color values](#rgba-color-values)
* [No leading zero on decimals](#no-leading-zero-on-decimals)
* [No space after comma in value functions](#no-space-after-comma-in-value-functions)
* [One space after comma in value lists](#one-space-after-comma-in-value-lists)

[**At-Rules**](#at-rules)
* [Mobile-first media queries](#mobile-first-media-queries)
* [Nearby media queries](#nearby-media-queries)

[**Comments**](#comments)
* [Hierarchical heading system](#hierarchical-heading-system)
* [Appropriate capitalization](#appropriate-capitalization)

&nbsp;

## General

### Tab indentation

Lines should be indented with tabs as opposed to spaces.

### No whitespace at ends of lines

Code should be neat and clean without unnecessary whitespace characters.

### Newline at end of file

Files should always end with a single LF newline character.

&nbsp;

## Rules

### One space before opening brace

A space between the selector and the brace increases readability.

``` css
/* Wrong */

.too-tight{
	color: rgba(255,0,0,1);
}

/* Right */

.just-right {
	color: rgba(0,255,0,1);
}
```

### Closing brace on new line

The brace on its own line makes for easier editing and cleaner git diffs

``` css
/* Wrong */

.wrong-spot {
	color: rgba(255,0,0,1);}

/* Right */

.right-spot {
	color: rgba(0,255,0,1);
}
```

### One blank line between rules

A blank line increases readability.

``` css
/* Wrong */

.cramped {
	font-size: 16px;
	color: rgba(255,0,0,1);
}
.crowded {
	background-color: rgba(255,0,0,1);
}

/* Right */

.breathable {
	font-size: 16px;
	color: rgba(0,255,0,1);
}

.spacious {
	background-color: rgba(0,255,0,1);
}
```

### Condensed format for alignment

For a set of single-property rules declaring the same property, aligning them with each other without empty lines in-between makes it easier to compare values.

``` css
/* Wrong */

.small {
	font-size: 12px;
}

.medium {
	font-size: 16px;
}

.large {
	font-size: 20px;
}

/* Right */

.small  {font-size: 12px;}
.medium {font-size: 16px;}
.large  {font-size: 20px;}
```

&nbsp;

## Selectors

### One selector per line

A new line makes it more clear that the following selector is separate and not a descendent.

``` css
/* Wrong */

.two-selectors, .one-line {
	color: rgba(255,0,0,1);
}

/* Right */

.two-selectors,
.two-lines {
	color: rgba(0,255,0,1);
}
```

### Class names in kebab-case

CSS properties are written in kebab-case, so class names should follow suit.

``` css
/* Wrong */

.camelCase {
	background-color: rgba(255,0,0,1);
}

/* Right */

.kebab-case {
	background-color: rgba(0,255,0,1);
}
```

### No tags or IDs in selectors

To mitigate specificity issues, all selectors should consist only of classes.

``` css
/* Wrong */

.low-specificity a {
	color: rgba(255,0,0,1);
}

#high-specificity .link {
	color: rgba(255,0,0,1);
}

/* Right */

.normal-specificity .link {
	color: rgba(0,255,0,1);
}
```

### Meaningful and generic class names

Improves clarity and prevents having to rename classes if there's a change in style.

``` css
/* Wrong */

.th-lft-256 {
	float: left;
	max-width: 256px;
}

.button-blue {
	color: rgba(0,0,255,1);
}

/* Right */

.image-thumbnail {
	float: left;
	max-width: 256px;
}

.button-primary {
	color: rgba(0,0,255,1);
}


```

&nbsp;

## Properties

### One property per line

Writing multiple properties on a single line reduces readability.

``` css
/* Wrong */

.hard-to-scan {
	top: 0; left: 0;
}

/* Right */

.easy-to-scan {
	top: 0;
	left: 0;
}
```

### LSB property ordering

Layout-Style-Behavior property ordering is a simple way to organize a rule to make it easier to read.

* **Layout:** `position`, `display`, `width`, `margin`, `padding`, etc.
* **Style:** `font`, `line-height`, `color`, `background`, etc.
* **Behavior:** `transition`, `cursor`, `pointer-events`, etc.

``` css
/* Wrong */

.randomly-ordered {
	color: rbga(255,255,255,1);
	transition: transform 1s ease-out;
	cursor: pointer;
	padding: 32px;
	position: absolute;
	background-color: rbga(0,255,0,1);
}

/* Right */

.logically-ordered {
	position: absolute;
	padding: 32px;
	background-color: rbga(0,255,0,1);
	color: rbga(255,255,255,1);
	transition: transform 1s ease-out;
	cursor: pointer;
}
```

### No space before colon, one space after

This configuration is most readable, because this is how it is used in the English language.

``` css
/* Wrong */

.too-tight {
	display:block;
}

.too-loose {
	display : block;
}

/* Right */

.just-right {
	display: block;
}
```

### Semicolon after every property value

Always including the semicolon prevents errors when reordering properties.

``` css
/* Wrong */

.without-last-semicolon {
	display: block;
	margin-bottom: 16px;
	padding: 16px
}

/* Right */

.with-last-semicolon {
	display: block;
	margin-bottom: 16px;
	padding: 16px;
}
```

&nbsp;

## Values

### Double-quoted strings

``` css
/* Wrong */

.not-quoted {
	background-image: url(not.png);
}

.single-quoted {
	background-image: url('single.png');
}

/* Right */

.double-quoted {
	background-image: url("double.png");
}
```

### Unitless zero values

``` css
/* Wrong */

.some-unnecessary-units {
	margin: 0px 8px 0px 16px;
}

/* Right */

.only-necessary-units {
	margin: 0 8px 0 16px;
}
```

### RGBA color values

``` css
/* Wrong */

.inconsistent-formatting {
	background-color: rgba(0,0,0,.25);
	border-color: rgb(127,127,127);
	color: #3f3f3f;
}

/* Right */

.consistent-formatting {
	background-color: rgba(0,0,0,.25);
	border-color: rgba(127,127,127,1);
	color: rgba(63,63,63,1);
}
```

### No leading zero on decimals

``` css
/* Wrong */

.with-leading-zero {
	opacity: 0.75;
}

/* Right */

.without-leading-zero {
	opacity: .75;
}
```

### No space after comma in value functions

``` css
/* Wrong */

.one-space {
	background: rgba(255, 255, 255, 1);
	color: rgba(0, 0, 0, 1);
}

/* Right */

.no-space {
	background: rgba(255,255,255,1);
	color: rgba(0,0,0,1);
}
```

### One space after comma in value lists

``` css
/* Wrong */

.no-space {
	background: linear-gradient(45deg,rgba(0,0,0,1),rgba(255,255,255,1));
}

/* Right */

.one-space {
	background: linear-gradient(45deg, rgba(0,0,0,1), rgba(255,255,255,1));
}
```

&nbsp;

## At-Rules

### Mobile-first media queries

``` css
/* Wrong */

@media screen and (max-width: 767px) {
	.desktop-first {
		color: rgba(255,0,0,1);
	}
}

/* Right */

@media screen and (min-width: 768px) {
	.mobile-first {
		color: rgba(0,255,0,1);
	}
}
```

### Nearby media queries

```
Example coming soon
```

&nbsp;

## Comments

### Hierarchical heading system

``` css
/* Primary Heading
============================================================= */

.primary-style {
	padding: 32px;
}

/* Secondary Heading
------------------------------------------------------------- */

.secondary-style {
	padding: 16px;
}
```

### Appropriate capitalization

``` css
example coming soon
```
