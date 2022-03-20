- # Sass-library

## _A Sass library of CSS styles for a quicker development process_

### [Sass Docs](https://sass-lang.com/)

## Why do this?

- Avoiding creating monolithic style pages.
- Understand the principles of how tools like Tailwind and Bootstrap are created and why they are useful.
- DRY principles: To avoid creating a grid system / color palette / breakpoints from scratch for each project.
  - _Have I gone against this principle by recreating a tool similar to what already exists?_
  - _A: No as this is a learning experience and a tool crafted for personal use._
- Faster development: When building the MVP there are your own components ready to go off the shelf.
- Flow: Knowing exactly how the library is composed avoids context switching and means there is deep knowledge from the start
  rather than having to learn the syntax of a framework.
- Easy customization and extendibility: As it's Sass and something that I created there is no black box about how to add features
  (careful of the bloat - address partially later). As new styles and techniques are required, it's totally possible to stay with current best practices.
- Consistency: We all have our favoured way of styling things, now rather than being at the mercy of my mood / motivation I have ready styles to go.
- Size: Overall it's quite a small library so - It's not an API and thus not calling specific styles which might help to reduce bundle overall size,
  but there are tools to help with this
- Removing redundancy: Using tools like Gulp helps to remove unused styles helping to make the final bundle size smaller and delivering
  a faster time to first paint (also dependent on other factors).

## Downside

The greatest cost to the library is time and maintenance to keep it fresh.

## Structure

- Use of variables and functions
- Separation of concerns for each file using an underscore at the start of a file name so that
  the styles are only read and complied from 1 Sass file to the CSS file.

## Sass features used

- @use
- @forward
- @mixin and @include
- @function
- @extend
- @debug
- !default

### Flow control from CSS

- @if and @else
- @each
- @for

### Built-in modules

- Sass:math

### Values

- Maps
- Lists
- Colors
- Strings
- Numbers

### Removed from the project:

- @import This is a depricated feature and should no longer be used
  [@use and @forward are the new way of doing things](https://www.youtube.com/watch?v=CR-a8upNjJ0).

## How to use it

- Use it as it is without making modifications to the styles of the library

### Customizing styles

- change the gulpfile.js to watch the new sass file rather than the sass file from the library.
- Rerun Gulp and it will still output to the CSS file.
- Use @forward to have SassLib accessible in the new file to include everything from the library.
- To override the styles from the library, put the import below the new styles
  In the `'sass/index.scss'` file:

```
$primary: indigo;

@forward 'sassLib';
```

In the `sassLib/index.scss` add `!defaut` to indicate to use this style unless there is another variable already declared which overrides the default style:

```
$primary: #326dee !default;
```

## Going forwards and extending the library

The main thing that I think that I will be adding include:

- Input fields
- Form elements

I may also add animations and transitions.

Overall, I've learnt a ton from this project and it will make future styling much more efficient.
