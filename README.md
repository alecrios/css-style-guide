# CSS Style Guide

The purpose of this document is to codify a comprehensive set of guidelines for writing CSS. When strictly adhered to, these guidelines ensure that stylesheets are readable, understandable, and maintainable.

&nbsp;

## Table of Contents

[**General**](#general)
* [Maximum line length of 80 characters](#maximum-line-length-of-80-characters)
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
* [Avoid tags and IDs in selectors if possible](#avoid-tags-and-ids-in-selectors-if-possible)
* [Quoted attribute values](#quoted-attribute-values)
* [Double colons for pseudo-elements](#double-colons-for-pseudo-elements)

[**Properties**](#properties)
* [One level of indentation for each property](#one-level-of-indentation-for-each-property)
* [One property per line](#one-property-per-line)
* [Logical property ordering](#logical-property-ordering)
* [No space before colon, one space after](#no-space-before-colon-one-space-after)
* [Semicolon after every property value](#semicolon-after-every-property-value)
* [Multi-line format for alignment](#multi-line-format-for-alignment)
* [Avoid the important exception](#avoid-the-important-exception)

[**Values**](#values)
* [REM units](#rem-units)
* [Single-quoted strings](#single-quoted-strings)
* [Unitless zero values](#unitless-zero-values)
* [No leading or trailing zeros on decimals](#no-leading-or-trailing-zeros-on-decimals)
* [Spaces after commas](#spaces-after-commas)

[**Media Queries**](#media-queries)
* [Mobile-first media queries](#mobile-first-media-queries)
* [Nearby media queries](#nearby-media-queries)

[**Comments**](#comments)
* [Hierarchical heading system](#hierarchical-heading-system)
* [Notes within rules](#notes-within-rules)
* [Comment keywords](#comment-keywords)
* [Space-padded comments](#space-padded-comments)

[**Sass**](#sass)
* [Variable names in kebab-case](#variable-names-in-kebab-case)
* [Limit nesting to three levels deep](#limit-nesting-to-three-levels-deep)
* [Organization within Sass rules](#organization-within-sass-rules)
* [One blank line separating nested rules from other declarations](#one-blank-line-separating-nested-rules-from-other-declarations)
* [Avoid the extend directive](#avoid-the-extend-directive)
* [Prefer single-line Sass comments](#prefer-single-line-sass-comments)

&nbsp;

## General

### Maximum line length of 80 characters

Long lines, such as comments, should be restricted to 80 characters.

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

.small  { width: 1rem; }
.medium { width: 2rem; }
.large  { width: 3rem; }
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

### Avoid tags and IDs in selectors if possible

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

.input[type='text'] {
	padding: 1rem 1.5rem;
}
```

### Double colons for pseudo-elements

Using double colons for [pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) helps to distinguish them from [pseudo-classes](https://developer.mozilla.org/en-US/docs/Glossary/Pseudo-class).

``` css
/* Wrong */

.element:before {
	content: '';
}

/* Right */

.element::before {
	content: '';
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

### Logical property ordering

Grouping properties together by similarity helps the reader understand the styling more quickly. As a loose guideline, prefer to order properties as follows:

1. **Layout:** `position`, `display`, `width`, `margin`, `padding`, etc.
2. **Style:** `font`, `line-height`, `color`, `background`, etc.
3. **Behavior:** `transition`, `cursor`, `pointer-events`, etc.

``` css
/* Wrong */

.randomly-ordered {
	color: #ffffff;
	transition: transform 1s ease-out;
	cursor: pointer;
	padding: 2rem;
	position: absolute;
	align-items: center;
	justify-content: center;
	background-color: #000000;
	display: flex;
}

/* Right */

.logically-ordered {
	position: absolute;
	display: flex;
	align-items: center;
	justify-content: center;
	padding: 2rem;
	background-color: #000000;
	color: #ffffff;
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

### Avoid the important exception

Using `!important` is bad practice because it breaks the natural cascading system.

``` css
/* Wrong */

.element {
	font-size: 1.5rem !important;
}

/* Right */

.element.with-added-specificity {
	font-size: 1.5rem;
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

### Single-quoted strings

Using single-quoted strings is simply an opinionated choice.

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

### No leading or trailing zeros on decimals

Omitting unnecessary zeros reduces clutter.

``` css
/* Wrong */

.with-unnecessary-zeros {
	margin: 0.75rem 0.375rem 1.0rem 2.50rem;
}

/* Right */

.without-unnecessary-zeros {
	margin: .75rem .375rem 1rem 2.5rem;
}
```

### Spaces after commas

Adding one space after each comma improves the readability.

``` css
/* Wrong */

.without-spaces {
	color: rgba(31,63,95,1);
}

/* Right */

.with-spaces {
	color: rgba(31, 63, 95, 1);
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

### Comment keywords

Prefixing comments with `TODO` or `FIXME` makes it easy to identify areas that need to be revisited.

``` css
/* Wrong */

.seems-complete-but-its-not {
	display: block;
	padding: 1rem 1.5rem;
	height: 16rem;
	background-color: #ffffff;
	color: #000000;
}

/* Right */

.clearly-incomplete {
	display: block;
	padding: 1rem 1.5rem;
	/* FIXME: Set height to scale according to width */
	height: 16rem;
	background-color: #ffffff;
	color: #000000;
	/* TODO: Define type styles */
}
```

### Space-padded comments

Padding comments with a space on each side makes them easier to read.

``` css
/*Wrong */

/* Wrong*/

/*Wrong*/

/* Right */
```

&nbsp;

## Sass

### Variable names in kebab-case

Writing variable names in kebab-case creates consistency with the classes.

``` scss
/* Wrong */

$colorPrimary: #0000ff;

/* Right */

$color-primary: #0000ff;
```

### Limit nesting to three levels deep

Nesting beyond this level is indicative of markup that should be broken up into multiple components.

``` scss
/* Wrong */

.level-one {
	.level-two {
		.level-three {
			.level-four {
				...
			}
		}
	}
}

/* Right */

.level-one {
	.level-two {
		.level-three {
			...
		}
	}
}
```

### Organization within Sass rules

`@include` statements should be listed first, followed by standard CSS properties, followed by nested rules.

``` scss
/* Wrong */

.rule {
	.nested-rule-1 {
		padding: .75rem;
	}

	display: flex;
	@include mixin-2;
	align-items: center;
	justify-content: center;
	padding: .75rem;
	@include mixin-1;
}

/* Right */

.rule {
	@include mixin-1;
	@include mixin-2;
	display: flex;
	align-items: center;
	justify-content: center;
	padding: .75rem;

	.nested-rule {
		padding: .75rem;
	}
}
```

### One blank line separating nested rules from other declarations

Nested rules should be visually separated from standard CSS properties and `@include` statements. Sibling nested rules should also have one blank line in between.

``` scss
/* Wrong */

.rule {
	@include mixin-1;
	display: block;
	max-width: 64rem;
	.nested-rule-1 {
		margin-top: 1.5rem;
	}
	.nested-rule-2 {
		margin-top: 3rem;
	}
}

/* Right */

.rule {
	@include mixin-1;
	display: block;
	max-width: 64rem;

	.nested-rule-1 {
		margin-top: 1.5rem;
	}

	.nested-rule-2 {
		margin-top: 3rem;
	}
}
```

### Avoid the extend directive

Using `@extend` is bad practice because it behaves in unintuitive ways, leading to increased specificity, inheritence problems, and large file sizes.

``` scss
/* Wrong */

h6 {
	font-size: .75rem;
	line-height: 1.25rem;
}

label {
	@extend h6;
	cursor: pointer;
}

/* Right */

@mixin text-level-6 {
	font-size: .75rem;
	line-height: 1.25rem;
}

h6 {
	@include text-level-6;
}

label {
	@include text-level-6;
	cursor: pointer;
}
```

### Prefer single-line Sass comments

The `//` comment type in Sass is easier to work with than the multi-line `/* */` comment type.

``` scss
/* Wrong */

// Right
```
