# BasecampSCSS

Welcome to Basecamp, a SCSS prototyping framework which allows you to write production ready code at a rapid development pace.

View the latest stable version in use at [JoeyGrable.com/git/BasecampSCSS](http://joeygrable.com/git/BasecampSCSS/)



## Getting Started

- clone the repository to your htdocs folder
- edit "base/config.scss" to customize your Basecamp settings
- add your custom styles to "base/_build.scss"
- compile the sass into css to build your basecamp

```
sass --watch inc/basecamp/basecamp.scss:inc/css/basecamp.css
```



## Naming Conventions

Basecamp uses the follow rules when naming classes, variables, mixins and functions.



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



## Prototype vs. Production

- *** what is the difference? why use one over the other? ***
- in the “base/config.scss” file there is a variable that enables prototype or production mode
- by default prototyping is enabled

```
$prototype: true !default;
```
- to use basecamp in production set the 

```
prototype: false;
```
- *** how does this change the code? what changes to your build do you need to alter once using in production mode? ***



## Establish Base (Modules)

- about the modules in the “base/“ folder



## Customize Camp (Components)

- about the components’ styles in the “components/“ folder



## Vendors (optional dependencies)

- reset.scss
- normalize.scss
- animate.scss
- colorMeSass
- blendModes.scss



## Build.

- about simple to complex implementation



### Primed Mixins & Functions

- basecamp mixins are already primed with the default values from your config file
- this means editing primary website styles are as easy as editing the “base/config.scss” file then compiling the sass into css
- if you want full customization, it is recomended you establish your web-styles basecamp in the “base/config.scss” file, then implement your custom mixins on your site specific DOM elements in the “base/build.scss” file



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



