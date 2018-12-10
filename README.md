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
* [Spaces after commas](#spaces-after-commas)

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
	display: flex;
}

/* Right */

.just-right {
	display: flex;
}
```

### Closing brace on new line

The closing brace on its own line makes for easier editing and cleaner git diffs.

``` css
/* Wrong */

.wrong-spot {
	position: relative;}

/* Right */

.right-spot {
	position: relative;
}
```

### One blank line between rules

A blank line increases readability.

``` css
/* Wrong */

.cramped {
	text-decoration: underline;
}
.crowded {
	font-weight: 700;
}

/* Right */

.breathable {
	text-decoration: underline;
}

.spacious {
	font-weight: 700;
}
```

### Condensed format for alignment

For a set of single-property rules with the same property, aligning them with each other without empty lines in-between makes it easier to compare values. This is a special exception to other rules.

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

.small  {font-size: 12px}
.medium {font-size: 16px}
.large  {font-size: 20px}
```

&nbsp;

## Selectors

### One selector per line

A new line makes it more clear that the following selector is separate and not a descendent.

``` css
/* Wrong */

.two-selectors, .one-line {
	background-size: cover;
}

/* Right */

.two-selectors,
.two-lines {
	background-size: cover;
}
```

### Class names in kebab-case

CSS properties are written in kebab-case, so class names should follow suit.

``` css
/* Wrong */

.camelCase {
	display: inline;
}

/* Right */

.kebab-case {
	display: inline;
}
```

### No tags or IDs in selectors

To mitigate specificity issues, all selectors should consist only of classes.

``` css
/* Wrong */

.low-specificity a {
	text-decoration: none;
}

#high-specificity .link {
	text-decoration: none;
}

/* Right */

.normal-specificity .link {
	text-decoration: none;
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
	color: rgba(0, 0, 255, 1);
}

/* Right */

.image-thumbnail {
	float: left;
	max-width: 256px;
}

.button-primary {
	color: rgba(0, 0, 255, 1);
}


```

&nbsp;

## Properties

### One property per line

Write each property on its own line to improve readability.

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

Layout-Style-Behavior is a loose property ordering guideline that makes rules more organized.

* **Layout:** `position`, `display`, `width`, `margin`, `padding`, etc.
* **Style:** `font`, `line-height`, `color`, `background`, etc.
* **Behavior:** `transition`, `cursor`, `pointer-events`, etc.

``` css
/* Wrong */

.randomly-ordered {
	color: rbga(255, 255, 255, 1);
	transition: transform 1s ease-out;
	cursor: pointer;
	padding: 32px;
	position: absolute;
	background-color: rbga(0, 255, 0, 1);
}

/* Right */

.logically-ordered {
	position: absolute;
	padding: 32px;
	background-color: rbga(0, 255, 0, 1);
	color: rbga(255, 255, 255, 1);
	transition: transform 1s ease-out;
	cursor: pointer;
}
```

### No space before colon, one space after

This configuration is the most readable, because it matches colon usage in the English language.

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

Using double-quoted strings matches the syntax used in HTML.

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

It is unnecessary to specify the unit on a zero value.

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

Since alpha values can only be specified in the RGBA format, it makes sense to use RGBA for everything to be consistent.

``` css
/* Wrong */

.inconsistent-formatting {
	border-color: rgb(127, 127, 127);
	background-color: rgba(0, 0, 0, .25);
	color: #3f3f3f;
}

/* Right */

.consistent-formatting {
	border-color: rgba(127, 127, 127, 1);
	background-color: rgba(0, 0, 0, .25);
	color: rgba(63, 63, 63, 1);
}
```

### No leading zero on decimals

The omission of leading zeros reduces clutter.

``` css
/* Wrong */

.with-leading-zeros {
	margin: 0.75rem 0.375rem 0.75rem 0.375rem;
}

/* Right */

.without-leading-zeros {
	margin: .75rem .375rem .75rem .375rem;
}
```

### Spaces after commas

The inclusion of spaces improves the readability.

``` css
/* Wrong */

.without-spaces {
	background: linear-gradient(45deg,rgba(0,0,0,1),rgba(255,255,255,1));
	color: rgba(0,0,0,1);
}

/* Right */

.with-spaces {
	background: linear-gradient(45deg, rgba(0, 0, 0, 1), rgba(255, 255, 255, 1));
	color: rgba(0, 0, 0, 1);
}
```

&nbsp;

## At-Rules

### Mobile-first media queries

Rules should always be specified for small sizes first, and then media queries may be added to modify styling at larger sizes.

``` css
/* Wrong */

.desktop-first-approach {
	font-size: 24px;
}

@media screen and (max-width: 767px) {
	.desktop-first-approach {
		font-size: 16px;
	}
}

/* Right */

.mobile-first-approach {
	font-size: 16px;
}

@media screen and (min-width: 768px) {
	.mobile-first-approach {
		font-size: 24px;
	}
}
```

### Nearby media queries

Rules within media queries should always reside immediately after the rules they override, rather than grouped together at the bottom of the file. This makes it easier to find rules that affect the same element and see them all at once.

```css
/* Wrong */

.selector-a {
	display: none;
}

.selector-b {
	display: none;
}

@media screen and (min-width: 768px) {
	.selector-a {
		display: block;
	}

	.selector-b {
		display: block;;
	}
}

/* Right */

.selector-a {
	display: none;
}

@media screen and (min-width: 768px) {
	.selector-a {
		display: block;
	}
}

.selector-b {
	display: none;
}

@media screen and (min-width: 768px) {
	.selector-b {
		display: block;;
	}
}
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
