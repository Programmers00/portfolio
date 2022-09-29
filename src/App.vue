<template>
  <div id="app">
    <!-- layout -->
    <AppNavbar></AppNavbar>
    <AppMain></AppMain>
    <AppFooter></AppFooter>
  </div>
</template>

<script>
import AppNavbar from "@/layout/AppNavbar.vue";
import AppMain from "@/layout/AppMain.vue";
import AppFooter from "@/layout/AppFooter.vue";

export default {
  name: "App",
  components: {
    AppNavbar,
    AppMain,
    AppFooter,
  },
};
</script>

<style lang="scss">
@charset "utf-8";
@import url("https://fonts.googleapis.com/css?family=Noto+Sans+KR:100,300,400,500,700,900&display=swap");

/* css reset */

/*! normalize.css v8.0.1 | MIT License | github.com/necolas/normalize.css */
html {
  line-height: 1.15;
  /* 1 */
  -webkit-text-size-adjust: 100%;
  /* 2 */
}

/* Sections
    ========================================================================== */

/**
* Remove the margin in all browsers.
*/

body {
  margin: 0;
}

/**
* Render the `main` element consistently in IE.
*/

main {
  display: block;
}

/**
* Correct the font size and margin on `h1` elements within `section` and
* `article` contexts in Chrome, Firefox, and Safari.
*/

h1 {
  font-size: 2em;
  margin: 0.67em 0;
}

/* Grouping content
    ========================================================================== */

/**
* 1. Add the correct box sizing in Firefox.
* 2. Show the overflow in Edge and IE.
*/

hr {
  box-sizing: content-box;
  /* 1 */
  height: 0;
  /* 1 */
  overflow: visible;
  /* 2 */
}

/**
* 1. Correct the inheritance and scaling of font size in all browsers.
* 2. Correct the odd `em` font sizing in all browsers.
*/

pre {
  font-family: monospace, monospace;
  /* 1 */
  font-size: 1em;
  /* 2 */
}

/* Text-level semantics
    ========================================================================== */

/**
* Remove the gray background on active links in IE 10.
*/

a {
  background-color: transparent;
}

/**
* 1. Remove the bottom border in Chrome 57-
* 2. Add the correct text decoration in Chrome, Edge, IE, Opera, and Safari.
*/

abbr[title] {
  border-bottom: none;
  /* 1 */
  text-decoration: underline;
  /* 2 */
  text-decoration: underline dotted;
  /* 2 */
}

/**
* Add the correct font weight in Chrome, Edge, and Safari.
*/

b,
strong {
  font-weight: bolder;
}

/**
* 1. Correct the inheritance and scaling of font size in all browsers.
* 2. Correct the odd `em` font sizing in all browsers.
*/

code,
kbd,
samp {
  font-family: monospace, monospace;
  /* 1 */
  font-size: 1em;
  /* 2 */
}

/**
* Add the correct font size in all browsers.
*/

small {
  font-size: 80%;
}

/**
* Prevent `sub` and `sup` elements from affecting the line height in
* all browsers.
*/

sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}

sub {
  bottom: -0.25em;
}

sup {
  top: -0.5em;
}

/* Embedded content
    ========================================================================== */

/**
* Remove the border on images inside links in IE 10.
*/

img {
  border-style: none;
}

/* Forms
    ========================================================================== */

/**
* 1. Change the font styles in all browsers.
* 2. Remove the margin in Firefox and Safari.
*/

button,
input,
optgroup,
select,
textarea {
  font-family: inherit;
  /* 1 */
  font-size: 100%;
  /* 1 */
  line-height: 1.15;
  /* 1 */
  margin: 0;
  /* 2 */
  background-color: transparent;
}

/**
* Show the overflow in IE.
* 1. Show the overflow in Edge.
*/

button,
input {
  /* 1 */
  overflow: visible;
  cursor: pointer;
}

/**
* Remove the inheritance of text transform in Edge, Firefox, and IE.
* 1. Remove the inheritance of text transform in Firefox.
*/

button,
select {
  /* 1 */
  text-transform: none;
}

/**
* Correct the inability to style clickable types in iOS and Safari.
*/

button,
[type="button"],
[type="reset"],
[type="submit"] {
  -webkit-appearance: button;
  outline: none !important;
}

/**
* Remove the inner border and padding in Firefox.
*/

button::-moz-focus-inner,
[type="button"]::-moz-focus-inner,
[type="reset"]::-moz-focus-inner,
[type="submit"]::-moz-focus-inner {
  border-style: none;
  padding: 0;
}

/**
* Restore the focus styles unset by the previous rule.
*/

button:-moz-focusring,
[type="button"]:-moz-focusring,
[type="reset"]:-moz-focusring,
[type="submit"]:-moz-focusring {
  outline: 1px dotted ButtonText;
}

/**
* Correct the padding in Firefox.
*/

fieldset {
  padding: 0.35em 0.75em 0.625em;
}

/**
* 1. Correct the text wrapping in Edge and IE.
* 2. Correct the color inheritance from `fieldset` elements in IE.
* 3. Remove the padding so developers are not caught out when they zero out
*    `fieldset` elements in all browsers.
*/

legend {
  box-sizing: border-box;
  /* 1 */
  color: inherit;
  /* 2 */
  display: table;
  /* 1 */
  max-width: 100%;
  /* 1 */
  padding: 0;
  /* 3 */
  white-space: normal;
  /* 1 */
}

/**
* Add the correct vertical alignment in Chrome, Firefox, and Opera.
*/

progress {
  vertical-align: baseline;
}

/**
* Remove the default vertical scrollbar in IE 10+.
*/

textarea {
  overflow: auto;
}

/**
* 1. Add the correct box sizing in IE 10.
* 2. Remove the padding in IE 10.
*/

