# BasecampSCSS

Welcome to BasecampSCSS, a SCSS prototyping framework which allows you to write production ready code at a rapid development pace.

View the latest stable version in use at [JoeyGrable.com/git/BasecampSCSS](http://joeygrable.com/git/BasecampSCSS/)



## Getting Started

- clone the repository to your htdocs folder
- edit "base/config.scss" to customize your BasecampSCSS settings
- add your custom styles to "base/_build.scss"
- compile the sass into css to build your BasecampSCSS

```
sass --watch basecamp.scss:basecamp.css
```



## Naming Conventions

BasecampSCSS uses the follow rules when naming classes, variables, mixins and functions.



### Variables and Classes

```
.classes-like-this {
    css-property: $var-block-element-modifier;
}

```



### Mixins & Functions (primed)


```
@mixin name-property-action(
    $variable-one: $config-default,
    $variable-two: $config-default
) {
    // do stuff with defaults or overwrite them
}

```



### Usage


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



## File Structure & Details

```
BasecampSCSS/
    basecamp.scss    // compiles everything into BasecampSCSS.css
    base/
        build.scss
        config.scss
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

- think of modules as the CONTROLLERS that output the CSS styles configured in the base/config and base/build file
- components contain foundational styles that are calculated using variables from the config file, and mixins or functions from the modules folder



### Modules

- think of modules as the LOGIC that calculates styles
- modules are mixins or functions that are used internally by BasecampSCSS
- they are used by variables components or in your base/build file



### Vendors (dependencies)

- reset.scss        (recommended)
- normalize.scss    (recommended)
- animate.scss      (as needed)
- colorMeSass       (as needed)
- blendModes.scss   (as needed)




## Build Your BasecampSCSS

- BasecampSCSS is unique because it is easy to do use it without very much configuring to establish a solid wireframe to build your website off of
- however, BasecampSCSS modules are what we call "Primed Mixins & Functions" and is discused in the following section
- the sections below outline how to implement BasecampSCSS quickly, then how to fully customize the mixins for your use



### Primed Mixins & Functions

- BasecampSCSS mixins are already primed with the default values from your config file
- this means editing primary website styles are as easy as editing the “base/config.scss” file then compiling the sass into css
- if you want full customization, it is recomended you establish your web-styles BasecampSCSS in the base/config.scss file, then implement your custom mixins on your site specific DOM elements in the base/build.scss file

```
@mixin name-property-action(
    $variable-one: $config-default,
    $variable-two: $config-default
) {
    // do stuff with defaults or overwrite them
}

```



#### Primed Mixin Usage:


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



## Order of Implementation

- ESTABLISH BASE
- IMPORT MODULES
- COMPONENTS
- BUILD CAMP