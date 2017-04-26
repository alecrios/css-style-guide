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
* [No space before colon](#no-space-before-colon)
* [One space after colon](#one-space-after-colon)

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
example coming soon
```

### LSB property ordering

``` css
example coming soon
```

### No space before colon

``` css
example coming soon
```

### One space after colon

``` css
example coming soon
```

&nbsp;

## Values

### Single-quoted strings

``` css
example coming soon
```

### Unitless zero values

``` css
example coming soon
```

### RGBA color values

``` css
example coming soon
```

### Leading zero on decimals

``` css
example coming soon
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
example coming soon
```

&nbsp;

## Comments

### Hierarchical heading system

``` css
example coming soon
```

### Appropriate capitalization

``` css
example coming soon
```
