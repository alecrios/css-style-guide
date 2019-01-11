# CSS Style Guide

&nbsp;

## Table of Contents

&nbsp;

1. [**General**](#general)
	* 1.1 [Tab indentation](#tab-indentation)
	* 1.2 [No whitespace at ends of lines](#no-whitespace-at-ends-of-lines)
	* 1.3 [Newline at end of file](#newline-at-end-of-file)

[**Rules**](#rules)
* [One space before opening brace](#one-space-before-opening-brace)
* [Closing brace on new line](#closing-brace-on-new-line)
* [One blank line between rules](#one-blank-line-between-rules)
* [Condensed format for alignment](#condensed-format-for-alignment)

[**Selectors**](#selectors)
* [One selector per line](#one-selector-per-line)
* [Class names in kebab-case](#class-names-in-kebab-case)
* [No tags or IDs in selectors](#no-tags-or-ids-in-selectors)
* [Quoted attribute values](#quoted-attribute-values)
* [Meaningful and generic class names](#meaningful-and-generic-class-names)

[**Properties**](#properties)
* [One level of indentation for each property](#one-level-of-indentation-for-each-property)
* [One property per line](#one-property-per-line)
* [LSB property ordering](#lsb-property-ordering)
* [No space before colon, one space after](#no-space-before-colon-one-space-after)
* [Semicolon after every property value](#semicolon-after-every-property-value)
* [Multi-line format for alignment](#multi-line-format-for-alignment)

[**Values**](#values)
* [REM units](#rem-units)
* [Double-quoted strings](#single-quoted-strings)
* [Unitless zero values](#unitless-zero-values)
* [RGBA color values](#rgba-color-values)
* [No leading zero on decimals](#no-leading-zero-on-decimals)
* [Spaces after commas](#spaces-after-commas)

[**Media Queries**](#media-queries)
* [Mobile-first media queries](#mobile-first-media-queries)
* [Nearby media queries](#nearby-media-queries)

[**Comments**](#comments)
* [Hierarchical heading system](#hierarchical-heading-system)
* [Notes within rules](#notes-within-rules)

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

Adding a space between the selector and the brace improves readability.

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

Placing the closing brace on its own line makes for easier editing and cleaner git diffs.

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

Separating rules in this way improves readability.

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

For a set of single-property rules of the same type, aligning them with each other without empty lines in-between makes it easier to compare values. This is a special exception to other rules.

``` css
/* Wrong */

.small {
	width: 1rem;
}

.medium {
	width: 2rem;
}

.large {
	width: 3rem;
}

/* Right */

.small  {width: 1rem}
.medium {width: 2rem}
.large  {width: 3rem}
```

&nbsp;

## Selectors

### One selector per line

Placing one selector per line helps to distinguish subsequent selectors from descendents.

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

Writing class names in kebab-case creates consistency with CSS properties.

``` css
/* Wrong */

.camelCase {
	border-bottom: 1rem;
}

/* Right */

.kebab-case {
	border-bottom: 1rem;
}
```

### No tags or IDs in selectors

Writing selectors using only classes mitigates specificity issues.

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

### Quoted attribute values

Including the quotes around attribute values in selectors is easier to read and is consistent with HTML syntax.

``` css
/* Wrong */

.input[type=text] {
	padding: 1rem 1.5rem;
}

/* Right */

.input[type="text"] {
	padding: 1rem 1.5rem;
}
```

### Meaningful and generic class names

Naming a class with shorthand or unclear language reduces readability; naming a class with a particular value creates the unnecessary burden of renaming the class if the value changes.

``` css
/* Wrong */

.img-thmb-16 {
	max-width: 16rem;
}

.button-blue {
	color: rgba(0, 0, 255, 1);
}

/* Right */

.image-thumbnail {
	max-width: 16rem;
}

.button-primary {
	color: rgba(0, 0, 255, 1);
}
```

&nbsp;

## Properties

### One level of indentation for each property

Indenting each property improves readability.

``` css
/* Wrong */

.without-indentation {
font-size: 1rem;
line-height: 1.5rem;
}

/* Right */

.with-indentation {
	font-size: 1rem;
	line-height: 1.5rem;
}
```

### One property per line

Writing each property on its own line improves readability.

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

Using the Layout-Style-Behavior method as a loose guideline helps to organize properties in a logical manner.

* **Layout:** `position`, `display`, `width`, `margin`, `padding`, etc.
* **Style:** `font`, `line-height`, `color`, `background`, etc.
* **Behavior:** `transition`, `cursor`, `pointer-events`, etc.

``` css
/* Wrong */

.randomly-ordered {
	color: rgba(255, 255, 255, 1);
	transition: transform 1s ease-out;
	cursor: pointer;
	padding: 2rem;
	position: absolute;
	background-color: rgba(0, 255, 0, 1);
}

/* Right */

.logically-ordered {
	position: absolute;
	padding: 2rem;
	background-color: rgba(0, 255, 0, 1);
	color: rgba(255, 255, 255, 1);
	transition: transform 1s ease-out;
	cursor: pointer;
}
```

### No space before colon, one space after

Using colons in this manner is the most readable, because it matches colon usage in the English language.

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

Always including the semicolon prevents potential errors when reordering properties.

``` css
/* Wrong */

.without-last-semicolon {
	display: block;
	margin-bottom: 1rem;
	padding: 1rem
}

/* Right */

.with-last-semicolon {
	display: block;
	margin-bottom: 1rem;
	padding: 1rem;
}
```

### Multi-line format for alignment

Comma-separated values can become long and unwieldy. Aligning them together across multiple lines helps to improve readability and results in cleaner git diffs. This is a special exception to other rules.

``` css
/* Wrong */

.difficult-to-read {
	box-shadow: 0 0.25rem 0.25rem 0 rgba(0, 0, 0, .125), 0 0.75rem 0.75rem 0 rgba(0, 0, 0, .125);
}

/* Right */

.easy-to-read {
	box-shadow:
		0 0.25rem 0.25rem 0 rgba(0, 0, 0, .125),
		0 0.75rem 0.75rem 0 rgba(0, 0, 0, .125);
}
```

&nbsp;

## Values

### REM units

Pixel units are misleading as they do not actually equate to on-screen pixels. Using REM units – where 1rem is equal to the root font size – is a more reliable, scalable, and accessible approach.

_Note: Media query rules are exempt from this rule, as EM units have better support._

``` css
/* Wrong */

.bad-units {
	font-size: 16px;
	line-height: 1.5em;
	letter-spacing: 1px;
}

/* Right */

.good-units {
	font-size: 1rem;
	line-height: 1.5rem;
	letter-spacing: .0625rem;
}
```

### Double-quoted strings

Using double-quoted strings maintains consistency with the syntax used in HTML.

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

Omitting the unit on zero values reduces clutter.

``` css
/* Wrong */

.some-unnecessary-units {
	margin: 0rem 1rem 0rem 2rem;
}

/* Right */

.only-necessary-units {
	margin: 0 1rem 0 2rem;
}
```

### RGBA color values

Since alpha values can only be specified in the RGBA format, using RGBA across the board makes sense for consistency.

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

Omitting leading zeros on decimals reduces clutter.

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

Adding one space after each comma improves the readability.

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

## Media Queries

### Mobile-first media queries

Because interfaces generally become more complex as the viewport increases in size, it logically follows to write base styles first and progressively add styles for larger viewports.

``` css
/* Wrong */

.desktop-first-approach {
	width: 50%;
}

@media (max-width: 47.9375em) {
	.desktop-first-approach {
		width: 100%;
	}
}

/* Right */

.mobile-first-approach {
	width: 100%;
}

@media (min-width: 48em) {
	.mobile-first-approach {
		width: 50%;
	}
}
```

### Nearby media queries

Rather than grouping all media queries together at the bottom of a file, placing each media query immediately after the rule it overrides makes it easier to deal with related rules at once.

``` css
/* Wrong */

.selector-a {
	display: none;
}

.selector-b {
	display: none;
}

...

@media (min-width: 48em) {
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

@media (min-width: 48em) {
	.selector-a {
		display: block;
	}
}

.selector-b {
	display: none;
}

@media (min-width: 48em) {
	.selector-b {
		display: block;;
	}
}

...
```

&nbsp;

## Comments

### Hierarchical heading system

Writing headings with visual hierarchy improves the organization and scannability of files. Headings should be written in title case and should have a blank line above and below.

``` css
/* Primary Heading
============================================================================= */

.primary-style {
	padding: 2rem;
}

/* Secondary Heading
------------------------------------- */

.secondary-style {
	padding: 2rem;
}
```

### Notes within rules

Writing notes within rules is useful to provide clarity about methodology that is not immediately obvious. Notes should be written in sentence case and should have no blank lines above or below.

``` css
.rule-with-note {
	/* This is a note */
	position: absolute;
	top: 0;
	left: 0;
}
```
