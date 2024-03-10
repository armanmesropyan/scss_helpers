

The package sets some sensible defaults for HTML elements eg.:

```scss
// base/*.scss

* {
    box-sizing: border-box;
    position: relative;

    &:after,
    &:before {
        box-sizing: border-box;
    }
}
```

Generic helper classes are included for common layout issues:

```scss
// helpers/margin.scss

.h-margin {
    ...
}

.h-margin-none {
    ...
}

.h-margin-small {
    ...
}

...

```

Default settings are stored in Sass maps...

```scss
// settings/typography.scss

$font-weight: (
    default: (
            ...
            ),
    secondary: (
        normal: 400,
        bold: 700,
    ),
    fixed: (
       ...
    ),
) !default;


// settings/colors.scss

$blue: (
    lightest: #e6f5ff,
    lighter: #8bcdff,
    ...
) !default;
```

... and can be used with mixins or functions afterwards:

```scss
// my-app.scss

@import '@spatie/scss/settings';
@import 'my-custom-settings';
@import '@spatie/scss/styles';

h1 {
    @include font-secondary-bold;
    color: blue(darkest);
}

```
