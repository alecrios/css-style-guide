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

A space between the selector and the brace improves readability.

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

A blank line improves readability.

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

All selectors should consist only of classes in order to mitigate specificity issues

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

Classes written with shorthand or specific values are difficult to read and make it more difficult to update if values change.

``` css
/* Wrong */

.th-256 {
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

Layout-Style-Behavior is a loose guideline to help organize properties within rules.

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

&nbsp;

## Values

### REM units

Use REM units in all cases except for media queries, in which EM units have better support.

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
	margin: 0rem 1rem 0rem 2rem;
}

/* Right */

.only-necessary-units {
	margin: 0 1rem 0 2rem;
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

## Media Queries

### Mobile-first media queries

Rules should always be specified for small sizes first, and then media queries may be added to modify styling at larger sizes.

``` css
/* Wrong */

.desktop-first-approach {
	font-size: 1.5rem;
}

@media screen and (max-width: 47.9375em) {
	.desktop-first-approach {
		font-size: 1rem;
	}
}

/* Right */

.mobile-first-approach {
	font-size: 1rem;
}

@media screen and (min-width: 48em) {
	.mobile-first-approach {
		font-size: 1.5rem;
	}
}
```

### Nearby media queries

Rules within media queries should always reside immediately after the rules they override, rather than grouped together at the bottom of the file. This makes it easier to find rules that affect the same element and see them all at once.

``` css
/* Wrong */

.selector-a {
	display: none;
}

.selector-b {
	display: none;
}

@media screen and (min-width: 48em) {
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

@media screen and (min-width: 48em) {
	.selector-a {
		display: block;
	}
}

.selector-b {
	display: none;
}

@media screen and (min-width: 48em) {
	.selector-b {
		display: block;;
	}
}
```

&nbsp;

## Comments

### Hierarchical heading system

The following headings should be added as necessary to improve the organization of files. Headings should be written in title case and should have a blank line above and below.

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

Notes may be written within rules to explain the styles. Notes should be written in sentence case and should have no blank lines above or below.

``` css
.rule-with-note {
	/* This is a note */
	position: absolute;
	top: 0;
	left: 0;
}
```
