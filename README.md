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

[**Properties**](#properties)
* [One property per line](#one-property-per-line)
* [LSB property ordering](#lsb-property-ordering)
* [No space before colon, one space after](#no-space-before-colon-one-space-after)
* [Semicolon after every property value](#semicolon-after-every-property-value)

[**Values**](#values)
* [Single-quoted strings](#single-quoted-strings)
* [Unitless zero values](#unitless-zero-values)
* [RGBA color values](#rgba-color-values)
* [No leading zero on decimals](#no-leading-zero-on-decimals)
* [One space after comma in value lists](#one-space-after-comma-in-value-lists)
* [No space after comma in value functions](#no-space-after-comma-in-value-functions)
* [Alignment on prefixed properties](#alignment-on-prefixed-properties)

[**At-Rules**](#at-rules)
* [Mobile-first media queries](#mobile-first-media-queries)
* [Nearby media queries](#nearby-media-queries)

[**Comments**](#comments)
* [Hierarchical heading system](#hierarchical-heading-system)
* [Appropriate capitalization](#appropriate-capitalization)

&nbsp;

## General

### Tab indentation

``` css
example coming soon
```

### No whitespace at ends of lines

``` css
example coming soon
```

### Newline at end of file

``` css
example coming soon
```

&nbsp;

## Rules

### One space before opening brace

``` css
/* Wrong */

.too-tight{
	color: rgba(255, 0, 0, 1);
}

/* Right */

.just-right {
	color: rgba(0, 255, 0, 1);
}
```

### Closing brace on new line

``` css
/* Wrong */

.wrong-spot {
	color: rgba(255, 0, 0, 1);}

/* Right */

.right-spot {
	color: rgba(0, 255, 0, 1);
}
```

### One blank line between rules

``` css
/* Wrong */

.cramped {
	color: rgba(255, 0, 0, 1);
}
.crowded {
	color: rgba(255, 0, 0, 1);
}

/* Right */

.breathable {
	color: rgba(0, 255, 0, 1);
}

.spacious {
	color: rgba(0, 255, 0, 1);
}
```

### Condensed format for alignment

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

``` css
/* Wrong */

.two-selectors, .one-line {
	color: rgba(255, 0, 0, 1);
}

/* Right */

.two-selectors,
.two-lines {
	color: rgba(0, 255, 0, 1);
}
```

### Class names in kebab-case

``` css
/* Wrong */

.camelCase {
	color: rgba(255, 0, 0, 1);
}

/* Right */

.kebab-case {
	color: rgba(0, 255, 0, 1);
}
```

### No tags or IDs in selectors

``` css
/* Wrong */

.low-specificity a {
	color: rgba(255, 0, 0, 1);
}

#high-specificity .link {
	color: rgba(255, 0, 0, 1);
}

/* Right */

.normal-specificity .link {
	color: rgba(0, 255, 0, 1);
}
```

&nbsp;

## Properties

### One property per line

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

``` css
/* Wrong */

.without-last-semicolon {
	display: block;
	margin-bottom: 16px;
	padding: 16px
}

.with-last-semicolon {
	display: block;
	margin-bottom: 16px;
	padding: 16px;
}

/* Right */
```

&nbsp;

## Values

### Single-quoted strings

``` css
/* Wrong */

.not-quoted {
	background-image: url(not.png);
}

.double-quoted {
	background-image: url("double.png");
}

/* Right */

.single-quoted {
	background-image: url('single.png');
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
	background-color: rgba(0, 0, 0, 0.25);
	border-color: rgb(127, 127, 127);
	color: #3f3f3f;
}

/* Right */

.consistent-formatting {
	background-color: rgba(0, 0, 0, 0.25);
	border-color: rgba(127, 127, 127, 1);
	color: rgba(63, 63, 63, 1);
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

### One space after comma in value lists

```
Example coming soon
```

### No space after comma in value functions

```
Example coming soon
```

### Alignment on prefixed properties

```
Example coming soon
```

&nbsp;

## At-Rules

### Mobile-first media queries

``` css
/* Wrong */

@media screen and (max-width: 767px) {
	.desktop-first {
		color: rgba(255, 0, 0, 1);
	}
}

/* Right */

@media screen and (min-width: 768px) {
	.mobile-first {
		color: rgba(0, 255, 0, 1);
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