[type="checkbox"],
[type="radio"] {
  box-sizing: border-box;
  /* 1 */
  padding: 0;
  /* 2 */
}

/**
* Correct the cursor style of increment and decrement buttons in Chrome.
*/

[type="number"]::-webkit-inner-spin-button,
[type="number"]::-webkit-outer-spin-button {
  height: auto;
}

/**
* 1. Correct the odd appearance in Chrome and Safari.
* 2. Correct the outline style in Safari.
*/

[type="search"] {
  -webkit-appearance: textfield;
  /* 1 */
  outline-offset: -2px;
  /* 2 */
}

/**
* Remove the inner padding in Chrome and Safari on macOS.
*/

[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}

/**
* 1. Correct the inability to style clickable types in iOS and Safari.
* 2. Change font properties to `inherit` in Safari.
*/

::-webkit-file-upload-button {
  -webkit-appearance: button;
  /* 1 */
  font: inherit;
  /* 2 */
}

/* Interactive
    ========================================================================== */

/*
* Add the correct display in Edge, IE 10+, and Firefox.
*/

details {
  display: block;
}

/*
* Add the correct display in all browsers.
*/

summary {
  display: list-item;
}

/* Misc
    ========================================================================== */

/**
* Add the correct display in IE 10+.
*/

template {
  display: none;
}

/**
* Add the correct display in IE 10.
*/

[hidden] {
  display: none;
}

/* additional for common */
*,
*:before,
*:after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
/*포틀릿 간격*/
.col,
.col-1,
.col-10,
.col-11,
.col-12,
.col-2,
.col-3,
.col-4,
.col-5,
.col-6,
.col-7,
.col-8,
.col-9,
.col-auto,
.col-lg,
.col-lg-1,
.col-lg-10,
.col-lg-11,
.col-lg-12,
.col-lg-2,
.col-lg-3,
.col-lg-4,
.col-lg-5,
.col-lg-6,
.col-lg-7,
.col-lg-8,
.col-lg-9,
.col-lg-auto,
.col-md,
.col-md-1,
.col-md-10,
.col-md-11,
.col-md-12,
.col-md-2,
.col-md-3,
.col-md-4,
.col-md-5,
.col-md-6,
.col-md-7,
.col-md-8,
.col-md-9,
.col-md-auto,
.col-sm,
.col-sm-1,
.col-sm-10,
.col-sm-11,
.col-sm-12,
.col-sm-2,
.col-sm-3,
.col-sm-4,
.col-sm-5,
.col-sm-6,
.col-sm-7,
.col-sm-8,
.col-sm-9,
.col-sm-auto,
.col-xl,
.col-xl-1,
.col-xl-10,
.col-xl-11,
.col-xl-12,
.col-xl-2,
.col-xl-3,
.col-xl-4,
.col-xl-5,
.col-xl-6,
.col-xl-7,
.col-xl-8,
.col-xl-9,
.col-xl-auto {
  padding-right: 5px !important;
  padding-left: 5px !important;
}
/** common */
.h100 {
  height: 100%;
}
.bd-no {
  border: none !important;
}

html,
body {
  margin: 0;
  padding: 0;
  font-family: "Noto Sans KR", sans-serif;
  /* font-family: "Nanum Gothic", sans-serif; */
  font-size: 13px;
  color: #3e3e3e;
  line-height: 1.4em;
  -webkit-font-smoothing: antialiased;
}

ul,
ol,
li {
  margin: 0;
  padding: 0;
  list-style: none;
}

dl,
dt,
dd {
  margin: 0;
  padding: 0;
}

input[type="text"],
input[type="password"] {
  width: 100%;
  height: 25px;
  padding: 0 0 0 8px;
  font-family: "Noto Sans KR", sans-serif;
  font-size: 13px;
  text-align: left;
  line-height: normal;
  color: #30313a;
  border: 1px solid #d8dee4;
  box-sizing: border-box;
  outline: none;
}

input[type="checkbox"],
input[type="radio"] {
  margin: 0 0 0 15px;
}

input[type="checkbox"]:first-child,
input[type="radio"]:first-child {
  margin: 0;
}

legend {
  display: block;
  position: absolute;
  top: -1000em;
  left: 0;
  width: 1px;
  height: 1px;
  overflow: hidden;
}

fieldset {
  padding: 0;
  border: none;
}

a {
  text-decoration: none;
  color: #333;
}
a:hover {
  color: #333;
  text-decoration: underline #666;
}

em {
  font-style: normal;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  margin: 0;
  padding: 0;
  line-height: normal;
}

/* scroll */
::-webkit-scrollbar {
  width: 15px;
  /*스크롤바의 너비*/
}

::-webkit-scrollbar-thumb {
  background-color: #e2e5e5;
  background-clip: padding-box;
  border: 4px solid transparent;
  /* border-top-left-radius: 100px;
    border-bottom-right-radius: 50px; */
}

::-webkit-scrollbar-track {
  background-color: #f2f2f2;
  border-radius: 0 0 5px 0;
}

/* scroll end */
/*global skip navigation*/
.for-a11y,
.blind {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  border: 0;
  clip: rect(0 0 0 0);
  overflow: hidden;
  text-indent: -5000em;
}

#skipNavigation {
}

#skipNavigation a {
  position: absolute;
  left: 0;
  top: -100px;
  z-index: 1020;
  display: block;
  padding: 9px 0;
  width: 100%;
  background: #1179ea;
  font-size: 0;
  line-height: 0;
  color: #fff;
  text-align: center;
  text-decoration: none;
}

#skipNavigation a:active,
#skipNavigation a:focus {
  top: 0;
  font-size: 13px;
  font-weight: bold;
  line-height: 1.5;
  opacity: 0.7;
}
</style>
