# BasecampSCSS

Welcome to BasecampSCSS, a SASS/SCSS prototyping framework which allows you to write production ready code at a rapid development pace.

View the latest stable version in use at [JoeyGrable.com/git/BasecampSCSS](http://joeygrable.com/git/BasecampSCSS/)



## Getting Started

1. clone the repository into your css folder
2. customize settings inside base/config-base.scss
3. add your custom styles to base/build-camp.scss
4. compile the sass into css to build your BasecampSCSS

```
sass --watch BasecampSCSS/basecamp.scss:basecamp.css
```



## Naming Conventions

BasecampSCSS uses the follow rules when naming classes, variables, mixins and functions.



### Classes & SASS Variables

```
.classes-like-this {
    css-property: $var-block-element-modifier;
}

```



### Primed Mixins & Functions


```
@mixin name-property-action(
    $variable-one: $config-default-1,
    $variable-two: $config-default-2
) {
    // do stuff with defaults
}

```



## File Structure & Details

```
BasecampSCSS/
    basecamp.scss    // compiles everything into BasecampSCSS.css
    base/
        build-camp.scss
        config-base.scss
    components/
        typography.scss
        forms.scss
        tables.scss
        buttons.scss
    modules/
        internal.scss
        functions.scss
        mixins.scss
    vendors/
        reset.scss
        normalize.scss
        vendors/animate/animate.scss
        color/
            color-me-sass.scss
            blend-modes.scss
```



### Base

- the base foler is where you will configure your base and build your camp
- these files are essential for simple BasecampSCSS implementations



### Components

- think of Components as the CONTROLLERS that output the CSS styles configured in the base/config-base.scss and base/build-camp.scss files
- components contain foundational styles that are calculated using variables from the config file, and mixins or functions from the modules folder



### Modules

- think of modules as the LOGIC that calculates styles
- modules are mixins or functions that are used internally by BasecampSCSS
- they are used by variables components or in your base/build-camp.scss file



### Vendors (dependencies)

- reset.scss        (recommended)
- normalize.scss    (recommended)
- animate.scss      (as needed)
- colorMeSass       (as needed)
- blendModes.scss   (as needed)



## Order of Implementation

- this is the order in which basecamp compiles and executes

1. Import Vendors
2. Establish Base
3. Import Modules
4. Create Components
5. Build Camp





# Build Your BasecampSCSS

- BasecampSCSS is unique because it is easy to rapidly implement a base wireframe to build your website off of
- Additionally, BasecampSCSS modules are "primed mixins & functions" and is discused in the following section
- the sections below outline how to implement BasecampSCSS quickly, and then how to fully customize the mixins for your use



## Primed Mixins & Functions

- BasecampSCSS mixins are already primed with the default values from your config file
- this means editing primary website styles are as easy as editing the “base/config-base.scss” file then compiling the sass into css
- if you want full customization, it is recomended you establish your web-styles BasecampSCSS in the base/config-base.scss file, then implement your custom mixins on your site specific DOM elements in the base/build-camp.scss file (examples provided below)



### Primed Mixin & Function Usage:


```
.inside-class-or-id {

    // call the mixin or function with config defaults
    @include name-property-action();

    // call but overwrite the defaults to customize
    @include name-property-action(
        $variable-one: overwrite,
        $variable-two: overwrite
    );
}

```



## Configure Base (config-base.scss)

- the configuration file contains everything you need to customize the base styles of your website



###  CSS Grid

```
$gridinator-cols: "repeat(2, 1fr)";
$gridinator-rows: "repeat(2, 1fr)";
$gridinator-gap: 0px 0px;
```



### Responsize Media

```
$breakpoint-sm: 420px;
$breakpoint-md: 760px;
$breakpoint-lg: 1080px;
$breakpoint-xl: 1440px;
```



### Color

```
// palettes
$color-primary:     $bluePrimary !default;
$color-secondary:   $yellowGoldmetal !default;
$color-tertiary:    $redDanger !default;

// states
$color-success:     $greenSuccess !default;
$color-info:        $blueInfo !default;
$color-warning:     $yellowWarning !default;
$color-error:       $orangeDark !default;
```



### Typography

```
// load typography.
$load-typesettings: true !default;

// sets the html and body tags height & width to 100vh/vw & 100%/100%
$full-screen-responsive: true !default;

// The vertical grid unit. Margin, padding, and line-height are set to
// multiples of this value. This is the value that determines the baseline
// for our vertical rhythm. The default value of 6px allows more fine
// tuned designs that still obey vertical rhythm.
$baseline-unit: 8px !default;

// This gives type an ideal line-height. The value that multiplies
// the $baseline-unit to get the $baseline-height.
$baseline-mltp: 4 !default;

// Base font size in pixels, gets converted to ems
$base-font-size: 18px !default;

// Modular scale ratio is used to calculate different font sizes
$ratio-modular-scale: 1.5 !default;

// paragraph-indent option sets paragraphs indent of the first line
// of a new paragraph ON or OFF. Indents all paragraphs execpt
// the first on in a group of p tags (p + p)
$paragraph-indent: true !default;

// paragraph-justify sets paragraphs ragged right or justified.
$paragraph-justify: false !default;

// base font family (paragraph content)
$base-font-family: Cambria, "Hoefler Text", Utopia, "Liberation Serif", "Nimbus Roman No9 L Regular", Times, "Times New Roman", serif !default;

// headers fonts
$base-font-headers: "Helvetica Neue", Helvetica, Arial, "Liberation Sans", FreeSans, sans-serif !default;

// monospaced fonts
$base-font-mono: Consolas, "Andale Mono WT", "Andale Mono", "Lucida Console", "Lucida Sans Typewriter", "DejaVu Sans Mono", "Bitstream Vera Sans Mono", "Liberation Mono", "Nimbus Mono L", Monaco, "Courier New", Courier, monospace !default;
```



### Elements

```
// borders
$border-width-default: 1px;
$border-style-default: solid;
$border-color-default: $black30;
$border-radius-default: $baseline-mltp;
```



### Forms

```
// label
$form-label-font-weight: 400;

// input
$form-input-color: $black;
$form-input-background-color: $transparent;
$form-input-box-shadow: 0px 0px 5px -2px $color-primary;

// input border
$form-input-border-width: 1px;
$form-input-border-color: $grayLight;
$form-input-border: $form-input-border-width solid $form-input-border-color;
$form-input-border-radius: 0px;

// disabled
$form-input-disabled-color: $black10;

// input focus
$form-input-focus-color: $black;
$form-input-focus-background: $transparent;
$form-input-focus-border-color: $color-primary;
$form-input-focus-box-shadow: 0px 0px 5px -2px $color-primary;
```



### Tables

```
$table-row-bordered: true !default;
$table-row-striped: true !default;
```



### Buttons

```
// base
$btn-font-size: inheret;
$btn-font-weight: 400;
$btn-border-radius: 4px;
$btn-border-width: 2px;
$btn-border-style: solid;
$btn-border-color: $black;
$btn-link-disabled-color: $graySilver;

// default
$btn-default-color: $white;
$btn-default-background: $black;
// border
$btn-default-border-width: $btn-border-width;
$btn-default-border-style: $btn-border-style;
$btn-default-border-color: $black;
    // :hover
    $btn-default-color-hover: $white;
    $btn-default-background-hover: $black70;
    // :hover border
    $btn-default-border-width-hover: $btn-border-width;
    $btn-default-border-style-hover: $btn-border-style;
    $btn-default-border-color-hover: $black;

// additional: primary, secondary, tertiary, info, warning, error
...
```



## Build Camp (build-camp.scss)



### Primed Mixins

```
@mixin base-xy($width: 100vw, $height: 100vh) {}
@mixin base-x($width: 100%) {}
@mixin base-y($height: 100vh) {}
@mixin base-columns($columns: 12) {}

@mixin gridinator(
    $type: grid,
    $columns: $gridinator-cols,
    $rows: $gridinator-rows,
    $gap: $gridinator-gap,
    $justify-items: stretch,
    $align-items: stretch,
    $justify-content: stretch,
    $align-content: stretch
) {}
@mixin g-child($justify-self: stretch, $align-self: stretch) {}
@mixin g-cols($start: 1, $end: 2) {}
@mixin g-rows($start: 1, $end: 2) {}

@mixin debug-vertical-alignment(
    $opacity: 0.8,
    $vertical-unit: $baseline-unit,
    $type-baseline-mltp: $baseline-mltp,
    $type-size: $base-font-em
) {}
@mixin rhythm-border-top($border-width: 1px, $lines: $baseline-mltp, $font-size: $base-font-em) {}
@mixin rhythm-border-bottom($border-width: 1px, $lines: $baseline-mltp, $font-size: $base-font-em) {}
@mixin rhythm-border($border-width: 1px, $lines: $baseline-mltp, $font-size: $base-font-em) {}

@mixin flex(
    $display: flex,
    $direction: row,
    $wrap: wrap,
    $justify-content: flex-start,
    $align-items: stretch,
    $align-content: stretch
) {}
@mixin flex-child(
    $order: 0,
    $align: auto
) {}

@mixin box(
    $width: auto,
    $height: auto,
    $display: block
) {}
@mixin box-position(
    $position: relative,
    $location: (top: auto, right: auto, bottom: auto, left: auto)
) {}
@mixin float($float: none) {}

@mixin z-depth($index: auto) {}

@mixin scroll-box($direction: y, $bar: true) {}
@mixin scroll-hide() {}

@mixin contain($breakpoint: 960px) {}

@mixin margin($mltp: 1px, $sides: true) {}
@mixin margin-em($mltp: 1, $sides: true) {}
@mixin padding($mltp: 1px, $sides: true) {}
@mixin padding-em($mltp: 1, $sides: true) {}

@mixin typesettings-init($full-screen-responsive: true) {
@mixin set-type(
    $lines: $baseline-mltp,
    $font-size: $base-font-em,
    $silent: false
) {}
@mixin set-leading(
    $lines: $baseline-mltp,
    $font-size: $base-font-em,
    $silent: false
) {}

@mixin button-base($display: inline-block) {}
@mixin button-size($padding-y: 1, $padding-x: 3) {}
@mixin button-size-em($padding-y: 1, $padding-x: 3) {}
@mixin button-color(
    $color: $black,
    $color-hover: $white,
    $background: $white,
    $background-hover: $black50,
) {}
@mixin button-outline(
    $color: $black,
    $color-hover: $grayDark,
    $background-active: $color,
    $border-active: lighten($color, 10%)
) {}
@mixin button-link(
    $font-weight: $btn-font-weight,
    $link-color: $color-primary,
    $link-color-hover: darken($color-primary, 7.5%),
    $link-decoration-hover: underline
) {}

@mixin form-input-base(
    $display: block,
    $border-radius: $form-input-border-radius,
    $border-focus: $form-input-focus-border-color,
    $input-color: $form-input-color,
    $input-background: $form-input-background-color,
    $input-border: $form-input-border,
    $input-border-radius: $form-input-border-radius
) {}
@mixin form-input-focus(
    $input-focus-color:         $form-input-focus-color,
    $input-focus-background:    $form-input-focus-background,
    $input-focus-border-color:  $form-input-focus-border-color,
    $input-box-shadow:          $form-input-box-shadow,
    $input-focus-box-shadow:    ($form-input-box-shadow, $form-input-focus-box-shadow)
) {}
@mixin form-input-plaintext() {

@mixin image-fluid {}
@mixin image-retina($file-1x, $file-2x, $width-1x, $height-1x) {}

@mixin hover {}
@mixin focus {}
@mixin active {}
@mixin disabled {}
@mixin hover-focus {}
@mixin plain-hover-focus {}
@mixin hover-focus-active {}
@mixin focus-active {}

@mixin border(
    $sides: true,
    $border-width: $border-width-default,
    $border-style: $border-style-default,
    $border-color: $border-color-default,
) {}
@mixin border-radius($radius: $border-radius-default) {}
@mixin border-top-radius($radius) {}
@mixin border-right-radius($radius) {}
@mixin border-bottom-radius($radius) {}
@mixin border-left-radius($radius) {}

@mixin respond-to($breakpoint, $media: all) {}
@mixin breakpoint($breakpoint, $media: all) {}
@mixin bp($breakpoint, $media: all) {}
@mixin high-dpi($media: all) {}
```



