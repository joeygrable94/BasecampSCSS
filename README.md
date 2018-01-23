# BasecampSCSS

Welcome to BasecampSCSS, a SCSS prototyping framework which allows you to write production ready code at a rapid development pace.

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

- BasecampSCSS is unique because it is easy to do use it without very much configuring to establish a solid wireframe to build your website off of
- however, BasecampSCSS modules are what we call Primed Mixins & Functions and is discused in the following section
- the sections below outline how to implement BasecampSCSS quickly, then how to fully customize the mixins for your use



## Primed Mixins & Functions

- BasecampSCSS mixins are already primed with the default values from your config file
- this means editing primary website styles are as easy as editing the “base/config-base.scss” file then compiling the sass into css
- if you want full customization, it is recomended you establish your web-styles BasecampSCSS in the base/config-base.scss file, then implement your custom mixins on your site specific DOM elements in the base/build-camp.scss file



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

### Responsize Media

### Color

### Typography

### Elements: borders

### Forms

### Tables

### Buttons



## Build Camp (build-camp.scss)


