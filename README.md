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

[**Selectors**](#selectors)
* [One selector per line](#one-selector-per-line)
* [Class names in kebab-case](#class-names-in-kebab-case)
* [No IDs in selectors](#no-ids-in-selectors)

[**Properties**](#properties)
* [One property per line](#one-property-per-line)
* [LSB property ordering](#lsb-property-ordering)
* [No space before colon, one space after](#no-space-before-colon-one-space-after)

[**Values**](#values)
* [Single-quoted strings](#single-quoted-strings)
* [Unitless zero values](#unitless-zero-values)
* [RGBA color values](#rgba-color-values)
* [Leading zero on decimals](#leading-zero-on-decimals)
* [Unitless `line-height`](#unitless-line-height)
* [Aversion to `!important`](#aversion-to-important)
* [Sensible `z-index` values](#sensible-z-index-values)

[**At-Rules**](#at-rules)
* [Mobile-first media queries](#mobile-first-media-queries)

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

### No IDs in selectors

``` css
/* Wrong */

#high-specificity {
	color: rgba(255, 0, 0, 1);
}

/* Right */

.normal-specificity {
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
	display: block;
	position: absolute;
	background-color: rbga(0, 255, 0, 1);
}

/* Right */

.logically-ordered {
	position: absolute;
	display: block;
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

### Leading zero on decimals

``` css
/* Wrong */

.less-explicit {
	opacity: .75;
}

/* Right */

.more-explicit {
	opacity: 0.75;
}
```

### Unitless `line-height`

``` css
example coming soon
```

### Aversion to `!important`

``` css
example coming soon
```

### Sensible `z-index` values

``` css
example coming soon
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
