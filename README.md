
@charset "UTF-8";	@charset "UTF-8";
/*!	/*!
* Start Bootstrap - Shop Homepage v5.0.5 (https://startbootstrap.com/template/shop-homepage)	* Start Bootstrap - Shop Homepage v5.0.6 (https://startbootstrap.com/template/shop-homepage)
* Copyright 2013-2022 Start Bootstrap	* Copyright 2013-2023 Start Bootstrap
* Licensed under MIT (https://github.com/StartBootstrap/startbootstrap-shop-homepage/blob/master/LICENSE)	* Licensed under MIT (https://github.com/StartBootstrap/startbootstrap-shop-homepage/blob/master/LICENSE)
*/	*/
/*!	/*!
 * Bootstrap v5.1.3 (https://getbootstrap.com/)	 * Bootstrap  v5.2.3 (https://getbootstrap.com/)
 * Copyright 2011-2021 The Bootstrap Authors	 * Copyright 2011-2022 The Bootstrap Authors
 * Copyright 2011-2021 Twitter, Inc.	 * Copyright 2011-2022 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/main/LICENSE)	 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/main/LICENSE)
 */	 */
:root {	:root {
@@ -21,6 +21,7 @@
  --bs-green: #198754;	  --bs-green: #198754;
  --bs-teal: #20c997;	  --bs-teal: #20c997;
  --bs-cyan: #0dcaf0;	  --bs-cyan: #0dcaf0;
  --bs-black: #000;
  --bs-white: #fff;	  --bs-white: #fff;
  --bs-gray: #6c757d;	  --bs-gray: #6c757d;
  --bs-gray-dark: #343a40;	  --bs-gray-dark: #343a40;
@@ -53,7 +54,7 @@
  --bs-black-rgb: 0, 0, 0;	  --bs-black-rgb: 0, 0, 0;
  --bs-body-color-rgb: 33, 37, 41;	  --bs-body-color-rgb: 33, 37, 41;
  --bs-body-bg-rgb: 255, 255, 255;	  --bs-body-bg-rgb: 255, 255, 255;
  --bs-font-sans-serif: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";	  --bs-font-sans-serif: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", "Noto Sans", "Liberation Sans", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  --bs-font-monospace: SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;	  --bs-font-monospace: SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
  --bs-gradient: linear-gradient(180deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0));	  --bs-gradient: linear-gradient(180deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0));
  --bs-body-font-family: var(--bs-font-sans-serif);	  --bs-body-font-family: var(--bs-font-sans-serif);
@@ -62,6 +63,20 @@
  --bs-body-line-height: 1.5;	  --bs-body-line-height: 1.5;
  --bs-body-color: #212529;	  --bs-body-color: #212529;
  --bs-body-bg: #fff;	  --bs-body-bg: #fff;
  --bs-border-width: 1px;
  --bs-border-style: solid;
  --bs-border-color: #dee2e6;
  --bs-border-color-translucent: rgba(0, 0, 0, 0.175);
  --bs-border-radius: 0.375rem;
  --bs-border-radius-sm: 0.25rem;
  --bs-border-radius-lg: 0.5rem;
  --bs-border-radius-xl: 1rem;
  --bs-border-radius-2xl: 2rem;
  --bs-border-radius-pill: 50rem;
  --bs-link-color: #0d6efd;
  --bs-link-hover-color: #0a58ca;
  --bs-code-color: #d63384;
  --bs-highlight-bg: #fff3cd;
}	}


*,	*,
@@ -92,15 +107,11 @@ body {
hr {	hr {
  margin: 1rem 0;	  margin: 1rem 0;
  color: inherit;	  color: inherit;
  background-color: currentColor;	
  border: 0;	  border: 0;
  border-top: 1px solid;
  opacity: 0.25;	  opacity: 0.25;
}	}


hr:not([size]) {	
  height: 1px;	
}	

h6, .h6, h5, .h5, h4, .h4, h3, .h3, h2, .h2, h1, .h1 {	h6, .h6, h5, .h5, h4, .h4, h3, .h3, h2, .h2, h1, .h1 {
  margin-top: 0;	  margin-top: 0;
  margin-bottom: 0.5rem;	  margin-bottom: 0.5rem;
@@ -157,8 +168,7 @@ p {
  margin-bottom: 1rem;	  margin-bottom: 1rem;
}	}


abbr[title],	abbr[title] {
abbr[data-bs-original-title] {	
  -webkit-text-decoration: underline dotted;	  -webkit-text-decoration: underline dotted;
          text-decoration: underline dotted;	          text-decoration: underline dotted;
  cursor: help;	  cursor: help;
@@ -214,8 +224,8 @@ small, .small {
}	}


mark, .mark {	mark, .mark {
  padding: 0.2em;	  padding: 0.1875em;
  background-color: #fcf8e3;	  background-color: var(--bs-highlight-bg);
}	}


sub,	sub,
@@ -235,11 +245,11 @@ sup {
}	}


a {	a {
  color: #0d6efd;	  color: var(--bs-link-color);
  text-decoration: underline;	  text-decoration: underline;
}	}
a:hover {	a:hover {
  color: #0a58ca;	  color: var(--bs-link-hover-color);
}	}


a:not([href]):not([class]), a:not([href]):not([class]):hover {	a:not([href]):not([class]), a:not([href]):not([class]):hover {
@@ -253,8 +263,6 @@ kbd,
samp {	samp {
  font-family: var(--bs-font-monospace);	  font-family: var(--bs-font-monospace);
  font-size: 1em;	  font-size: 1em;
  direction: ltr /* rtl:ignore */;	
  unicode-bidi: bidi-override;	
}	}


pre {	pre {
@@ -272,24 +280,23 @@ pre code {


code {	code {
  font-size: 0.875em;	  font-size: 0.875em;
  color: #d63384;	  color: var(--bs-code-color);
  word-wrap: break-word;	  word-wrap: break-word;
}	}
a > code {	a > code {
  color: inherit;	  color: inherit;
}	}


kbd {	kbd {
  padding: 0.2rem 0.4rem;	  padding: 0.1875rem 0.375rem;
  font-size: 0.875em;	  font-size: 0.875em;
  color: #fff;	  color: var(--bs-body-bg);
  background-color: #212529;	  background-color: var(--bs-body-color);
  border-radius: 0.2rem;	  border-radius: 0.25rem;
}	}
kbd kbd {	kbd kbd {
  padding: 0;	  padding: 0;
  font-size: 1em;	  font-size: 1em;
  font-weight: 700;	
}	}


figure {	figure {
@@ -368,8 +375,8 @@ select:disabled {
  opacity: 1;	  opacity: 1;
}	}


[list]::-webkit-calendar-picker-indicator {	[list]:not([type=date]):not([type=datetime-local]):not([type=month]):not([type=week]):not([type=time])::-webkit-calendar-picker-indicator {
  display: none;	  display: none !important;
}	}


button,	button,
@@ -453,16 +460,8 @@ legend + * {
  padding: 0;	  padding: 0;
}	}


::-webkit-file-upload-button {	
  font: inherit;	
}	

::file-selector-button {	::file-selector-button {
  font: inherit;	  font: inherit;
}	

::-webkit-file-upload-button {	
  font: inherit;	
  -webkit-appearance: button;	  -webkit-appearance: button;
}	}


@@ -606,8 +605,8 @@ progress {
.img-thumbnail {	.img-thumbnail {
  padding: 0.25rem;	  padding: 0.25rem;
  background-color: #fff;	  background-color: #fff;
  border: 1px solid #dee2e6;	  border: 1px solid var(--bs-border-color);
  border-radius: 0.25rem;	  border-radius: 0.375rem;
  max-width: 100%;	  max-width: 100%;
  height: auto;	  height: auto;
}	}
@@ -633,9 +632,11 @@ progress {
.container-lg,	.container-lg,
.container-md,	.container-md,
.container-sm {	.container-sm {
  --bs-gutter-x: 1.5rem;
  --bs-gutter-y: 0;
  width: 100%;	  width: 100%;
  padding-right: var(--bs-gutter-x, 0.75rem);	  padding-right: calc(var(--bs-gutter-x) * 0.5);
  padding-left: var(--bs-gutter-x, 0.75rem);	  padding-left: calc(var(--bs-gutter-x) * 0.5);
  margin-right: auto;	  margin-right: auto;
  margin-left: auto;	  margin-left: auto;
}	}
@@ -895,1081 +896,863 @@ progress {
  .col-sm {	  .col-sm {
    flex: 1 0 0%;	    flex: 1 0 0%;
  }	  }

  .row-cols-sm-auto > * {	  .row-cols-sm-auto > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: auto;	    width: auto;
  }	  }

  .row-cols-sm-1 > * {	  .row-cols-sm-1 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 100%;	    width: 100%;
  }	  }

  .row-cols-sm-2 > * {	  .row-cols-sm-2 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 50%;	    width: 50%;
  }	  }

  .row-cols-sm-3 > * {	  .row-cols-sm-3 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 33.3333333333%;	    width: 33.3333333333%;
  }	  }

  .row-cols-sm-4 > * {	  .row-cols-sm-4 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 25%;	    width: 25%;
  }	  }

  .row-cols-sm-5 > * {	  .row-cols-sm-5 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 20%;	    width: 20%;
  }	  }

  .row-cols-sm-6 > * {	  .row-cols-sm-6 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 16.6666666667%;	    width: 16.6666666667%;
  }	  }

  .col-sm-auto {	  .col-sm-auto {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: auto;	    width: auto;
  }	  }

  .col-sm-1 {	  .col-sm-1 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 8.33333333%;	    width: 8.33333333%;
  }	  }

  .col-sm-2 {	  .col-sm-2 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 16.66666667%;	    width: 16.66666667%;
  }	  }

  .col-sm-3 {	  .col-sm-3 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 25%;	    width: 25%;
  }	  }

  .col-sm-4 {	  .col-sm-4 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 33.33333333%;	    width: 33.33333333%;
  }	  }

  .col-sm-5 {	  .col-sm-5 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 41.66666667%;	    width: 41.66666667%;
  }	  }

  .col-sm-6 {	  .col-sm-6 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 50%;	    width: 50%;
  }	  }

  .col-sm-7 {	  .col-sm-7 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 58.33333333%;	    width: 58.33333333%;
  }	  }

  .col-sm-8 {	  .col-sm-8 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 66.66666667%;	    width: 66.66666667%;
  }	  }

  .col-sm-9 {	  .col-sm-9 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 75%;	    width: 75%;
  }	  }

  .col-sm-10 {	  .col-sm-10 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 83.33333333%;	    width: 83.33333333%;
  }	  }

  .col-sm-11 {	  .col-sm-11 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 91.66666667%;	    width: 91.66666667%;
  }	  }

  .col-sm-12 {	  .col-sm-12 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 100%;	    width: 100%;
  }	  }

  .offset-sm-0 {	  .offset-sm-0 {
    margin-left: 0;	    margin-left: 0;
  }	  }

  .offset-sm-1 {	  .offset-sm-1 {
    margin-left: 8.33333333%;	    margin-left: 8.33333333%;
  }	  }

  .offset-sm-2 {	  .offset-sm-2 {
    margin-left: 16.66666667%;	    margin-left: 16.66666667%;
  }	  }

  .offset-sm-3 {	  .offset-sm-3 {
    margin-left: 25%;	    margin-left: 25%;
  }	  }

  .offset-sm-4 {	  .offset-sm-4 {
    margin-left: 33.33333333%;	    margin-left: 33.33333333%;
  }	  }

  .offset-sm-5 {	  .offset-sm-5 {
    margin-left: 41.66666667%;	    margin-left: 41.66666667%;
  }	  }

  .offset-sm-6 {	  .offset-sm-6 {
    margin-left: 50%;	    margin-left: 50%;
  }	  }

  .offset-sm-7 {	  .offset-sm-7 {
    margin-left: 58.33333333%;	    margin-left: 58.33333333%;
  }	  }

  .offset-sm-8 {	  .offset-sm-8 {
    margin-left: 66.66666667%;	    margin-left: 66.66666667%;
  }	  }

  .offset-sm-9 {	  .offset-sm-9 {
    margin-left: 75%;	    margin-left: 75%;
  }	  }

  .offset-sm-10 {	  .offset-sm-10 {
    margin-left: 83.33333333%;	    margin-left: 83.33333333%;
  }	  }

  .offset-sm-11 {	  .offset-sm-11 {
    margin-left: 91.66666667%;	    margin-left: 91.66666667%;
  }	  }

  .g-sm-0,	  .g-sm-0,
.gx-sm-0 {	  .gx-sm-0 {
    --bs-gutter-x: 0;	    --bs-gutter-x: 0;
  }	  }

  .g-sm-0,	  .g-sm-0,
.gy-sm-0 {	  .gy-sm-0 {
    --bs-gutter-y: 0;	    --bs-gutter-y: 0;
  }	  }

  .g-sm-1,	  .g-sm-1,
.gx-sm-1 {	  .gx-sm-1 {
    --bs-gutter-x: 0.25rem;	    --bs-gutter-x: 0.25rem;
  }	  }

  .g-sm-1,	  .g-sm-1,
.gy-sm-1 {	  .gy-sm-1 {
    --bs-gutter-y: 0.25rem;	    --bs-gutter-y: 0.25rem;
  }	  }

  .g-sm-2,	  .g-sm-2,
.gx-sm-2 {	  .gx-sm-2 {
    --bs-gutter-x: 0.5rem;	    --bs-gutter-x: 0.5rem;
  }	  }

  .g-sm-2,	  .g-sm-2,
.gy-sm-2 {	  .gy-sm-2 {
    --bs-gutter-y: 0.5rem;	    --bs-gutter-y: 0.5rem;
  }	  }

  .g-sm-3,	  .g-sm-3,
.gx-sm-3 {	  .gx-sm-3 {
    --bs-gutter-x: 1rem;	    --bs-gutter-x: 1rem;
  }	  }

  .g-sm-3,	  .g-sm-3,
.gy-sm-3 {	  .gy-sm-3 {
    --bs-gutter-y: 1rem;	    --bs-gutter-y: 1rem;
  }	  }

  .g-sm-4,	  .g-sm-4,
.gx-sm-4 {	  .gx-sm-4 {
    --bs-gutter-x: 1.5rem;	    --bs-gutter-x: 1.5rem;
  }	  }

  .g-sm-4,	  .g-sm-4,
.gy-sm-4 {	  .gy-sm-4 {
    --bs-gutter-y: 1.5rem;	    --bs-gutter-y: 1.5rem;
  }	  }

  .g-sm-5,	  .g-sm-5,
.gx-sm-5 {	  .gx-sm-5 {
    --bs-gutter-x: 3rem;	    --bs-gutter-x: 3rem;
  }	  }

  .g-sm-5,	  .g-sm-5,
.gy-sm-5 {	  .gy-sm-5 {
    --bs-gutter-y: 3rem;	    --bs-gutter-y: 3rem;
  }	  }
}	}
@media (min-width: 768px) {	@media (min-width: 768px) {
  .col-md {	  .col-md {
    flex: 1 0 0%;	    flex: 1 0 0%;
  }	  }

  .row-cols-md-auto > * {	  .row-cols-md-auto > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: auto;	    width: auto;
  }	  }

  .row-cols-md-1 > * {	  .row-cols-md-1 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 100%;	    width: 100%;
  }	  }

  .row-cols-md-2 > * {	  .row-cols-md-2 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 50%;	    width: 50%;
  }	  }

  .row-cols-md-3 > * {	  .row-cols-md-3 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 33.3333333333%;	    width: 33.3333333333%;
  }	  }

  .row-cols-md-4 > * {	  .row-cols-md-4 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 25%;	    width: 25%;
  }	  }

  .row-cols-md-5 > * {	  .row-cols-md-5 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 20%;	    width: 20%;
  }	  }

  .row-cols-md-6 > * {	  .row-cols-md-6 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 16.6666666667%;	    width: 16.6666666667%;
  }	  }

  .col-md-auto {	  .col-md-auto {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: auto;	    width: auto;
  }	  }

  .col-md-1 {	  .col-md-1 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 8.33333333%;	    width: 8.33333333%;
  }	  }

  .col-md-2 {	  .col-md-2 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 16.66666667%;	    width: 16.66666667%;
  }	  }

  .col-md-3 {	  .col-md-3 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 25%;	    width: 25%;
  }	  }

  .col-md-4 {	  .col-md-4 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 33.33333333%;	    width: 33.33333333%;
  }	  }

  .col-md-5 {	  .col-md-5 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 41.66666667%;	    width: 41.66666667%;
  }	  }

  .col-md-6 {	  .col-md-6 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 50%;	    width: 50%;
  }	  }

  .col-md-7 {	  .col-md-7 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 58.33333333%;	    width: 58.33333333%;
  }	  }

  .col-md-8 {	  .col-md-8 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 66.66666667%;	    width: 66.66666667%;
  }	  }

  .col-md-9 {	  .col-md-9 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 75%;	    width: 75%;
  }	  }

  .col-md-10 {	  .col-md-10 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 83.33333333%;	    width: 83.33333333%;
  }	  }

  .col-md-11 {	  .col-md-11 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 91.66666667%;	    width: 91.66666667%;
  }	  }

  .col-md-12 {	  .col-md-12 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 100%;	    width: 100%;
  }	  }

  .offset-md-0 {	  .offset-md-0 {
    margin-left: 0;	    margin-left: 0;
  }	  }

  .offset-md-1 {	  .offset-md-1 {
    margin-left: 8.33333333%;	    margin-left: 8.33333333%;
  }	  }

  .offset-md-2 {	  .offset-md-2 {
    margin-left: 16.66666667%;	    margin-left: 16.66666667%;
  }	  }

  .offset-md-3 {	  .offset-md-3 {
    margin-left: 25%;	    margin-left: 25%;
  }	  }

  .offset-md-4 {	  .offset-md-4 {
    margin-left: 33.33333333%;	    margin-left: 33.33333333%;
  }	  }

  .offset-md-5 {	  .offset-md-5 {
    margin-left: 41.66666667%;	    margin-left: 41.66666667%;
  }	  }

  .offset-md-6 {	  .offset-md-6 {
    margin-left: 50%;	    margin-left: 50%;
  }	  }

  .offset-md-7 {	  .offset-md-7 {
    margin-left: 58.33333333%;	    margin-left: 58.33333333%;
  }	  }

  .offset-md-8 {	  .offset-md-8 {
    margin-left: 66.66666667%;	    margin-left: 66.66666667%;
  }	  }

  .offset-md-9 {	  .offset-md-9 {
    margin-left: 75%;	    margin-left: 75%;
  }	  }

  .offset-md-10 {	  .offset-md-10 {
    margin-left: 83.33333333%;	    margin-left: 83.33333333%;
  }	  }

  .offset-md-11 {	  .offset-md-11 {
    margin-left: 91.66666667%;	    margin-left: 91.66666667%;
  }	  }

  .g-md-0,	  .g-md-0,
.gx-md-0 {	  .gx-md-0 {
    --bs-gutter-x: 0;	    --bs-gutter-x: 0;
  }	  }

  .g-md-0,	  .g-md-0,
.gy-md-0 {	  .gy-md-0 {
    --bs-gutter-y: 0;	    --bs-gutter-y: 0;
  }	  }

  .g-md-1,	  .g-md-1,
.gx-md-1 {	  .gx-md-1 {
    --bs-gutter-x: 0.25rem;	    --bs-gutter-x: 0.25rem;
  }	  }

  .g-md-1,	  .g-md-1,
.gy-md-1 {	  .gy-md-1 {
    --bs-gutter-y: 0.25rem;	    --bs-gutter-y: 0.25rem;
  }	  }

  .g-md-2,	  .g-md-2,
.gx-md-2 {	  .gx-md-2 {
    --bs-gutter-x: 0.5rem;	    --bs-gutter-x: 0.5rem;
  }	  }

  .g-md-2,	  .g-md-2,
.gy-md-2 {	  .gy-md-2 {
    --bs-gutter-y: 0.5rem;	    --bs-gutter-y: 0.5rem;
  }	  }

  .g-md-3,	  .g-md-3,
.gx-md-3 {	  .gx-md-3 {
    --bs-gutter-x: 1rem;	    --bs-gutter-x: 1rem;
  }	  }

  .g-md-3,	  .g-md-3,
.gy-md-3 {	  .gy-md-3 {
    --bs-gutter-y: 1rem;	    --bs-gutter-y: 1rem;
  }	  }

  .g-md-4,	  .g-md-4,
.gx-md-4 {	  .gx-md-4 {
    --bs-gutter-x: 1.5rem;	    --bs-gutter-x: 1.5rem;
  }	  }

  .g-md-4,	  .g-md-4,
.gy-md-4 {	  .gy-md-4 {
    --bs-gutter-y: 1.5rem;	    --bs-gutter-y: 1.5rem;
  }	  }

  .g-md-5,	  .g-md-5,
.gx-md-5 {	  .gx-md-5 {
    --bs-gutter-x: 3rem;	    --bs-gutter-x: 3rem;
  }	  }

  .g-md-5,	  .g-md-5,
.gy-md-5 {	  .gy-md-5 {
    --bs-gutter-y: 3rem;	    --bs-gutter-y: 3rem;
  }	  }
}	}
@media (min-width: 992px) {	@media (min-width: 992px) {
  .col-lg {	  .col-lg {
    flex: 1 0 0%;	    flex: 1 0 0%;
  }	  }

  .row-cols-lg-auto > * {	  .row-cols-lg-auto > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: auto;	    width: auto;
  }	  }

  .row-cols-lg-1 > * {	  .row-cols-lg-1 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 100%;	    width: 100%;
  }	  }

  .row-cols-lg-2 > * {	  .row-cols-lg-2 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 50%;	    width: 50%;
  }	  }

  .row-cols-lg-3 > * {	  .row-cols-lg-3 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 33.3333333333%;	    width: 33.3333333333%;
  }	  }

  .row-cols-lg-4 > * {	  .row-cols-lg-4 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 25%;	    width: 25%;
  }	  }

  .row-cols-lg-5 > * {	  .row-cols-lg-5 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 20%;	    width: 20%;
  }	  }

  .row-cols-lg-6 > * {	  .row-cols-lg-6 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 16.6666666667%;	    width: 16.6666666667%;
  }	  }

  .col-lg-auto {	  .col-lg-auto {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: auto;	    width: auto;
  }	  }

  .col-lg-1 {	  .col-lg-1 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 8.33333333%;	    width: 8.33333333%;
  }	  }

  .col-lg-2 {	  .col-lg-2 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 16.66666667%;	    width: 16.66666667%;
  }	  }

  .col-lg-3 {	  .col-lg-3 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 25%;	    width: 25%;
  }	  }

  .col-lg-4 {	  .col-lg-4 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 33.33333333%;	    width: 33.33333333%;
  }	  }

  .col-lg-5 {	  .col-lg-5 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 41.66666667%;	    width: 41.66666667%;
  }	  }

  .col-lg-6 {	  .col-lg-6 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 50%;	    width: 50%;
  }	  }

  .col-lg-7 {	  .col-lg-7 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 58.33333333%;	    width: 58.33333333%;
  }	  }

  .col-lg-8 {	  .col-lg-8 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 66.66666667%;	    width: 66.66666667%;
  }	  }

  .col-lg-9 {	  .col-lg-9 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 75%;	    width: 75%;
  }	  }

  .col-lg-10 {	  .col-lg-10 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 83.33333333%;	    width: 83.33333333%;
  }	  }

  .col-lg-11 {	  .col-lg-11 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 91.66666667%;	    width: 91.66666667%;
  }	  }

  .col-lg-12 {	  .col-lg-12 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 100%;	    width: 100%;
  }	  }

  .offset-lg-0 {	  .offset-lg-0 {
    margin-left: 0;	    margin-left: 0;
  }	  }

  .offset-lg-1 {	  .offset-lg-1 {
    margin-left: 8.33333333%;	    margin-left: 8.33333333%;
  }	  }

  .offset-lg-2 {	  .offset-lg-2 {
    margin-left: 16.66666667%;	    margin-left: 16.66666667%;
  }	  }

  .offset-lg-3 {	  .offset-lg-3 {
    margin-left: 25%;	    margin-left: 25%;
  }	  }

  .offset-lg-4 {	  .offset-lg-4 {
    margin-left: 33.33333333%;	    margin-left: 33.33333333%;
  }	  }

  .offset-lg-5 {	  .offset-lg-5 {
    margin-left: 41.66666667%;	    margin-left: 41.66666667%;
  }	  }

  .offset-lg-6 {	  .offset-lg-6 {
    margin-left: 50%;	    margin-left: 50%;
  }	  }

  .offset-lg-7 {	  .offset-lg-7 {
    margin-left: 58.33333333%;	    margin-left: 58.33333333%;
  }	  }

  .offset-lg-8 {	  .offset-lg-8 {
    margin-left: 66.66666667%;	    margin-left: 66.66666667%;
  }	  }

  .offset-lg-9 {	  .offset-lg-9 {
    margin-left: 75%;	    margin-left: 75%;
  }	  }

  .offset-lg-10 {	  .offset-lg-10 {
    margin-left: 83.33333333%;	    margin-left: 83.33333333%;
  }	  }

  .offset-lg-11 {	  .offset-lg-11 {
    margin-left: 91.66666667%;	    margin-left: 91.66666667%;
  }	  }

  .g-lg-0,	  .g-lg-0,
.gx-lg-0 {	  .gx-lg-0 {
    --bs-gutter-x: 0;	    --bs-gutter-x: 0;
  }	  }

  .g-lg-0,	  .g-lg-0,
.gy-lg-0 {	  .gy-lg-0 {
    --bs-gutter-y: 0;	    --bs-gutter-y: 0;
  }	  }

  .g-lg-1,	  .g-lg-1,
.gx-lg-1 {	  .gx-lg-1 {
    --bs-gutter-x: 0.25rem;	    --bs-gutter-x: 0.25rem;
  }	  }

  .g-lg-1,	  .g-lg-1,
.gy-lg-1 {	  .gy-lg-1 {
    --bs-gutter-y: 0.25rem;	    --bs-gutter-y: 0.25rem;
  }	  }

  .g-lg-2,	  .g-lg-2,
.gx-lg-2 {	  .gx-lg-2 {
    --bs-gutter-x: 0.5rem;	    --bs-gutter-x: 0.5rem;
  }	  }

  .g-lg-2,	  .g-lg-2,
.gy-lg-2 {	  .gy-lg-2 {
    --bs-gutter-y: 0.5rem;	    --bs-gutter-y: 0.5rem;
  }	  }

  .g-lg-3,	  .g-lg-3,
.gx-lg-3 {	  .gx-lg-3 {
    --bs-gutter-x: 1rem;	    --bs-gutter-x: 1rem;
  }	  }

  .g-lg-3,	  .g-lg-3,
.gy-lg-3 {	  .gy-lg-3 {
    --bs-gutter-y: 1rem;	    --bs-gutter-y: 1rem;
  }	  }

  .g-lg-4,	  .g-lg-4,
.gx-lg-4 {	  .gx-lg-4 {
    --bs-gutter-x: 1.5rem;	    --bs-gutter-x: 1.5rem;
  }	  }

  .g-lg-4,	  .g-lg-4,
.gy-lg-4 {	  .gy-lg-4 {
    --bs-gutter-y: 1.5rem;	    --bs-gutter-y: 1.5rem;
  }	  }

  .g-lg-5,	  .g-lg-5,
.gx-lg-5 {	  .gx-lg-5 {
    --bs-gutter-x: 3rem;	    --bs-gutter-x: 3rem;
  }	  }

  .g-lg-5,	  .g-lg-5,
.gy-lg-5 {	  .gy-lg-5 {
    --bs-gutter-y: 3rem;	    --bs-gutter-y: 3rem;
  }	  }
}	}
@media (min-width: 1200px) {	@media (min-width: 1200px) {
  .col-xl {	  .col-xl {
    flex: 1 0 0%;	    flex: 1 0 0%;
  }	  }

  .row-cols-xl-auto > * {	  .row-cols-xl-auto > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: auto;	    width: auto;
  }	  }

  .row-cols-xl-1 > * {	  .row-cols-xl-1 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 100%;	    width: 100%;
  }	  }

  .row-cols-xl-2 > * {	  .row-cols-xl-2 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 50%;	    width: 50%;
  }	  }

  .row-cols-xl-3 > * {	  .row-cols-xl-3 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 33.3333333333%;	    width: 33.3333333333%;
  }	  }

  .row-cols-xl-4 > * {	  .row-cols-xl-4 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 25%;	    width: 25%;
  }	  }

  .row-cols-xl-5 > * {	  .row-cols-xl-5 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 20%;	    width: 20%;
  }	  }

  .row-cols-xl-6 > * {	  .row-cols-xl-6 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 16.6666666667%;	    width: 16.6666666667%;
  }	  }

  .col-xl-auto {	  .col-xl-auto {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: auto;	    width: auto;
  }	  }

  .col-xl-1 {	  .col-xl-1 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 8.33333333%;	    width: 8.33333333%;
  }	  }

  .col-xl-2 {	  .col-xl-2 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 16.66666667%;	    width: 16.66666667%;
  }	  }

  .col-xl-3 {	  .col-xl-3 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 25%;	    width: 25%;
  }	  }

  .col-xl-4 {	  .col-xl-4 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 33.33333333%;	    width: 33.33333333%;
  }	  }

  .col-xl-5 {	  .col-xl-5 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 41.66666667%;	    width: 41.66666667%;
  }	  }

  .col-xl-6 {	  .col-xl-6 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 50%;	    width: 50%;
  }	  }

  .col-xl-7 {	  .col-xl-7 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 58.33333333%;	    width: 58.33333333%;
  }	  }

  .col-xl-8 {	  .col-xl-8 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 66.66666667%;	    width: 66.66666667%;
  }	  }

  .col-xl-9 {	  .col-xl-9 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 75%;	    width: 75%;
  }	  }

  .col-xl-10 {	  .col-xl-10 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 83.33333333%;	    width: 83.33333333%;
  }	  }

  .col-xl-11 {	  .col-xl-11 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 91.66666667%;	    width: 91.66666667%;
  }	  }

  .col-xl-12 {	  .col-xl-12 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 100%;	    width: 100%;
  }	  }

  .offset-xl-0 {	  .offset-xl-0 {
    margin-left: 0;	    margin-left: 0;
  }	  }

  .offset-xl-1 {	  .offset-xl-1 {
    margin-left: 8.33333333%;	    margin-left: 8.33333333%;
  }	  }

  .offset-xl-2 {	  .offset-xl-2 {
    margin-left: 16.66666667%;	    margin-left: 16.66666667%;
  }	  }

  .offset-xl-3 {	  .offset-xl-3 {
    margin-left: 25%;	    margin-left: 25%;
  }	  }

  .offset-xl-4 {	  .offset-xl-4 {
    margin-left: 33.33333333%;	    margin-left: 33.33333333%;
  }	  }

  .offset-xl-5 {	  .offset-xl-5 {
    margin-left: 41.66666667%;	    margin-left: 41.66666667%;
  }	  }

  .offset-xl-6 {	  .offset-xl-6 {
    margin-left: 50%;	    margin-left: 50%;
  }	  }

  .offset-xl-7 {	  .offset-xl-7 {
    margin-left: 58.33333333%;	    margin-left: 58.33333333%;
  }	  }

  .offset-xl-8 {	  .offset-xl-8 {
    margin-left: 66.66666667%;	    margin-left: 66.66666667%;
  }	  }

  .offset-xl-9 {	  .offset-xl-9 {
    margin-left: 75%;	    margin-left: 75%;
  }	  }

  .offset-xl-10 {	  .offset-xl-10 {
    margin-left: 83.33333333%;	    margin-left: 83.33333333%;
  }	  }

  .offset-xl-11 {	  .offset-xl-11 {
    margin-left: 91.66666667%;	    margin-left: 91.66666667%;
  }	  }

  .g-xl-0,	  .g-xl-0,
.gx-xl-0 {	  .gx-xl-0 {
    --bs-gutter-x: 0;	    --bs-gutter-x: 0;
  }	  }

  .g-xl-0,	  .g-xl-0,
.gy-xl-0 {	  .gy-xl-0 {
    --bs-gutter-y: 0;	    --bs-gutter-y: 0;
  }	  }

  .g-xl-1,	  .g-xl-1,
.gx-xl-1 {	  .gx-xl-1 {
    --bs-gutter-x: 0.25rem;	    --bs-gutter-x: 0.25rem;
  }	  }

  .g-xl-1,	  .g-xl-1,
.gy-xl-1 {	  .gy-xl-1 {
    --bs-gutter-y: 0.25rem;	    --bs-gutter-y: 0.25rem;
  }	  }

  .g-xl-2,	  .g-xl-2,
.gx-xl-2 {	  .gx-xl-2 {
    --bs-gutter-x: 0.5rem;	    --bs-gutter-x: 0.5rem;
  }	  }

  .g-xl-2,	  .g-xl-2,
.gy-xl-2 {	  .gy-xl-2 {
    --bs-gutter-y: 0.5rem;	    --bs-gutter-y: 0.5rem;
  }	  }

  .g-xl-3,	  .g-xl-3,
.gx-xl-3 {	  .gx-xl-3 {
    --bs-gutter-x: 1rem;	    --bs-gutter-x: 1rem;
  }	  }

  .g-xl-3,	  .g-xl-3,
.gy-xl-3 {	  .gy-xl-3 {
    --bs-gutter-y: 1rem;	    --bs-gutter-y: 1rem;
  }	  }

  .g-xl-4,	  .g-xl-4,
.gx-xl-4 {	  .gx-xl-4 {
    --bs-gutter-x: 1.5rem;	    --bs-gutter-x: 1.5rem;
  }	  }

  .g-xl-4,	  .g-xl-4,
.gy-xl-4 {	  .gy-xl-4 {
    --bs-gutter-y: 1.5rem;	    --bs-gutter-y: 1.5rem;
  }	  }

  .g-xl-5,	  .g-xl-5,
.gx-xl-5 {	  .gx-xl-5 {
    --bs-gutter-x: 3rem;	    --bs-gutter-x: 3rem;
  }	  }

  .g-xl-5,	  .g-xl-5,
.gy-xl-5 {	  .gy-xl-5 {
    --bs-gutter-y: 3rem;	    --bs-gutter-y: 3rem;
  }	  }
}	}
@media (min-width: 1400px) {	@media (min-width: 1400px) {
  .col-xxl {	  .col-xxl {
    flex: 1 0 0%;	    flex: 1 0 0%;
  }	  }

  .row-cols-xxl-auto > * {	  .row-cols-xxl-auto > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: auto;	    width: auto;
  }	  }

  .row-cols-xxl-1 > * {	  .row-cols-xxl-1 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 100%;	    width: 100%;
  }	  }

  .row-cols-xxl-2 > * {	  .row-cols-xxl-2 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 50%;	    width: 50%;
  }	  }

  .row-cols-xxl-3 > * {	  .row-cols-xxl-3 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 33.3333333333%;	    width: 33.3333333333%;
  }	  }

  .row-cols-xxl-4 > * {	  .row-cols-xxl-4 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 25%;	    width: 25%;
  }	  }

  .row-cols-xxl-5 > * {	  .row-cols-xxl-5 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 20%;	    width: 20%;
  }	  }

  .row-cols-xxl-6 > * {	  .row-cols-xxl-6 > * {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 16.6666666667%;	    width: 16.6666666667%;
  }	  }

  .col-xxl-auto {	  .col-xxl-auto {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: auto;	    width: auto;
  }	  }

  .col-xxl-1 {	  .col-xxl-1 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 8.33333333%;	    width: 8.33333333%;
  }	  }

  .col-xxl-2 {	  .col-xxl-2 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 16.66666667%;	    width: 16.66666667%;
  }	  }

  .col-xxl-3 {	  .col-xxl-3 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 25%;	    width: 25%;
  }	  }

  .col-xxl-4 {	  .col-xxl-4 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 33.33333333%;	    width: 33.33333333%;
  }	  }

  .col-xxl-5 {	  .col-xxl-5 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 41.66666667%;	    width: 41.66666667%;
  }	  }

  .col-xxl-6 {	  .col-xxl-6 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 50%;	    width: 50%;
  }	  }

  .col-xxl-7 {	  .col-xxl-7 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 58.33333333%;	    width: 58.33333333%;
  }	  }

  .col-xxl-8 {	  .col-xxl-8 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 66.66666667%;	    width: 66.66666667%;
  }	  }

  .col-xxl-9 {	  .col-xxl-9 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 75%;	    width: 75%;
  }	  }

  .col-xxl-10 {	  .col-xxl-10 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 83.33333333%;	    width: 83.33333333%;
  }	  }

  .col-xxl-11 {	  .col-xxl-11 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 91.66666667%;	    width: 91.66666667%;
  }	  }

  .col-xxl-12 {	  .col-xxl-12 {
    flex: 0 0 auto;	    flex: 0 0 auto;
    width: 100%;	    width: 100%;
  }	  }

  .offset-xxl-0 {	  .offset-xxl-0 {
    margin-left: 0;	    margin-left: 0;
  }	  }

  .offset-xxl-1 {	  .offset-xxl-1 {
    margin-left: 8.33333333%;	    margin-left: 8.33333333%;
  }	  }

  .offset-xxl-2 {	  .offset-xxl-2 {
    margin-left: 16.66666667%;	    margin-left: 16.66666667%;
  }	  }

  .offset-xxl-3 {	  .offset-xxl-3 {
    margin-left: 25%;	    margin-left: 25%;
  }	  }

  .offset-xxl-4 {	  .offset-xxl-4 {
    margin-left: 33.33333333%;	    margin-left: 33.33333333%;
  }	  }

  .offset-xxl-5 {	  .offset-xxl-5 {
    margin-left: 41.66666667%;	    margin-left: 41.66666667%;
  }	  }

  .offset-xxl-6 {	  .offset-xxl-6 {
    margin-left: 50%;	    margin-left: 50%;
  }	  }

  .offset-xxl-7 {	  .offset-xxl-7 {
    margin-left: 58.33333333%;	    margin-left: 58.33333333%;
  }	  }

  .offset-xxl-8 {	  .offset-xxl-8 {
    margin-left: 66.66666667%;	    margin-left: 66.66666667%;
  }	  }

  .offset-xxl-9 {	  .offset-xxl-9 {
    margin-left: 75%;	    margin-left: 75%;
  }	  }

  .offset-xxl-10 {	  .offset-xxl-10 {
    margin-left: 83.33333333%;	    margin-left: 83.33333333%;
  }	  }

  .offset-xxl-11 {	  .offset-xxl-11 {
    margin-left: 91.66666667%;	    margin-left: 91.66666667%;
  }	  }

  .g-xxl-0,	  .g-xxl-0,
.gx-xxl-0 {	  .gx-xxl-0 {
    --bs-gutter-x: 0;	    --bs-gutter-x: 0;
  }	  }

  .g-xxl-0,	  .g-xxl-0,
.gy-xxl-0 {	  .gy-xxl-0 {
    --bs-gutter-y: 0;	    --bs-gutter-y: 0;
  }	  }

  .g-xxl-1,	  .g-xxl-1,
.gx-xxl-1 {	  .gx-xxl-1 {
    --bs-gutter-x: 0.25rem;	    --bs-gutter-x: 0.25rem;
  }	  }

  .g-xxl-1,	  .g-xxl-1,
.gy-xxl-1 {	  .gy-xxl-1 {
    --bs-gutter-y: 0.25rem;	    --bs-gutter-y: 0.25rem;
  }	  }

  .g-xxl-2,	  .g-xxl-2,
.gx-xxl-2 {	  .gx-xxl-2 {
    --bs-gutter-x: 0.5rem;	    --bs-gutter-x: 0.5rem;
  }	  }

  .g-xxl-2,	  .g-xxl-2,
.gy-xxl-2 {	  .gy-xxl-2 {
    --bs-gutter-y: 0.5rem;	    --bs-gutter-y: 0.5rem;
  }	  }

  .g-xxl-3,	  .g-xxl-3,
.gx-xxl-3 {	  .gx-xxl-3 {
    --bs-gutter-x: 1rem;	    --bs-gutter-x: 1rem;
  }	  }

  .g-xxl-3,	  .g-xxl-3,
.gy-xxl-3 {	  .gy-xxl-3 {
    --bs-gutter-y: 1rem;	    --bs-gutter-y: 1rem;
  }	  }

  .g-xxl-4,	  .g-xxl-4,
.gx-xxl-4 {	  .gx-xxl-4 {
    --bs-gutter-x: 1.5rem;	    --bs-gutter-x: 1.5rem;
  }	  }

  .g-xxl-4,	  .g-xxl-4,
.gy-xxl-4 {	  .gy-xxl-4 {
    --bs-gutter-y: 1.5rem;	    --bs-gutter-y: 1.5rem;
  }	  }

  .g-xxl-5,	  .g-xxl-5,
.gx-xxl-5 {	  .gx-xxl-5 {
    --bs-gutter-x: 3rem;	    --bs-gutter-x: 3rem;
  }	  }

  .g-xxl-5,	  .g-xxl-5,
.gy-xxl-5 {	  .gy-xxl-5 {
    --bs-gutter-y: 3rem;	    --bs-gutter-y: 3rem;
  }	  }
}	}
.table {	.table {
  --bs-table-color: var(--bs-body-color);
  --bs-table-bg: transparent;	  --bs-table-bg: transparent;
  --bs-table-border-color: var(--bs-border-color);
  --bs-table-accent-bg: transparent;	  --bs-table-accent-bg: transparent;
  --bs-table-striped-color: #212529;	  --bs-table-striped-color: var(--bs-body-color);
  --bs-table-striped-bg: rgba(0, 0, 0, 0.05);	  --bs-table-striped-bg: rgba(0, 0, 0, 0.05);
  --bs-table-active-color: #212529;	  --bs-table-active-color: var(--bs-body-color);
  --bs-table-active-bg: rgba(0, 0, 0, 0.1);	  --bs-table-active-bg: rgba(0, 0, 0, 0.1);
  --bs-table-hover-color: #212529;	  --bs-table-hover-color: var(--bs-body-color);
  --bs-table-hover-bg: rgba(0, 0, 0, 0.075);	  --bs-table-hover-bg: rgba(0, 0, 0, 0.075);
  width: 100%;	  width: 100%;
  margin-bottom: 1rem;	  margin-bottom: 1rem;
  color: #212529;	  color: var(--bs-table-color);
  vertical-align: top;	  vertical-align: top;
  border-color: #dee2e6;	  border-color: var(--bs-table-border-color);
}	}
.table > :not(caption) > * > * {	.table > :not(caption) > * > * {
  padding: 0.5rem 0.5rem;	  padding: 0.5rem 0.5rem;
@@ -1983,8 +1766,9 @@ progress {
.table > thead {	.table > thead {
  vertical-align: bottom;	  vertical-align: bottom;
}	}
.table > :not(:first-child) {	
  border-top: 2px solid currentColor;	.table-group-divider {
  border-top: 2px solid currentcolor;
}	}


.caption-top {	.caption-top {
@@ -2014,6 +1798,11 @@ progress {
  color: var(--bs-table-striped-color);	  color: var(--bs-table-striped-color);
}	}


.table-striped-columns > :not(caption) > tr > :nth-child(even) {
  --bs-table-accent-bg: var(--bs-table-striped-bg);
  color: var(--bs-table-striped-color);
}

.table-active {	.table-active {
  --bs-table-accent-bg: var(--bs-table-active-bg);	  --bs-table-accent-bg: var(--bs-table-active-bg);
  color: var(--bs-table-active-color);	  color: var(--bs-table-active-color);
@@ -2025,99 +1814,115 @@ progress {
}	}


.table-primary {	.table-primary {
  --bs-table-color: #000;
  --bs-table-bg: #cfe2ff;	  --bs-table-bg: #cfe2ff;
  --bs-table-border-color: #bacbe6;
  --bs-table-striped-bg: #c5d7f2;	  --bs-table-striped-bg: #c5d7f2;
  --bs-table-striped-color: #000;	  --bs-table-striped-color: #000;
  --bs-table-active-bg: #bacbe6;	  --bs-table-active-bg: #bacbe6;
  --bs-table-active-color: #000;	  --bs-table-active-color: #000;
  --bs-table-hover-bg: #bfd1ec;	  --bs-table-hover-bg: #bfd1ec;
  --bs-table-hover-color: #000;	  --bs-table-hover-color: #000;
  color: #000;	  color: var(--bs-table-color);
  border-color: #bacbe6;	  border-color: var(--bs-table-border-color);
}	}


.table-secondary {	.table-secondary {
  --bs-table-color: #000;
  --bs-table-bg: #e2e3e5;	  --bs-table-bg: #e2e3e5;
  --bs-table-border-color: #cbccce;
  --bs-table-striped-bg: #d7d8da;	  --bs-table-striped-bg: #d7d8da;
  --bs-table-striped-color: #000;	  --bs-table-striped-color: #000;
  --bs-table-active-bg: #cbccce;	  --bs-table-active-bg: #cbccce;
  --bs-table-active-color: #000;	  --bs-table-active-color: #000;
  --bs-table-hover-bg: #d1d2d4;	  --bs-table-hover-bg: #d1d2d4;
  --bs-table-hover-color: #000;	  --bs-table-hover-color: #000;
  color: #000;	  color: var(--bs-table-color);
  border-color: #cbccce;	  border-color: var(--bs-table-border-color);
}	}


.table-success {	.table-success {
  --bs-table-color: #000;
  --bs-table-bg: #d1e7dd;	  --bs-table-bg: #d1e7dd;
  --bs-table-border-color: #bcd0c7;
  --bs-table-striped-bg: #c7dbd2;	  --bs-table-striped-bg: #c7dbd2;
  --bs-table-striped-color: #000;	  --bs-table-striped-color: #000;
  --bs-table-active-bg: #bcd0c7;	  --bs-table-active-bg: #bcd0c7;
  --bs-table-active-color: #000;	  --bs-table-active-color: #000;
  --bs-table-hover-bg: #c1d6cc;	  --bs-table-hover-bg: #c1d6cc;
  --bs-table-hover-color: #000;	  --bs-table-hover-color: #000;
  color: #000;	  color: var(--bs-table-color);
  border-color: #bcd0c7;	  border-color: var(--bs-table-border-color);
}	}


.table-info {	.table-info {
  --bs-table-color: #000;
  --bs-table-bg: #cff4fc;	  --bs-table-bg: #cff4fc;
  --bs-table-border-color: #badce3;
  --bs-table-striped-bg: #c5e8ef;	  --bs-table-striped-bg: #c5e8ef;
  --bs-table-striped-color: #000;	  --bs-table-striped-color: #000;
  --bs-table-active-bg: #badce3;	  --bs-table-active-bg: #badce3;
  --bs-table-active-color: #000;	  --bs-table-active-color: #000;
  --bs-table-hover-bg: #bfe2e9;	  --bs-table-hover-bg: #bfe2e9;
  --bs-table-hover-color: #000;	  --bs-table-hover-color: #000;
  color: #000;	  color: var(--bs-table-color);
  border-color: #badce3;	  border-color: var(--bs-table-border-color);
}	}


.table-warning {	.table-warning {
  --bs-table-color: #000;
  --bs-table-bg: #fff3cd;	  --bs-table-bg: #fff3cd;
  --bs-table-border-color: #e6dbb9;
  --bs-table-striped-bg: #f2e7c3;	  --bs-table-striped-bg: #f2e7c3;
  --bs-table-striped-color: #000;	  --bs-table-striped-color: #000;
  --bs-table-active-bg: #e6dbb9;	  --bs-table-active-bg: #e6dbb9;
  --bs-table-active-color: #000;	  --bs-table-active-color: #000;
  --bs-table-hover-bg: #ece1be;	  --bs-table-hover-bg: #ece1be;
  --bs-table-hover-color: #000;	  --bs-table-hover-color: #000;
  color: #000;	  color: var(--bs-table-color);
  border-color: #e6dbb9;	  border-color: var(--bs-table-border-color);
}	}


.table-danger {	.table-danger {
  --bs-table-color: #000;
  --bs-table-bg: #f8d7da;	  --bs-table-bg: #f8d7da;
  --bs-table-border-color: #dfc2c4;
  --bs-table-striped-bg: #eccccf;	  --bs-table-striped-bg: #eccccf;
  --bs-table-striped-color: #000;	  --bs-table-striped-color: #000;
  --bs-table-active-bg: #dfc2c4;	  --bs-table-active-bg: #dfc2c4;
  --bs-table-active-color: #000;	  --bs-table-active-color: #000;
  --bs-table-hover-bg: #e5c7ca;	  --bs-table-hover-bg: #e5c7ca;
  --bs-table-hover-color: #000;	  --bs-table-hover-color: #000;
  color: #000;	  color: var(--bs-table-color);
  border-color: #dfc2c4;	  border-color: var(--bs-table-border-color);
}	}


.table-light {	.table-light {
  --bs-table-color: #000;
  --bs-table-bg: #f8f9fa;	  --bs-table-bg: #f8f9fa;
  --bs-table-border-color: #dfe0e1;
  --bs-table-striped-bg: #ecedee;	  --bs-table-striped-bg: #ecedee;
  --bs-table-striped-color: #000;	  --bs-table-striped-color: #000;
  --bs-table-active-bg: #dfe0e1;	  --bs-table-active-bg: #dfe0e1;
  --bs-table-active-color: #000;	  --bs-table-active-color: #000;
  --bs-table-hover-bg: #e5e6e7;	  --bs-table-hover-bg: #e5e6e7;
  --bs-table-hover-color: #000;	  --bs-table-hover-color: #000;
  color: #000;	  color: var(--bs-table-color);
  border-color: #dfe0e1;	  border-color: var(--bs-table-border-color);
}	}


.table-dark {	.table-dark {
  --bs-table-color: #fff;
  --bs-table-bg: #212529;	  --bs-table-bg: #212529;
  --bs-table-border-color: #373b3e;
  --bs-table-striped-bg: #2c3034;	  --bs-table-striped-bg: #2c3034;
  --bs-table-striped-color: #fff;	  --bs-table-striped-color: #fff;
  --bs-table-active-bg: #373b3e;	  --bs-table-active-bg: #373b3e;
  --bs-table-active-color: #fff;	  --bs-table-active-color: #fff;
  --bs-table-hover-bg: #323539;	  --bs-table-hover-bg: #323539;
  --bs-table-hover-color: #fff;	  --bs-table-hover-color: #fff;
  color: #fff;	  color: var(--bs-table-color);
  border-color: #373b3e;	  border-color: var(--bs-table-border-color);
}	}


.table-responsive {	.table-responsive {
@@ -2199,7 +2004,7 @@ progress {
  -webkit-appearance: none;	  -webkit-appearance: none;
     -moz-appearance: none;	     -moz-appearance: none;
          appearance: none;	          appearance: none;
  border-radius: 0.25rem;	  border-radius: 0.375rem;
  transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;	  transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
}	}
@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
@@ -2227,34 +2032,14 @@ progress {
  color: #6c757d;	  color: #6c757d;
  opacity: 1;	  opacity: 1;
}	}
.form-control:-ms-input-placeholder {	
  color: #6c757d;	
  opacity: 1;	
}	
.form-control::placeholder {	.form-control::placeholder {
  color: #6c757d;	  color: #6c757d;
  opacity: 1;	  opacity: 1;
}	}
.form-control:disabled, .form-control[readonly] {	.form-control:disabled {
  background-color: #e9ecef;	  background-color: #e9ecef;
  opacity: 1;	  opacity: 1;
}	}
.form-control::-webkit-file-upload-button {	
  padding: 0.375rem 0.75rem;	
  margin: -0.375rem -0.75rem;	
  -webkit-margin-end: 0.75rem;	
          margin-inline-end: 0.75rem;	
  color: #212529;	
  background-color: #e9ecef;	
  pointer-events: none;	
  border-color: inherit;	
  border-style: solid;	
  border-width: 0;	
  border-inline-end-width: 1px;	
  border-radius: 0;	
  -webkit-transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;	
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;	
}	
.form-control::file-selector-button {	.form-control::file-selector-button {
  padding: 0.375rem 0.75rem;	  padding: 0.375rem 0.75rem;
  margin: -0.375rem -0.75rem;	  margin: -0.375rem -0.75rem;
@@ -2271,45 +2056,13 @@ progress {
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;	  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
}	}
@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
  .form-control::-webkit-file-upload-button {	
    -webkit-transition: none;	
    transition: none;	
  }	
  .form-control::file-selector-button {	  .form-control::file-selector-button {
    transition: none;	    transition: none;
  }	  }
}	}
.form-control:hover:not(:disabled):not([readonly])::-webkit-file-upload-button {	
  background-color: #dde0e3;	
}	
.form-control:hover:not(:disabled):not([readonly])::file-selector-button {	.form-control:hover:not(:disabled):not([readonly])::file-selector-button {
  background-color: #dde0e3;	  background-color: #dde0e3;
}	}
.form-control::-webkit-file-upload-button {	
  padding: 0.375rem 0.75rem;	
  margin: -0.375rem -0.75rem;	
  -webkit-margin-end: 0.75rem;	
          margin-inline-end: 0.75rem;	
  color: #212529;	
  background-color: #e9ecef;	
  pointer-events: none;	
  border-color: inherit;	
  border-style: solid;	
  border-width: 0;	
  border-inline-end-width: 1px;	
  border-radius: 0;	
  -webkit-transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;	
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;	
}	
@media (prefers-reduced-motion: reduce) {	
  .form-control::-webkit-file-upload-button {	
    -webkit-transition: none;	
    transition: none;	
  }	
}	
.form-control:hover:not(:disabled):not([readonly])::-webkit-file-upload-button {	
  background-color: #dde0e3;	
}	


.form-control-plaintext {	.form-control-plaintext {
  display: block;	  display: block;
@@ -2322,6 +2075,9 @@ progress {
  border: solid transparent;	  border: solid transparent;
  border-width: 1px 0;	  border-width: 1px 0;
}	}
.form-control-plaintext:focus {
  outline: 0;
}
.form-control-plaintext.form-control-sm, .form-control-plaintext.form-control-lg {	.form-control-plaintext.form-control-sm, .form-control-plaintext.form-control-lg {
  padding-right: 0;	  padding-right: 0;
  padding-left: 0;	  padding-left: 0;
@@ -2331,51 +2087,27 @@ progress {
  min-height: calc(1.5em + 0.5rem + 2px);	  min-height: calc(1.5em + 0.5rem + 2px);
  padding: 0.25rem 0.5rem;	  padding: 0.25rem 0.5rem;
  font-size: 0.875rem;	  font-size: 0.875rem;
  border-radius: 0.2rem;	  border-radius: 0.25rem;
}	
.form-control-sm::-webkit-file-upload-button {	
  padding: 0.25rem 0.5rem;	
  margin: -0.25rem -0.5rem;	
  -webkit-margin-end: 0.5rem;	
          margin-inline-end: 0.5rem;	
}	}
.form-control-sm::file-selector-button {	.form-control-sm::file-selector-button {
  padding: 0.25rem 0.5rem;	  padding: 0.25rem 0.5rem;
  margin: -0.25rem -0.5rem;	  margin: -0.25rem -0.5rem;
  -webkit-margin-end: 0.5rem;	  -webkit-margin-end: 0.5rem;
          margin-inline-end: 0.5rem;	          margin-inline-end: 0.5rem;
}	}
.form-control-sm::-webkit-file-upload-button {	
  padding: 0.25rem 0.5rem;	
  margin: -0.25rem -0.5rem;	
  -webkit-margin-end: 0.5rem;	
          margin-inline-end: 0.5rem;	
}	


.form-control-lg {	.form-control-lg {
  min-height: calc(1.5em + 1rem + 2px);	  min-height: calc(1.5em + 1rem + 2px);
  padding: 0.5rem 1rem;	  padding: 0.5rem 1rem;
  font-size: 1.25rem;	  font-size: 1.25rem;
  border-radius: 0.3rem;	  border-radius: 0.5rem;
}	
.form-control-lg::-webkit-file-upload-button {	
  padding: 0.5rem 1rem;	
  margin: -0.5rem -1rem;	
  -webkit-margin-end: 1rem;	
          margin-inline-end: 1rem;	
}	}
.form-control-lg::file-selector-button {	.form-control-lg::file-selector-button {
  padding: 0.5rem 1rem;	  padding: 0.5rem 1rem;
  margin: -0.5rem -1rem;	  margin: -0.5rem -1rem;
  -webkit-margin-end: 1rem;	  -webkit-margin-end: 1rem;
          margin-inline-end: 1rem;	          margin-inline-end: 1rem;
}	}
.form-control-lg::-webkit-file-upload-button {	
  padding: 0.5rem 1rem;	
  margin: -0.5rem -1rem;	
  -webkit-margin-end: 1rem;	
          margin-inline-end: 1rem;	
}	


textarea.form-control {	textarea.form-control {
  min-height: calc(1.5em + 0.75rem + 2px);	  min-height: calc(1.5em + 0.75rem + 2px);
@@ -2389,19 +2121,24 @@ textarea.form-control-lg {


.form-control-color {	.form-control-color {
  width: 3rem;	  width: 3rem;
  height: auto;	  height: calc(1.5em + 0.75rem + 2px);
  padding: 0.375rem;	  padding: 0.375rem;
}	}
.form-control-color:not(:disabled):not([readonly]) {	.form-control-color:not(:disabled):not([readonly]) {
  cursor: pointer;	  cursor: pointer;
}	}
.form-control-color::-moz-color-swatch {	.form-control-color::-moz-color-swatch {
  height: 1.5em;	  border: 0 !important;
  border-radius: 0.25rem;	  border-radius: 0.375rem;
}	}
.form-control-color::-webkit-color-swatch {	.form-control-color::-webkit-color-swatch {
  height: 1.5em;	  border-radius: 0.375rem;
  border-radius: 0.25rem;	}
.form-control-color.form-control-sm {
  height: calc(1.5em + 0.5rem + 2px);
}
.form-control-color.form-control-lg {
  height: calc(1.5em + 1rem + 2px);
}	}


.form-select {	.form-select {
@@ -2414,12 +2151,12 @@ textarea.form-control-lg {
  line-height: 1.5;	  line-height: 1.5;
  color: #212529;	  color: #212529;
  background-color: #fff;	  background-color: #fff;
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill='none' stroke='%23343a40' stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='M2 5l6 6 6-6'/%3e%3c/svg%3e");	  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill='none' stroke='%23343a40' stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='m2 5 6 6 6-6'/%3e%3c/svg%3e");
  background-repeat: no-repeat;	  background-repeat: no-repeat;
  background-position: right 0.75rem center;	  background-position: right 0.75rem center;
  background-size: 16px 12px;	  background-size: 16px 12px;
  border: 1px solid #ced4da;	  border: 1px solid #ced4da;
  border-radius: 0.25rem;	  border-radius: 0.375rem;
  transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;	  transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
  -webkit-appearance: none;	  -webkit-appearance: none;
     -moz-appearance: none;	     -moz-appearance: none;
@@ -2452,15 +2189,15 @@ textarea.form-control-lg {
  padding-bottom: 0.25rem;	  padding-bottom: 0.25rem;
  padding-left: 0.5rem;	  padding-left: 0.5rem;
  font-size: 0.875rem;	  font-size: 0.875rem;
  border-radius: 0.2rem;	  border-radius: 0.25rem;
}	}


.form-select-lg {	.form-select-lg {
  padding-top: 0.5rem;	  padding-top: 0.5rem;
  padding-bottom: 0.5rem;	  padding-bottom: 0.5rem;
  padding-left: 1rem;	  padding-left: 1rem;
  font-size: 1.25rem;	  font-size: 1.25rem;
  border-radius: 0.3rem;	  border-radius: 0.5rem;
}	}


.form-check {	.form-check {
@@ -2474,6 +2211,17 @@ textarea.form-control-lg {
  margin-left: -1.5em;	  margin-left: -1.5em;
}	}


.form-check-reverse {
  padding-right: 1.5em;
  padding-left: 0;
  text-align: right;
}
.form-check-reverse .form-check-input {
  float: right;
  margin-right: -1.5em;
  margin-left: 0;
}

.form-check-input {	.form-check-input {
  width: 1em;	  width: 1em;
  height: 1em;	  height: 1em;
@@ -2488,7 +2236,7 @@ textarea.form-control-lg {
     -moz-appearance: none;	     -moz-appearance: none;
          appearance: none;	          appearance: none;
  -webkit-print-color-adjust: exact;	  -webkit-print-color-adjust: exact;
          color-adjust: exact;	          print-color-adjust: exact;
}	}
.form-check-input[type=checkbox] {	.form-check-input[type=checkbox] {
  border-radius: 0.25em;	  border-radius: 0.25em;
@@ -2509,7 +2257,7 @@ textarea.form-control-lg {
  border-color: #0d6efd;	  border-color: #0d6efd;
}	}
.form-check-input:checked[type=checkbox] {	.form-check-input:checked[type=checkbox] {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 20 20'%3e%3cpath fill='none' stroke='%23fff' stroke-linecap='round' stroke-linejoin='round' stroke-width='3' d='M6 10l3 3l6-6'/%3e%3c/svg%3e");	  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 20 20'%3e%3cpath fill='none' stroke='%23fff' stroke-linecap='round' stroke-linejoin='round' stroke-width='3' d='m6 10 3 3 6-6'/%3e%3c/svg%3e");
}	}
.form-check-input:checked[type=radio] {	.form-check-input:checked[type=radio] {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='-4 -4 8 8'%3e%3ccircle r='2' fill='%23fff'/%3e%3c/svg%3e");	  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='-4 -4 8 8'%3e%3ccircle r='2' fill='%23fff'/%3e%3c/svg%3e");
@@ -2525,6 +2273,7 @@ textarea.form-control-lg {
  opacity: 0.5;	  opacity: 0.5;
}	}
.form-check-input[disabled] ~ .form-check-label, .form-check-input:disabled ~ .form-check-label {	.form-check-input[disabled] ~ .form-check-label, .form-check-input:disabled ~ .form-check-label {
  cursor: default;
  opacity: 0.5;	  opacity: 0.5;
}	}


@@ -2551,6 +2300,14 @@ textarea.form-control-lg {
  background-position: right center;	  background-position: right center;
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='-4 -4 8 8'%3e%3ccircle r='3' fill='%23fff'/%3e%3c/svg%3e");	  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='-4 -4 8 8'%3e%3ccircle r='3' fill='%23fff'/%3e%3c/svg%3e");
}	}
.form-switch.form-check-reverse {
  padding-right: 2.5em;
  padding-left: 0;
}
.form-switch.form-check-reverse .form-check-input {
  margin-right: -2.5em;
  margin-left: 0;
}


.form-check-inline {	.form-check-inline {
  display: inline-block;	  display: inline-block;
@@ -2662,6 +2419,7 @@ textarea.form-control-lg {
  position: relative;	  position: relative;
}	}
.form-floating > .form-control,	.form-floating > .form-control,
.form-floating > .form-control-plaintext,
.form-floating > .form-select {	.form-floating > .form-select {
  height: calc(3.5rem + 2px);	  height: calc(3.5rem + 2px);
  line-height: 1.25;	  line-height: 1.25;
@@ -2670,8 +2428,13 @@ textarea.form-control-lg {
  position: absolute;	  position: absolute;
  top: 0;	  top: 0;
  left: 0;	  left: 0;
  width: 100%;
  height: 100%;	  height: 100%;
  padding: 1rem 0.75rem;	  padding: 1rem 0.75rem;
  overflow: hidden;
  text-align: start;
  text-overflow: ellipsis;
  white-space: nowrap;
  pointer-events: none;	  pointer-events: none;
  border: 1px solid transparent;	  border: 1px solid transparent;
  transform-origin: 0 0;	  transform-origin: 0 0;
@@ -2682,31 +2445,29 @@ textarea.form-control-lg {
    transition: none;	    transition: none;
  }	  }
}	}
.form-floating > .form-control {	.form-floating > .form-control,
.form-floating > .form-control-plaintext {
  padding: 1rem 0.75rem;	  padding: 1rem 0.75rem;
}	}
.form-floating > .form-control::-moz-placeholder {	.form-floating > .form-control::-moz-placeholder, .form-floating > .form-control-plaintext::-moz-placeholder {
  color: transparent;	
}	
.form-floating > .form-control:-ms-input-placeholder {	
  color: transparent;	  color: transparent;
}	}
.form-floating > .form-control::placeholder {	.form-floating > .form-control::placeholder,
.form-floating > .form-control-plaintext::placeholder {
  color: transparent;	  color: transparent;
}	}
.form-floating > .form-control:not(:-moz-placeholder-shown) {	.form-floating > .form-control:not(:-moz-placeholder-shown), .form-floating > .form-control-plaintext:not(:-moz-placeholder-shown) {
  padding-top: 1.625rem;	
  padding-bottom: 0.625rem;	
}	
.form-floating > .form-control:not(:-ms-input-placeholder) {	
  padding-top: 1.625rem;	  padding-top: 1.625rem;
  padding-bottom: 0.625rem;	  padding-bottom: 0.625rem;
}	}
.form-floating > .form-control:focus, .form-floating > .form-control:not(:placeholder-shown) {	.form-floating > .form-control:focus, .form-floating > .form-control:not(:placeholder-shown),
.form-floating > .form-control-plaintext:focus,
.form-floating > .form-control-plaintext:not(:placeholder-shown) {
  padding-top: 1.625rem;	  padding-top: 1.625rem;
  padding-bottom: 0.625rem;	  padding-bottom: 0.625rem;
}	}
.form-floating > .form-control:-webkit-autofill {	.form-floating > .form-control:-webkit-autofill,
.form-floating > .form-control-plaintext:-webkit-autofill {
  padding-top: 1.625rem;	  padding-top: 1.625rem;
  padding-bottom: 0.625rem;	  padding-bottom: 0.625rem;
}	}
@@ -2718,12 +2479,9 @@ textarea.form-control-lg {
  opacity: 0.65;	  opacity: 0.65;
  transform: scale(0.85) translateY(-0.5rem) translateX(0.15rem);	  transform: scale(0.85) translateY(-0.5rem) translateX(0.15rem);
}	}
.form-floating > .form-control:not(:-ms-input-placeholder) ~ label {	
  opacity: 0.65;	
  transform: scale(0.85) translateY(-0.5rem) translateX(0.15rem);	
}	
.form-floating > .form-control:focus ~ label,	.form-floating > .form-control:focus ~ label,
.form-floating > .form-control:not(:placeholder-shown) ~ label,	.form-floating > .form-control:not(:placeholder-shown) ~ label,
.form-floating > .form-control-plaintext ~ label,
.form-floating > .form-select ~ label {	.form-floating > .form-select ~ label {
  opacity: 0.65;	  opacity: 0.65;
  transform: scale(0.85) translateY(-0.5rem) translateX(0.15rem);	  transform: scale(0.85) translateY(-0.5rem) translateX(0.15rem);
@@ -2732,6 +2490,9 @@ textarea.form-control-lg {
  opacity: 0.65;	  opacity: 0.65;
  transform: scale(0.85) translateY(-0.5rem) translateX(0.15rem);	  transform: scale(0.85) translateY(-0.5rem) translateX(0.15rem);
}	}
.form-floating > .form-control-plaintext ~ label {
  border-width: 1px 0;
}


.input-group {	.input-group {
  position: relative;	  position: relative;
@@ -2741,22 +2502,24 @@ textarea.form-control-lg {
  width: 100%;	  width: 100%;
}	}
.input-group > .form-control,	.input-group > .form-control,
.input-group > .form-select {	.input-group > .form-select,
.input-group > .form-floating {
  position: relative;	  position: relative;
  flex: 1 1 auto;	  flex: 1 1 auto;
  width: 1%;	  width: 1%;
  min-width: 0;	  min-width: 0;
}	}
.input-group > .form-control:focus,	.input-group > .form-control:focus,
.input-group > .form-select:focus {	.input-group > .form-select:focus,
  z-index: 3;	.input-group > .form-floating:focus-within {
  z-index: 5;
}	}
.input-group .btn {	.input-group .btn {
  position: relative;	  position: relative;
  z-index: 2;	  z-index: 2;
}	}
.input-group .btn:focus {	.input-group .btn:focus {
  z-index: 3;	  z-index: 5;
}	}


.input-group-text {	.input-group-text {
@@ -2771,7 +2534,7 @@ textarea.form-control-lg {
  white-space: nowrap;	  white-space: nowrap;
  background-color: #e9ecef;	  background-color: #e9ecef;
  border: 1px solid #ced4da;	  border: 1px solid #ced4da;
  border-radius: 0.25rem;	  border-radius: 0.375rem;
}	}


.input-group-lg > .form-control,	.input-group-lg > .form-control,
@@ -2780,7 +2543,7 @@ textarea.form-control-lg {
.input-group-lg > .btn {	.input-group-lg > .btn {
  padding: 0.5rem 1rem;	  padding: 0.5rem 1rem;
  font-size: 1.25rem;	  font-size: 1.25rem;
  border-radius: 0.3rem;	  border-radius: 0.5rem;
}	}


.input-group-sm > .form-control,	.input-group-sm > .form-control,
@@ -2789,21 +2552,25 @@ textarea.form-control-lg {
.input-group-sm > .btn {	.input-group-sm > .btn {
  padding: 0.25rem 0.5rem;	  padding: 0.25rem 0.5rem;
  font-size: 0.875rem;	  font-size: 0.875rem;
  border-radius: 0.2rem;	  border-radius: 0.25rem;
}	}


.input-group-lg > .form-select,	.input-group-lg > .form-select,
.input-group-sm > .form-select {	.input-group-sm > .form-select {
  padding-right: 3rem;	  padding-right: 3rem;
}	}


.input-group:not(.has-validation) > :not(:last-child):not(.dropdown-toggle):not(.dropdown-menu),	.input-group:not(.has-validation) > :not(:last-child):not(.dropdown-toggle):not(.dropdown-menu):not(.form-floating),
.input-group:not(.has-validation) > .dropdown-toggle:nth-last-child(n+3) {	.input-group:not(.has-validation) > .dropdown-toggle:nth-last-child(n+3),
.input-group:not(.has-validation) > .form-floating:not(:last-child) > .form-control,
.input-group:not(.has-validation) > .form-floating:not(:last-child) > .form-select {
  border-top-right-radius: 0;	  border-top-right-radius: 0;
  border-bottom-right-radius: 0;	  border-bottom-right-radius: 0;
}	}
.input-group.has-validation > :nth-last-child(n+3):not(.dropdown-toggle):not(.dropdown-menu),	.input-group.has-validation > :nth-last-child(n+3):not(.dropdown-toggle):not(.dropdown-menu):not(.form-floating),
.input-group.has-validation > .dropdown-toggle:nth-last-child(n+4) {	.input-group.has-validation > .dropdown-toggle:nth-last-child(n+4),
.input-group.has-validation > .form-floating:nth-last-child(n+3) > .form-control,
.input-group.has-validation > .form-floating:nth-last-child(n+3) > .form-select {
  border-top-right-radius: 0;	  border-top-right-radius: 0;
  border-bottom-right-radius: 0;	  border-bottom-right-radius: 0;
}	}
@@ -2812,6 +2579,11 @@ textarea.form-control-lg {
  border-top-left-radius: 0;	  border-top-left-radius: 0;
  border-bottom-left-radius: 0;	  border-bottom-left-radius: 0;
}	}
.input-group > .form-floating:not(:first-child) > .form-control,
.input-group > .form-floating:not(:first-child) > .form-select {
  border-top-left-radius: 0;
  border-bottom-left-radius: 0;
}


.valid-feedback {	.valid-feedback {
  display: none;	  display: none;
@@ -2832,7 +2604,7 @@ textarea.form-control-lg {
  font-size: 0.875rem;	  font-size: 0.875rem;
  color: #fff;	  color: #fff;
  background-color: rgba(25, 135, 84, 0.9);	  background-color: rgba(25, 135, 84, 0.9);
  border-radius: 0.25rem;	  border-radius: 0.375rem;
}	}


.was-validated :valid ~ .valid-feedback,	.was-validated :valid ~ .valid-feedback,
@@ -2845,7 +2617,7 @@ textarea.form-control-lg {
.was-validated .form-control:valid, .form-control.is-valid {	.was-validated .form-control:valid, .form-control.is-valid {
  border-color: #198754;	  border-color: #198754;
  padding-right: calc(1.5em + 0.75rem);	  padding-right: calc(1.5em + 0.75rem);
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 8 8'%3e%3cpath fill='%23198754' d='M2.3 6.73L.6 4.53c-.4-1.04.46-1.4 1.1-.8l1.1 1.4 3.4-3.8c.6-.63 1.6-.27 1.2.7l-4 4.6c-.43.5-.8.4-1.1.1z'/%3e%3c/svg%3e");	  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 8 8'%3e%3cpath fill='%23198754' d='M2.3 6.73.6 4.53c-.4-1.04.46-1.4 1.1-.8l1.1 1.4 3.4-3.8c.6-.63 1.6-.27 1.2.7l-4 4.6c-.43.5-.8.4-1.1.1z'/%3e%3c/svg%3e");
  background-repeat: no-repeat;	  background-repeat: no-repeat;
  background-position: right calc(0.375em + 0.1875rem) center;	  background-position: right calc(0.375em + 0.1875rem) center;
  background-size: calc(0.75em + 0.375rem) calc(0.75em + 0.375rem);	  background-size: calc(0.75em + 0.375rem) calc(0.75em + 0.375rem);
@@ -2865,7 +2637,7 @@ textarea.form-control-lg {
}	}
.was-validated .form-select:valid:not([multiple]):not([size]), .was-validated .form-select:valid:not([multiple])[size="1"], .form-select.is-valid:not([multiple]):not([size]), .form-select.is-valid:not([multiple])[size="1"] {	.was-validated .form-select:valid:not([multiple]):not([size]), .was-validated .form-select:valid:not([multiple])[size="1"], .form-select.is-valid:not([multiple]):not([size]), .form-select.is-valid:not([multiple])[size="1"] {
  padding-right: 4.125rem;	  padding-right: 4.125rem;
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill='none' stroke='%23343a40' stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='M2 5l6 6 6-6'/%3e%3c/svg%3e"), url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 8 8'%3e%3cpath fill='%23198754' d='M2.3 6.73L.6 4.53c-.4-1.04.46-1.4 1.1-.8l1.1 1.4 3.4-3.8c.6-.63 1.6-.27 1.2.7l-4 4.6c-.43.5-.8.4-1.1.1z'/%3e%3c/svg%3e");	  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill='none' stroke='%23343a40' stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='m2 5 6 6 6-6'/%3e%3c/svg%3e"), url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 8 8'%3e%3cpath fill='%23198754' d='M2.3 6.73.6 4.53c-.4-1.04.46-1.4 1.1-.8l1.1 1.4 3.4-3.8c.6-.63 1.6-.27 1.2.7l-4 4.6c-.43.5-.8.4-1.1.1z'/%3e%3c/svg%3e");
  background-position: right 0.75rem center, center right 2.25rem;	  background-position: right 0.75rem center, center right 2.25rem;
  background-size: 16px 12px, calc(0.75em + 0.375rem) calc(0.75em + 0.375rem);	  background-size: 16px 12px, calc(0.75em + 0.375rem) calc(0.75em + 0.375rem);
}	}
@@ -2874,6 +2646,10 @@ textarea.form-control-lg {
  box-shadow: 0 0 0 0.25rem rgba(25, 135, 84, 0.25);	  box-shadow: 0 0 0 0.25rem rgba(25, 135, 84, 0.25);
}	}


.was-validated .form-control-color:valid, .form-control-color.is-valid {
  width: calc(3rem + calc(1.5em + 0.75rem));
}

.was-validated .form-check-input:valid, .form-check-input.is-valid {	.was-validated .form-check-input:valid, .form-check-input.is-valid {
  border-color: #198754;	  border-color: #198754;
}	}
@@ -2891,14 +2667,11 @@ textarea.form-control-lg {
  margin-left: 0.5em;	  margin-left: 0.5em;
}	}


.was-validated .input-group .form-control:valid, .input-group .form-control.is-valid,	.was-validated .input-group > .form-control:not(:focus):valid, .input-group > .form-control:not(:focus).is-valid,
.was-validated .input-group .form-select:valid,	.was-validated .input-group > .form-select:not(:focus):valid,
.input-group .form-select.is-valid {	.input-group > .form-select:not(:focus).is-valid,
  z-index: 1;	.was-validated .input-group > .form-floating:not(:focus-within):valid,
}	.input-group > .form-floating:not(:focus-within).is-valid {
.was-validated .input-group .form-control:valid:focus, .input-group .form-control.is-valid:focus,	
.was-validated .input-group .form-select:valid:focus,	
.input-group .form-select.is-valid:focus {	
  z-index: 3;	  z-index: 3;
}	}


@@ -2921,7 +2694,7 @@ textarea.form-control-lg {
  font-size: 0.875rem;	  font-size: 0.875rem;
  color: #fff;	  color: #fff;
  background-color: rgba(220, 53, 69, 0.9);	  background-color: rgba(220, 53, 69, 0.9);
  border-radius: 0.25rem;	  border-radius: 0.375rem;
}	}


.was-validated :invalid ~ .invalid-feedback,	.was-validated :invalid ~ .invalid-feedback,
@@ -2954,7 +2727,7 @@ textarea.form-control-lg {
}	}
.was-validated .form-select:invalid:not([multiple]):not([size]), .was-validated .form-select:invalid:not([multiple])[size="1"], .form-select.is-invalid:not([multiple]):not([size]), .form-select.is-invalid:not([multiple])[size="1"] {	.was-validated .form-select:invalid:not([multiple]):not([size]), .was-validated .form-select:invalid:not([multiple])[size="1"], .form-select.is-invalid:not([multiple]):not([size]), .form-select.is-invalid:not([multiple])[size="1"] {
  padding-right: 4.125rem;	  padding-right: 4.125rem;
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill='none' stroke='%23343a40' stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='M2 5l6 6 6-6'/%3e%3c/svg%3e"), url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 12 12' width='12' height='12' fill='none' stroke='%23dc3545'%3e%3ccircle cx='6' cy='6' r='4.5'/%3e%3cpath stroke-linejoin='round' d='M5.8 3.6h.4L6 6.5z'/%3e%3ccircle cx='6' cy='8.2' r='.6' fill='%23dc3545' stroke='none'/%3e%3c/svg%3e");	  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill='none' stroke='%23343a40' stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='m2 5 6 6 6-6'/%3e%3c/svg%3e"), url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 12 12' width='12' height='12' fill='none' stroke='%23dc3545'%3e%3ccircle cx='6' cy='6' r='4.5'/%3e%3cpath stroke-linejoin='round' d='M5.8 3.6h.4L6 6.5z'/%3e%3ccircle cx='6' cy='8.2' r='.6' fill='%23dc3545' stroke='none'/%3e%3c/svg%3e");
  background-position: right 0.75rem center, center right 2.25rem;	  background-position: right 0.75rem center, center right 2.25rem;
  background-size: 16px 12px, calc(0.75em + 0.375rem) calc(0.75em + 0.375rem);	  background-size: 16px 12px, calc(0.75em + 0.375rem) calc(0.75em + 0.375rem);
}	}
@@ -2963,6 +2736,10 @@ textarea.form-control-lg {
  box-shadow: 0 0 0 0.25rem rgba(220, 53, 69, 0.25);	  box-shadow: 0 0 0 0.25rem rgba(220, 53, 69, 0.25);
}	}


.was-validated .form-control-color:invalid, .form-control-color.is-invalid {
  width: calc(3rem + calc(1.5em + 0.75rem));
}

.was-validated .form-check-input:invalid, .form-check-input.is-invalid {	.was-validated .form-check-input:invalid, .form-check-input.is-invalid {
  border-color: #dc3545;	  border-color: #dc3545;
}	}
@@ -2980,35 +2757,47 @@ textarea.form-control-lg {
  margin-left: 0.5em;	  margin-left: 0.5em;
}	}


.was-validated .input-group .form-control:invalid, .input-group .form-control.is-invalid,	.was-validated .input-group > .form-control:not(:focus):invalid, .input-group > .form-control:not(:focus).is-invalid,
.was-validated .input-group .form-select:invalid,	.was-validated .input-group > .form-select:not(:focus):invalid,
.input-group .form-select.is-invalid {	.input-group > .form-select:not(:focus).is-invalid,
  z-index: 2;	.was-validated .input-group > .form-floating:not(:focus-within):invalid,
}	.input-group > .form-floating:not(:focus-within).is-invalid {
.was-validated .input-group .form-control:invalid:focus, .input-group .form-control.is-invalid:focus,	  z-index: 4;
.was-validated .input-group .form-select:invalid:focus,	
.input-group .form-select.is-invalid:focus {	
  z-index: 3;	
}	}


.btn {	.btn {
  --bs-btn-padding-x: 0.75rem;
  --bs-btn-padding-y: 0.375rem;
  --bs-btn-font-family: ;
  --bs-btn-font-size: 1rem;
  --bs-btn-font-weight: 400;
  --bs-btn-line-height: 1.5;
  --bs-btn-color: #212529;
  --bs-btn-bg: transparent;
  --bs-btn-border-width: 1px;
  --bs-btn-border-color: transparent;
  --bs-btn-border-radius: 0.375rem;
  --bs-btn-hover-border-color: transparent;
  --bs-btn-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.15), 0 1px 1px rgba(0, 0, 0, 0.075);
  --bs-btn-disabled-opacity: 0.65;
  --bs-btn-focus-box-shadow: 0 0 0 0.25rem rgba(var(--bs-btn-focus-shadow-rgb), .5);
  display: inline-block;	  display: inline-block;
  font-weight: 400;	  padding: var(--bs-btn-padding-y) var(--bs-btn-padding-x);
  line-height: 1.5;	  font-family: var(--bs-btn-font-family);
  color: #212529;	  font-size: var(--bs-btn-font-size);
  font-weight: var(--bs-btn-font-weight);
  line-height: var(--bs-btn-line-height);
  color: var(--bs-btn-color);
  text-align: center;	  text-align: center;
  text-decoration: none;	  text-decoration: none;
  vertical-align: middle;	  vertical-align: middle;
  cursor: pointer;	  cursor: pointer;
  -webkit-user-select: none;	  -webkit-user-select: none;
     -moz-user-select: none;	     -moz-user-select: none;
      -ms-user-select: none;	
          user-select: none;	          user-select: none;
  background-color: transparent;	  border: var(--bs-btn-border-width) solid var(--bs-btn-border-color);
  border: 1px solid transparent;	  border-radius: var(--bs-btn-border-radius);
  padding: 0.375rem 0.75rem;	  background-color: var(--bs-btn-bg);
  font-size: 1rem;	
  border-radius: 0.25rem;	
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;	  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
}	}
@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
@@ -3017,501 +2806,371 @@ textarea.form-control-lg {
  }	  }
}	}
.btn:hover {	.btn:hover {
  color: #212529;	  color: var(--bs-btn-hover-color);
  background-color: var(--bs-btn-hover-bg);
  border-color: var(--bs-btn-hover-border-color);
}
.btn-check + .btn:hover {
  color: var(--bs-btn-color);
  background-color: var(--bs-btn-bg);
  border-color: var(--bs-btn-border-color);
}
.btn:focus-visible {
  color: var(--bs-btn-hover-color);
  background-color: var(--bs-btn-hover-bg);
  border-color: var(--bs-btn-hover-border-color);
  outline: 0;
  box-shadow: var(--bs-btn-focus-box-shadow);
}	}
.btn-check:focus + .btn, .btn:focus {	.btn-check:focus-visible + .btn {
  border-color: var(--bs-btn-hover-border-color);
  outline: 0;	  outline: 0;
  box-shadow: 0 0 0 0.25rem rgba(13, 110, 253, 0.25);	  box-shadow: var(--bs-btn-focus-box-shadow);
}
.btn-check:checked + .btn, :not(.btn-check) + .btn:active, .btn:first-child:active, .btn.active, .btn.show {
  color: var(--bs-btn-active-color);
  background-color: var(--bs-btn-active-bg);
  border-color: var(--bs-btn-active-border-color);
}
.btn-check:checked + .btn:focus-visible, :not(.btn-check) + .btn:active:focus-visible, .btn:first-child:active:focus-visible, .btn.active:focus-visible, .btn.show:focus-visible {
  box-shadow: var(--bs-btn-focus-box-shadow);
}	}
.btn:disabled, .btn.disabled, fieldset:disabled .btn {	.btn:disabled, .btn.disabled, fieldset:disabled .btn {
  color: var(--bs-btn-disabled-color);
  pointer-events: none;	  pointer-events: none;
  opacity: 0.65;	  background-color: var(--bs-btn-disabled-bg);
  border-color: var(--bs-btn-disabled-border-color);
  opacity: var(--bs-btn-disabled-opacity);
}	}


.btn-primary {	.btn-primary {
  color: #fff;	  --bs-btn-color: #fff;
  background-color: #0d6efd;	  --bs-btn-bg: #0d6efd;
  border-color: #0d6efd;	  --bs-btn-border-color: #0d6efd;
}	  --bs-btn-hover-color: #fff;
.btn-primary:hover {	  --bs-btn-hover-bg: #0b5ed7;
  color: #fff;	  --bs-btn-hover-border-color: #0a58ca;
  background-color: #0b5ed7;	  --bs-btn-focus-shadow-rgb: 49, 132, 253;
  border-color: #0a58ca;	  --bs-btn-active-color: #fff;
}	  --bs-btn-active-bg: #0a58ca;
.btn-check:focus + .btn-primary, .btn-primary:focus {	  --bs-btn-active-border-color: #0a53be;
  color: #fff;	  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  background-color: #0b5ed7;	  --bs-btn-disabled-color: #fff;
  border-color: #0a58ca;	  --bs-btn-disabled-bg: #0d6efd;
  box-shadow: 0 0 0 0.25rem rgba(49, 132, 253, 0.5);	  --bs-btn-disabled-border-color: #0d6efd;
}	
.btn-check:checked + .btn-primary, .btn-check:active + .btn-primary, .btn-primary:active, .btn-primary.active, .show > .btn-primary.dropdown-toggle {	
  color: #fff;	
  background-color: #0a58ca;	
  border-color: #0a53be;	
}	
.btn-check:checked + .btn-primary:focus, .btn-check:active + .btn-primary:focus, .btn-primary:active:focus, .btn-primary.active:focus, .show > .btn-primary.dropdown-toggle:focus {	
  box-shadow: 0 0 0 0.25rem rgba(49, 132, 253, 0.5);	
}	
.btn-primary:disabled, .btn-primary.disabled {	
  color: #fff;	
  background-color: #0d6efd;	
  border-color: #0d6efd;	
}	}


.btn-secondary {	.btn-secondary {
  color: #fff;	  --bs-btn-color: #fff;
  background-color: #6c757d;	  --bs-btn-bg: #6c757d;
  border-color: #6c757d;	  --bs-btn-border-color: #6c757d;
}	  --bs-btn-hover-color: #fff;
.btn-secondary:hover {	  --bs-btn-hover-bg: #5c636a;
  color: #fff;	  --bs-btn-hover-border-color: #565e64;
  background-color: #5c636a;	  --bs-btn-focus-shadow-rgb: 130, 138, 145;
  border-color: #565e64;	  --bs-btn-active-color: #fff;
}	  --bs-btn-active-bg: #565e64;
.btn-check:focus + .btn-secondary, .btn-secondary:focus {	  --bs-btn-active-border-color: #51585e;
  color: #fff;	  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  background-color: #5c636a;	  --bs-btn-disabled-color: #fff;
  border-color: #565e64;	  --bs-btn-disabled-bg: #6c757d;
  box-shadow: 0 0 0 0.25rem rgba(130, 138, 145, 0.5);	  --bs-btn-disabled-border-color: #6c757d;
}	
.btn-check:checked + .btn-secondary, .btn-check:active + .btn-secondary, .btn-secondary:active, .btn-secondary.active, .show > .btn-secondary.dropdown-toggle {	
  color: #fff;	
  background-color: #565e64;	
  border-color: #51585e;	
}	
.btn-check:checked + .btn-secondary:focus, .btn-check:active + .btn-secondary:focus, .btn-secondary:active:focus, .btn-secondary.active:focus, .show > .btn-secondary.dropdown-toggle:focus {	
  box-shadow: 0 0 0 0.25rem rgba(130, 138, 145, 0.5);	
}	
.btn-secondary:disabled, .btn-secondary.disabled {	
  color: #fff;	
  background-color: #6c757d;	
  border-color: #6c757d;	
}	}


.btn-success {	.btn-success {
  color: #fff;	  --bs-btn-color: #fff;
  background-color: #198754;	  --bs-btn-bg: #198754;
  border-color: #198754;	  --bs-btn-border-color: #198754;
}	  --bs-btn-hover-color: #fff;
.btn-success:hover {	  --bs-btn-hover-bg: #157347;
  color: #fff;	  --bs-btn-hover-border-color: #146c43;
  background-color: #157347;	  --bs-btn-focus-shadow-rgb: 60, 153, 110;
  border-color: #146c43;	  --bs-btn-active-color: #fff;
}	  --bs-btn-active-bg: #146c43;
.btn-check:focus + .btn-success, .btn-success:focus {	  --bs-btn-active-border-color: #13653f;
  color: #fff;	  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  background-color: #157347;	  --bs-btn-disabled-color: #fff;
  border-color: #146c43;	  --bs-btn-disabled-bg: #198754;
  box-shadow: 0 0 0 0.25rem rgba(60, 153, 110, 0.5);	  --bs-btn-disabled-border-color: #198754;
}	
.btn-check:checked + .btn-success, .btn-check:active + .btn-success, .btn-success:active, .btn-success.active, .show > .btn-success.dropdown-toggle {	
  color: #fff;	
  background-color: #146c43;	
  border-color: #13653f;	
}	
.btn-check:checked + .btn-success:focus, .btn-check:active + .btn-success:focus, .btn-success:active:focus, .btn-success.active:focus, .show > .btn-success.dropdown-toggle:focus {	
  box-shadow: 0 0 0 0.25rem rgba(60, 153, 110, 0.5);	
}	
.btn-success:disabled, .btn-success.disabled {	
  color: #fff;	
  background-color: #198754;	
  border-color: #198754;	
}	}


.btn-info {	.btn-info {
  color: #000;	  --bs-btn-color: #000;
  background-color: #0dcaf0;	  --bs-btn-bg: #0dcaf0;
  border-color: #0dcaf0;	  --bs-btn-border-color: #0dcaf0;
}	  --bs-btn-hover-color: #000;
.btn-info:hover {	  --bs-btn-hover-bg: #31d2f2;
  color: #000;	  --bs-btn-hover-border-color: #25cff2;
  background-color: #31d2f2;	  --bs-btn-focus-shadow-rgb: 11, 172, 204;
  border-color: #25cff2;	  --bs-btn-active-color: #000;
}	  --bs-btn-active-bg: #3dd5f3;
.btn-check:focus + .btn-info, .btn-info:focus {	  --bs-btn-active-border-color: #25cff2;
  color: #000;	  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  background-color: #31d2f2;	  --bs-btn-disabled-color: #000;
  border-color: #25cff2;	  --bs-btn-disabled-bg: #0dcaf0;
  box-shadow: 0 0 0 0.25rem rgba(11, 172, 204, 0.5);	  --bs-btn-disabled-border-color: #0dcaf0;
}	
.btn-check:checked + .btn-info, .btn-check:active + .btn-info, .btn-info:active, .btn-info.active, .show > .btn-info.dropdown-toggle {	
  color: #000;	
  background-color: #3dd5f3;	
  border-color: #25cff2;	
}	
.btn-check:checked + .btn-info:focus, .btn-check:active + .btn-info:focus, .btn-info:active:focus, .btn-info.active:focus, .show > .btn-info.dropdown-toggle:focus {	
  box-shadow: 0 0 0 0.25rem rgba(11, 172, 204, 0.5);	
}	
.btn-info:disabled, .btn-info.disabled {	
  color: #000;	
  background-color: #0dcaf0;	
  border-color: #0dcaf0;	
}	}


.btn-warning {	.btn-warning {
  color: #000;	  --bs-btn-color: #000;
  background-color: #ffc107;	  --bs-btn-bg: #ffc107;
  border-color: #ffc107;	  --bs-btn-border-color: #ffc107;
}	  --bs-btn-hover-color: #000;
.btn-warning:hover {	  --bs-btn-hover-bg: #ffca2c;
  color: #000;	  --bs-btn-hover-border-color: #ffc720;
  background-color: #ffca2c;	  --bs-btn-focus-shadow-rgb: 217, 164, 6;
  border-color: #ffc720;	  --bs-btn-active-color: #000;
  --bs-btn-active-bg: #ffcd39;
  --bs-btn-active-border-color: #ffc720;
  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  --bs-btn-disabled-color: #000;
  --bs-btn-disabled-bg: #ffc107;
  --bs-btn-disabled-border-color: #ffc107;
}	}
.btn-check:focus + .btn-warning, .btn-warning:focus {	
  color: #000;	.btn-danger {
  background-color: #ffca2c;	  --bs-btn-color: #fff;
  border-color: #ffc720;	  --bs-btn-bg: #dc3545;
  box-shadow: 0 0 0 0.25rem rgba(217, 164, 6, 0.5);	  --bs-btn-border-color: #dc3545;
}	  --bs-btn-hover-color: #fff;
.btn-check:checked + .btn-warning, .btn-check:active + .btn-warning, .btn-warning:active, .btn-warning.active, .show > .btn-warning.dropdown-toggle {	  --bs-btn-hover-bg: #bb2d3b;
  color: #000;	  --bs-btn-hover-border-color: #b02a37;
  background-color: #ffcd39;	  --bs-btn-focus-shadow-rgb: 225, 83, 97;
  border-color: #ffc720;	  --bs-btn-active-color: #fff;
}	  --bs-btn-active-bg: #b02a37;
.btn-check:checked + .btn-warning:focus, .btn-check:active + .btn-warning:focus, .btn-warning:active:focus, .btn-warning.active:focus, .show > .btn-warning.dropdown-toggle:focus {	  --bs-btn-active-border-color: #a52834;
  box-shadow: 0 0 0 0.25rem rgba(217, 164, 6, 0.5);	  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  --bs-btn-disabled-color: #fff;
  --bs-btn-disabled-bg: #dc3545;
  --bs-btn-disabled-border-color: #dc3545;
}	}
.btn-warning:disabled, .btn-warning.disabled {	
  color: #000;	.btn-light {
  background-color: #ffc107;	  --bs-btn-color: #000;
  border-color: #ffc107;	  --bs-btn-bg: #f8f9fa;
  --bs-btn-border-color: #f8f9fa;
  --bs-btn-hover-color: #000;
  --bs-btn-hover-bg: #d3d4d5;
  --bs-btn-hover-border-color: #c6c7c8;
  --bs-btn-focus-shadow-rgb: 211, 212, 213;
  --bs-btn-active-color: #000;
  --bs-btn-active-bg: #c6c7c8;
  --bs-btn-active-border-color: #babbbc;
  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  --bs-btn-disabled-color: #000;
  --bs-btn-disabled-bg: #f8f9fa;
  --bs-btn-disabled-border-color: #f8f9fa;
}	}


.btn-danger {	.btn-dark {
  color: #fff;	  --bs-btn-color: #fff;
  background-color: #dc3545;	  --bs-btn-bg: #212529;
  border-color: #dc3545;	  --bs-btn-border-color: #212529;
  --bs-btn-hover-color: #fff;
  --bs-btn-hover-bg: #424649;
  --bs-btn-hover-border-color: #373b3e;
  --bs-btn-focus-shadow-rgb: 66, 70, 73;
  --bs-btn-active-color: #fff;
  --bs-btn-active-bg: #4d5154;
  --bs-btn-active-border-color: #373b3e;
  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  --bs-btn-disabled-color: #fff;
  --bs-btn-disabled-bg: #212529;
  --bs-btn-disabled-border-color: #212529;
}	}
.btn-danger:hover {	
  color: #fff;	.btn-outline-primary {
  background-color: #bb2d3b;	  --bs-btn-color: #0d6efd;
  border-color: #b02a37;	  --bs-btn-border-color: #0d6efd;
  --bs-btn-hover-color: #fff;
  --bs-btn-hover-bg: #0d6efd;
  --bs-btn-hover-border-color: #0d6efd;
  --bs-btn-focus-shadow-rgb: 13, 110, 253;
  --bs-btn-active-color: #fff;
  --bs-btn-active-bg: #0d6efd;
  --bs-btn-active-border-color: #0d6efd;
  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  --bs-btn-disabled-color: #0d6efd;
  --bs-btn-disabled-bg: transparent;
  --bs-btn-disabled-border-color: #0d6efd;
  --bs-gradient: none;
}	}
.btn-check:focus + .btn-danger, .btn-danger:focus {	
  color: #fff;	.btn-outline-secondary {
  background-color: #bb2d3b;	  --bs-btn-color: #6c757d;
  border-color: #b02a37;	  --bs-btn-border-color: #6c757d;
  box-shadow: 0 0 0 0.25rem rgba(225, 83, 97, 0.5);	  --bs-btn-hover-color: #fff;
  --bs-btn-hover-bg: #6c757d;
  --bs-btn-hover-border-color: #6c757d;
  --bs-btn-focus-shadow-rgb: 108, 117, 125;
  --bs-btn-active-color: #fff;
  --bs-btn-active-bg: #6c757d;
  --bs-btn-active-border-color: #6c757d;
  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  --bs-btn-disabled-color: #6c757d;
  --bs-btn-disabled-bg: transparent;
  --bs-btn-disabled-border-color: #6c757d;
  --bs-gradient: none;
}	}
.btn-check:checked + .btn-danger, .btn-check:active + .btn-danger, .btn-danger:active, .btn-danger.active, .show > .btn-danger.dropdown-toggle {	
  color: #fff;	.btn-outline-success {
  background-color: #b02a37;	  --bs-btn-color: #198754;
  border-color: #a52834;	  --bs-btn-border-color: #198754;
  --bs-btn-hover-color: #fff;
  --bs-btn-hover-bg: #198754;
  --bs-btn-hover-border-color: #198754;
  --bs-btn-focus-shadow-rgb: 25, 135, 84;
  --bs-btn-active-color: #fff;
  --bs-btn-active-bg: #198754;
  --bs-btn-active-border-color: #198754;
  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  --bs-btn-disabled-color: #198754;
  --bs-btn-disabled-bg: transparent;
  --bs-btn-disabled-border-color: #198754;
  --bs-gradient: none;
}	}
.btn-check:checked + .btn-danger:focus, .btn-check:active + .btn-danger:focus, .btn-danger:active:focus, .btn-danger.active:focus, .show > .btn-danger.dropdown-toggle:focus {	
  box-shadow: 0 0 0 0.25rem rgba(225, 83, 97, 0.5);	.btn-outline-info {
  --bs-btn-color: #0dcaf0;
  --bs-btn-border-color: #0dcaf0;
  --bs-btn-hover-color: #000;
  --bs-btn-hover-bg: #0dcaf0;
  --bs-btn-hover-border-color: #0dcaf0;
  --bs-btn-focus-shadow-rgb: 13, 202, 240;
  --bs-btn-active-color: #000;
  --bs-btn-active-bg: #0dcaf0;
  --bs-btn-active-border-color: #0dcaf0;
  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  --bs-btn-disabled-color: #0dcaf0;
  --bs-btn-disabled-bg: transparent;
  --bs-btn-disabled-border-color: #0dcaf0;
  --bs-gradient: none;
}	}
.btn-danger:disabled, .btn-danger.disabled {	
  color: #fff;	.btn-outline-warning {
  background-color: #dc3545;	  --bs-btn-color: #ffc107;
  border-color: #dc3545;	  --bs-btn-border-color: #ffc107;
  --bs-btn-hover-color: #000;
  --bs-btn-hover-bg: #ffc107;
  --bs-btn-hover-border-color: #ffc107;
  --bs-btn-focus-shadow-rgb: 255, 193, 7;
  --bs-btn-active-color: #000;
  --bs-btn-active-bg: #ffc107;
  --bs-btn-active-border-color: #ffc107;
  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  --bs-btn-disabled-color: #ffc107;
  --bs-btn-disabled-bg: transparent;
  --bs-btn-disabled-border-color: #ffc107;
  --bs-gradient: none;
}	}


.btn-light {	.btn-outline-danger {
  color: #000;	  --bs-btn-color: #dc3545;
  background-color: #f8f9fa;	  --bs-btn-border-color: #dc3545;
  border-color: #f8f9fa;	  --bs-btn-hover-color: #fff;
  --bs-btn-hover-bg: #dc3545;
  --bs-btn-hover-border-color: #dc3545;
  --bs-btn-focus-shadow-rgb: 220, 53, 69;
  --bs-btn-active-color: #fff;
  --bs-btn-active-bg: #dc3545;
  --bs-btn-active-border-color: #dc3545;
  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  --bs-btn-disabled-color: #dc3545;
  --bs-btn-disabled-bg: transparent;
  --bs-btn-disabled-border-color: #dc3545;
  --bs-gradient: none;
}	}
.btn-light:hover {	
  color: #000;	.btn-outline-light {
  background-color: #f9fafb;	  --bs-btn-color: #f8f9fa;
  border-color: #f9fafb;	  --bs-btn-border-color: #f8f9fa;
  --bs-btn-hover-color: #000;
  --bs-btn-hover-bg: #f8f9fa;
  --bs-btn-hover-border-color: #f8f9fa;
  --bs-btn-focus-shadow-rgb: 248, 249, 250;
  --bs-btn-active-color: #000;
  --bs-btn-active-bg: #f8f9fa;
  --bs-btn-active-border-color: #f8f9fa;
  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  --bs-btn-disabled-color: #f8f9fa;
  --bs-btn-disabled-bg: transparent;
  --bs-btn-disabled-border-color: #f8f9fa;
  --bs-gradient: none;
}	}
.btn-check:focus + .btn-light, .btn-light:focus {	
  color: #000;	.btn-outline-dark {
  background-color: #f9fafb;	  --bs-btn-color: #212529;
  border-color: #f9fafb;	  --bs-btn-border-color: #212529;
  box-shadow: 0 0 0 0.25rem rgba(211, 212, 213, 0.5);	  --bs-btn-hover-color: #fff;
  --bs-btn-hover-bg: #212529;
  --bs-btn-hover-border-color: #212529;
  --bs-btn-focus-shadow-rgb: 33, 37, 41;
  --bs-btn-active-color: #fff;
  --bs-btn-active-bg: #212529;
  --bs-btn-active-border-color: #212529;
  --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  --bs-btn-disabled-color: #212529;
  --bs-btn-disabled-bg: transparent;
  --bs-btn-disabled-border-color: #212529;
  --bs-gradient: none;
}	}
.btn-check:checked + .btn-light, .btn-check:active + .btn-light, .btn-light:active, .btn-light.active, .show > .btn-light.dropdown-toggle {	
  color: #000;	.btn-link {
  background-color: #f9fafb;	  --bs-btn-font-weight: 400;
  border-color: #f9fafb;	  --bs-btn-color: var(--bs-link-color);
  --bs-btn-bg: transparent;
  --bs-btn-border-color: transparent;
  --bs-btn-hover-color: var(--bs-link-hover-color);
  --bs-btn-hover-border-color: transparent;
  --bs-btn-active-color: var(--bs-link-hover-color);
  --bs-btn-active-border-color: transparent;
  --bs-btn-disabled-color: #6c757d;
  --bs-btn-disabled-border-color: transparent;
  --bs-btn-box-shadow: none;
  --bs-btn-focus-shadow-rgb: 49, 132, 253;
  text-decoration: underline;
}	}
.btn-check:checked + .btn-light:focus, .btn-check:active + .btn-light:focus, .btn-light:active:focus, .btn-light.active:focus, .show > .btn-light.dropdown-toggle:focus {	.btn-link:focus-visible {
  box-shadow: 0 0 0 0.25rem rgba(211, 212, 213, 0.5);	  color: var(--bs-btn-color);
}	}
.btn-light:disabled, .btn-light.disabled {	.btn-link:hover {
  color: #000;	  color: var(--bs-btn-hover-color);
  background-color: #f8f9fa;	
  border-color: #f8f9fa;	
}	}


.btn-dark {	.btn-lg, .btn-group-lg > .btn {
  color: #fff;	  --bs-btn-padding-y: 0.5rem;
  background-color: #212529;	  --bs-btn-padding-x: 1rem;
  border-color: #212529;	  --bs-btn-font-size: 1.25rem;
  --bs-btn-border-radius: 0.5rem;
}	}
.btn-dark:hover {	
  color: #fff;	.btn-sm, .btn-group-sm > .btn {
  background-color: #1c1f23;	  --bs-btn-padding-y: 0.25rem;
  border-color: #1a1e21;	  --bs-btn-padding-x: 0.5rem;
  --bs-btn-font-size: 0.875rem;
  --bs-btn-border-radius: 0.25rem;
}	}
.btn-check:focus + .btn-dark, .btn-dark:focus {	
  color: #fff;	.fade {
  background-color: #1c1f23;	  transition: opacity 0.15s linear;
  border-color: #1a1e21;	
  box-shadow: 0 0 0 0.25rem rgba(66, 70, 73, 0.5);	
}	}
.btn-check:checked + .btn-dark, .btn-check:active + .btn-dark, .btn-dark:active, .btn-dark.active, .show > .btn-dark.dropdown-toggle {	@media (prefers-reduced-motion: reduce) {
  color: #fff;	  .fade {
  background-color: #1a1e21;	    transition: none;
  border-color: #191c1f;	  }
}	}
.btn-check:checked + .btn-dark:focus, .btn-check:active + .btn-dark:focus, .btn-dark:active:focus, .btn-dark.active:focus, .show > .btn-dark.dropdown-toggle:focus {	.fade:not(.show) {
  box-shadow: 0 0 0 0.25rem rgba(66, 70, 73, 0.5);	  opacity: 0;
}	}
.btn-dark:disabled, .btn-dark.disabled {	
  color: #fff;	.collapse:not(.show) {
  background-color: #212529;	  display: none;
  border-color: #212529;	
}	}


.btn-outline-primary {	.collapsing {
  color: #0d6efd;	  height: 0;
  border-color: #0d6efd;	  overflow: hidden;
}	  transition: height 0.35s ease;
.btn-outline-primary:hover {	
  color: #fff;	
  background-color: #0d6efd;	
  border-color: #0d6efd;	
}	
.btn-check:focus + .btn-outline-primary, .btn-outline-primary:focus {	
  box-shadow: 0 0 0 0.25rem rgba(13, 110, 253, 0.5);	
}	
.btn-check:checked + .btn-outline-primary, .btn-check:active + .btn-outline-primary, .btn-outline-primary:active, .btn-outline-primary.active, .btn-outline-primary.dropdown-toggle.show {	
  color: #fff;	
  background-color: #0d6efd;	
  border-color: #0d6efd;	
}	
.btn-check:checked + .btn-outline-primary:focus, .btn-check:active + .btn-outline-primary:focus, .btn-outline-primary:active:focus, .btn-outline-primary.active:focus, .btn-outline-primary.dropdown-toggle.show:focus {	
  box-shadow: 0 0 0 0.25rem rgba(13, 110, 253, 0.5);	
}	
.btn-outline-primary:disabled, .btn-outline-primary.disabled {	
  color: #0d6efd;	
  background-color: transparent;	
}	

.btn-outline-secondary {	
  color: #6c757d;	
  border-color: #6c757d;	
}	
.btn-outline-secondary:hover {	
  color: #fff;	
  background-color: #6c757d;	
  border-color: #6c757d;	
}	
.btn-check:focus + .btn-outline-secondary, .btn-outline-secondary:focus {	
  box-shadow: 0 0 0 0.25rem rgba(108, 117, 125, 0.5);	
}	
.btn-check:checked + .btn-outline-secondary, .btn-check:active + .btn-outline-secondary, .btn-outline-secondary:active, .btn-outline-secondary.active, .btn-outline-secondary.dropdown-toggle.show {	
  color: #fff;	
  background-color: #6c757d;	
  border-color: #6c757d;	
}	
.btn-check:checked + .btn-outline-secondary:focus, .btn-check:active + .btn-outline-secondary:focus, .btn-outline-secondary:active:focus, .btn-outline-secondary.active:focus, .btn-outline-secondary.dropdown-toggle.show:focus {	
  box-shadow: 0 0 0 0.25rem rgba(108, 117, 125, 0.5);	
}	
.btn-outline-secondary:disabled, .btn-outline-secondary.disabled {	
  color: #6c757d;	
  background-color: transparent;	
}	

.btn-outline-success {	
  color: #198754;	
  border-color: #198754;	
}	
.btn-outline-success:hover {	
  color: #fff;	
  background-color: #198754;	
  border-color: #198754;	
}	
.btn-check:focus + .btn-outline-success, .btn-outline-success:focus {	
  box-shadow: 0 0 0 0.25rem rgba(25, 135, 84, 0.5);	
}	
.btn-check:checked + .btn-outline-success, .btn-check:active + .btn-outline-success, .btn-outline-success:active, .btn-outline-success.active, .btn-outline-success.dropdown-toggle.show {	
  color: #fff;	
  background-color: #198754;	
  border-color: #198754;	
}	
.btn-check:checked + .btn-outline-success:focus, .btn-check:active + .btn-outline-success:focus, .btn-outline-success:active:focus, .btn-outline-success.active:focus, .btn-outline-success.dropdown-toggle.show:focus {	
  box-shadow: 0 0 0 0.25rem rgba(25, 135, 84, 0.5);	
}	
.btn-outline-success:disabled, .btn-outline-success.disabled {	
  color: #198754;	
  background-color: transparent;	
}	

.btn-outline-info {	
  color: #0dcaf0;	
  border-color: #0dcaf0;	
}	
.btn-outline-info:hover {	
  color: #000;	
  background-color: #0dcaf0;	
  border-color: #0dcaf0;	
}	
.btn-check:focus + .btn-outline-info, .btn-outline-info:focus {	
  box-shadow: 0 0 0 0.25rem rgba(13, 202, 240, 0.5);	
}	
.btn-check:checked + .btn-outline-info, .btn-check:active + .btn-outline-info, .btn-outline-info:active, .btn-outline-info.active, .btn-outline-info.dropdown-toggle.show {	
  color: #000;	
  background-color: #0dcaf0;	
  border-color: #0dcaf0;	
}	
.btn-check:checked + .btn-outline-info:focus, .btn-check:active + .btn-outline-info:focus, .btn-outline-info:active:focus, .btn-outline-info.active:focus, .btn-outline-info.dropdown-toggle.show:focus {	
  box-shadow: 0 0 0 0.25rem rgba(13, 202, 240, 0.5);	
}	
.btn-outline-info:disabled, .btn-outline-info.disabled {	
  color: #0dcaf0;	
  background-color: transparent;	
}	

.btn-outline-warning {	
  color: #ffc107;	
  border-color: #ffc107;	
}	
.btn-outline-warning:hover {	
  color: #000;	
  background-color: #ffc107;	
  border-color: #ffc107;	
}	
.btn-check:focus + .btn-outline-warning, .btn-outline-warning:focus {	
  box-shadow: 0 0 0 0.25rem rgba(255, 193, 7, 0.5);	
}	
.btn-check:checked + .btn-outline-warning, .btn-check:active + .btn-outline-warning, .btn-outline-warning:active, .btn-outline-warning.active, .btn-outline-warning.dropdown-toggle.show {	
  color: #000;	
  background-color: #ffc107;	
  border-color: #ffc107;	
}	
.btn-check:checked + .btn-outline-warning:focus, .btn-check:active + .btn-outline-warning:focus, .btn-outline-warning:active:focus, .btn-outline-warning.active:focus, .btn-outline-warning.dropdown-toggle.show:focus {	
  box-shadow: 0 0 0 0.25rem rgba(255, 193, 7, 0.5);	
}	
.btn-outline-warning:disabled, .btn-outline-warning.disabled {	
  color: #ffc107;	
  background-color: transparent;	
}	

.btn-outline-danger {	
  color: #dc3545;	
  border-color: #dc3545;	
}	
.btn-outline-danger:hover {	
  color: #fff;	
  background-color: #dc3545;	
  border-color: #dc3545;	
}	
.btn-check:focus + .btn-outline-danger, .btn-outline-danger:focus {	
  box-shadow: 0 0 0 0.25rem rgba(220, 53, 69, 0.5);	
}	
.btn-check:checked + .btn-outline-danger, .btn-check:active + .btn-outline-danger, .btn-outline-danger:active, .btn-outline-danger.active, .btn-outline-danger.dropdown-toggle.show {	
  color: #fff;	
  background-color: #dc3545;	
  border-color: #dc3545;	
}	
.btn-check:checked + .btn-outline-danger:focus, .btn-check:active + .btn-outline-danger:focus, .btn-outline-danger:active:focus, .btn-outline-danger.active:focus, .btn-outline-danger.dropdown-toggle.show:focus {	
  box-shadow: 0 0 0 0.25rem rgba(220, 53, 69, 0.5);	
}	
.btn-outline-danger:disabled, .btn-outline-danger.disabled {	
  color: #dc3545;	
  background-color: transparent;	
}	

.btn-outline-light {	
  color: #f8f9fa;	
  border-color: #f8f9fa;	
}	
.btn-outline-light:hover {	
  color: #000;	
  background-color: #f8f9fa;	
  border-color: #f8f9fa;	
}	
.btn-check:focus + .btn-outline-light, .btn-outline-light:focus {	
  box-shadow: 0 0 0 0.25rem rgba(248, 249, 250, 0.5);	
}	
.btn-check:checked + .btn-outline-light, .btn-check:active + .btn-outline-light, .btn-outline-light:active, .btn-outline-light.active, .btn-outline-light.dropdown-toggle.show {	
  color: #000;	
  background-color: #f8f9fa;	
  border-color: #f8f9fa;	
}	
.btn-check:checked + .btn-outline-light:focus, .btn-check:active + .btn-outline-light:focus, .btn-outline-light:active:focus, .btn-outline-light.active:focus, .btn-outline-light.dropdown-toggle.show:focus {	
  box-shadow: 0 0 0 0.25rem rgba(248, 249, 250, 0.5);	
}	
.btn-outline-light:disabled, .btn-outline-light.disabled {	
  color: #f8f9fa;	
  background-color: transparent;	
}	

.btn-outline-dark {	
  color: #212529;	
  border-color: #212529;	
}	
.btn-outline-dark:hover {	
  color: #fff;	
  background-color: #212529;	
  border-color: #212529;	
}	
.btn-check:focus + .btn-outline-dark, .btn-outline-dark:focus {	
  box-shadow: 0 0 0 0.25rem rgba(33, 37, 41, 0.5);	
}	
.btn-check:checked + .btn-outline-dark, .btn-check:active + .btn-outline-dark, .btn-outline-dark:active, .btn-outline-dark.active, .btn-outline-dark.dropdown-toggle.show {	
  color: #fff;	
  background-color: #212529;	
  border-color: #212529;	
}	
.btn-check:checked + .btn-outline-dark:focus, .btn-check:active + .btn-outline-dark:focus, .btn-outline-dark:active:focus, .btn-outline-dark.active:focus, .btn-outline-dark.dropdown-toggle.show:focus {	
  box-shadow: 0 0 0 0.25rem rgba(33, 37, 41, 0.5);	
}	
.btn-outline-dark:disabled, .btn-outline-dark.disabled {	
  color: #212529;	
  background-color: transparent;	
}	

.btn-link {	
  font-weight: 400;	
  color: #0d6efd;	
  text-decoration: underline;	
}	
.btn-link:hover {	
  color: #0a58ca;	
}	
.btn-link:disabled, .btn-link.disabled {	
  color: #6c757d;	
}	

.btn-lg, .btn-group-lg > .btn {	
  padding: 0.5rem 1rem;	
  font-size: 1.25rem;	
  border-radius: 0.3rem;	
}	

.btn-sm, .btn-group-sm > .btn {	
  padding: 0.25rem 0.5rem;	
  font-size: 0.875rem;	
  border-radius: 0.2rem;	
}	

.fade {	
  transition: opacity 0.15s linear;	
}	
@media (prefers-reduced-motion: reduce) {	
  .fade {	
    transition: none;	
  }	
}	
.fade:not(.show) {	
  opacity: 0;	
}	

.collapse:not(.show) {	
  display: none;	
}	

.collapsing {	
  height: 0;	
  overflow: hidden;	
  transition: height 0.35s ease;	
}	}
@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
  .collapsing {	  .collapsing {
@@ -3532,7 +3191,9 @@ textarea.form-control-lg {
.dropup,	.dropup,
.dropend,	.dropend,
.dropdown,	.dropdown,
.dropstart {	.dropstart,
.dropup-center,
.dropdown-center {
  position: relative;	  position: relative;
}	}


@@ -3554,25 +3215,51 @@ textarea.form-control-lg {
}	}


.dropdown-menu {	.dropdown-menu {
  --bs-dropdown-zindex: 1000;
  --bs-dropdown-min-width: 10rem;
  --bs-dropdown-padding-x: 0;
  --bs-dropdown-padding-y: 0.5rem;
  --bs-dropdown-spacer: 0.125rem;
  --bs-dropdown-font-size: 1rem;
  --bs-dropdown-color: #212529;
  --bs-dropdown-bg: #fff;
  --bs-dropdown-border-color: var(--bs-border-color-translucent);
  --bs-dropdown-border-radius: 0.375rem;
  --bs-dropdown-border-width: 1px;
  --bs-dropdown-inner-border-radius: calc(0.375rem - 1px);
  --bs-dropdown-divider-bg: var(--bs-border-color-translucent);
  --bs-dropdown-divider-margin-y: 0.5rem;
  --bs-dropdown-box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15);
  --bs-dropdown-link-color: #212529;
  --bs-dropdown-link-hover-color: #1e2125;
  --bs-dropdown-link-hover-bg: #e9ecef;
  --bs-dropdown-link-active-color: #fff;
  --bs-dropdown-link-active-bg: #0d6efd;
  --bs-dropdown-link-disabled-color: #adb5bd;
  --bs-dropdown-item-padding-x: 1rem;
  --bs-dropdown-item-padding-y: 0.25rem;
  --bs-dropdown-header-color: #6c757d;
  --bs-dropdown-header-padding-x: 1rem;
  --bs-dropdown-header-padding-y: 0.5rem;
  position: absolute;	  position: absolute;
  z-index: 1000;	  z-index: var(--bs-dropdown-zindex);
  display: none;	  display: none;
  min-width: 10rem;	  min-width: var(--bs-dropdown-min-width);
  padding: 0.5rem 0;	  padding: var(--bs-dropdown-padding-y) var(--bs-dropdown-padding-x);
  margin: 0;	  margin: 0;
  font-size: 1rem;	  font-size: var(--bs-dropdown-font-size);
  color: #212529;	  color: var(--bs-dropdown-color);
  text-align: left;	  text-align: left;
  list-style: none;	  list-style: none;
  background-color: #fff;	  background-color: var(--bs-dropdown-bg);
  background-clip: padding-box;	  background-clip: padding-box;
  border: 1px solid rgba(0, 0, 0, 0.15);	  border: var(--bs-dropdown-border-width) solid var(--bs-dropdown-border-color);
  border-radius: 0.25rem;	  border-radius: var(--bs-dropdown-border-radius);
}	}
.dropdown-menu[data-bs-popper] {	.dropdown-menu[data-bs-popper] {
  top: 100%;	  top: 100%;
  left: 0;	  left: 0;
  margin-top: 0.125rem;	  margin-top: var(--bs-dropdown-spacer);
}	}


.dropdown-menu-start {	.dropdown-menu-start {
@@ -3599,7 +3286,6 @@ textarea.form-control-lg {
    right: auto;	    right: auto;
    left: 0;	    left: 0;
  }	  }

  .dropdown-menu-sm-end {	  .dropdown-menu-sm-end {
    --bs-position: end;	    --bs-position: end;
  }	  }
@@ -3616,7 +3302,6 @@ textarea.form-control-lg {
    right: auto;	    right: auto;
    left: 0;	    left: 0;
  }	  }

  .dropdown-menu-md-end {	  .dropdown-menu-md-end {
    --bs-position: end;	    --bs-position: end;
  }	  }
@@ -3633,7 +3318,6 @@ textarea.form-control-lg {
    right: auto;	    right: auto;
    left: 0;	    left: 0;
  }	  }

  .dropdown-menu-lg-end {	  .dropdown-menu-lg-end {
    --bs-position: end;	    --bs-position: end;
  }	  }
@@ -3650,7 +3334,6 @@ textarea.form-control-lg {
    right: auto;	    right: auto;
    left: 0;	    left: 0;
  }	  }

  .dropdown-menu-xl-end {	  .dropdown-menu-xl-end {
    --bs-position: end;	    --bs-position: end;
  }	  }
@@ -3667,7 +3350,6 @@ textarea.form-control-lg {
    right: auto;	    right: auto;
    left: 0;	    left: 0;
  }	  }

  .dropdown-menu-xxl-end {	  .dropdown-menu-xxl-end {
    --bs-position: end;	    --bs-position: end;
  }	  }
@@ -3680,7 +3362,7 @@ textarea.form-control-lg {
  top: auto;	  top: auto;
  bottom: 100%;	  bottom: 100%;
  margin-top: 0;	  margin-top: 0;
  margin-bottom: 0.125rem;	  margin-bottom: var(--bs-dropdown-spacer);
}	}
.dropup .dropdown-toggle::after {	.dropup .dropdown-toggle::after {
  display: inline-block;	  display: inline-block;
@@ -3701,7 +3383,7 @@ textarea.form-control-lg {
  right: auto;	  right: auto;
  left: 100%;	  left: 100%;
  margin-top: 0;	  margin-top: 0;
  margin-left: 0.125rem;	  margin-left: var(--bs-dropdown-spacer);
}	}
.dropend .dropdown-toggle::after {	.dropend .dropdown-toggle::after {
  display: inline-block;	  display: inline-block;
@@ -3725,7 +3407,7 @@ textarea.form-control-lg {
  right: 100%;	  right: 100%;
  left: auto;	  left: auto;
  margin-top: 0;	  margin-top: 0;
  margin-right: 0.125rem;	  margin-right: var(--bs-dropdown-spacer);
}	}
.dropstart .dropdown-toggle::after {	.dropstart .dropdown-toggle::after {
  display: inline-block;	  display: inline-block;
@@ -3754,35 +3436,36 @@ textarea.form-control-lg {


.dropdown-divider {	.dropdown-divider {
  height: 0;	  height: 0;
  margin: 0.5rem 0;	  margin: var(--bs-dropdown-divider-margin-y) 0;
  overflow: hidden;	  overflow: hidden;
  border-top: 1px solid rgba(0, 0, 0, 0.15);	  border-top: 1px solid var(--bs-dropdown-divider-bg);
  opacity: 1;
}	}


.dropdown-item {	.dropdown-item {
  display: block;	  display: block;
  width: 100%;	  width: 100%;
  padding: 0.25rem 1rem;	  padding: var(--bs-dropdown-item-padding-y) var(--bs-dropdown-item-padding-x);
  clear: both;	  clear: both;
  font-weight: 400;	  font-weight: 400;
  color: #212529;	  color: var(--bs-dropdown-link-color);
  text-align: inherit;	  text-align: inherit;
  text-decoration: none;	  text-decoration: none;
  white-space: nowrap;	  white-space: nowrap;
  background-color: transparent;	  background-color: transparent;
  border: 0;	  border: 0;
}	}
.dropdown-item:hover, .dropdown-item:focus {	.dropdown-item:hover, .dropdown-item:focus {
  color: #1e2125;	  color: var(--bs-dropdown-link-hover-color);
  background-color: #e9ecef;	  background-color: var(--bs-dropdown-link-hover-bg);
}	}
.dropdown-item.active, .dropdown-item:active {	.dropdown-item.active, .dropdown-item:active {
  color: #fff;	  color: var(--bs-dropdown-link-active-color);
  text-decoration: none;	  text-decoration: none;
  background-color: #0d6efd;	  background-color: var(--bs-dropdown-link-active-bg);
}	}
.dropdown-item.disabled, .dropdown-item:disabled {	.dropdown-item.disabled, .dropdown-item:disabled {
  color: #adb5bd;	  color: var(--bs-dropdown-link-disabled-color);
  pointer-events: none;	  pointer-events: none;
  background-color: transparent;	  background-color: transparent;
}	}
@@ -3793,46 +3476,32 @@ textarea.form-control-lg {


.dropdown-header {	.dropdown-header {
  display: block;	  display: block;
  padding: 0.5rem 1rem;	  padding: var(--bs-dropdown-header-padding-y) var(--bs-dropdown-header-padding-x);
  margin-bottom: 0;	  margin-bottom: 0;
  font-size: 0.875rem;	  font-size: 0.875rem;
  color: #6c757d;	  color: var(--bs-dropdown-header-color);
  white-space: nowrap;	  white-space: nowrap;
}	}


.dropdown-item-text {	.dropdown-item-text {
  display: block;	  display: block;
  padding: 0.25rem 1rem;	  padding: var(--bs-dropdown-item-padding-y) var(--bs-dropdown-item-padding-x);
  color: #212529;	  color: var(--bs-dropdown-link-color);
}	}


.dropdown-menu-dark {	.dropdown-menu-dark {
  color: #dee2e6;	  --bs-dropdown-color: #dee2e6;
  background-color: #343a40;	  --bs-dropdown-bg: #343a40;
  border-color: rgba(0, 0, 0, 0.15);	  --bs-dropdown-border-color: var(--bs-border-color-translucent);
}	  --bs-dropdown-box-shadow: ;
.dropdown-menu-dark .dropdown-item {	  --bs-dropdown-link-color: #dee2e6;
  color: #dee2e6;	  --bs-dropdown-link-hover-color: #fff;
}	  --bs-dropdown-divider-bg: var(--bs-border-color-translucent);
.dropdown-menu-dark .dropdown-item:hover, .dropdown-menu-dark .dropdown-item:focus {	  --bs-dropdown-link-hover-bg: rgba(255, 255, 255, 0.15);
  color: #fff;	  --bs-dropdown-link-active-color: #fff;
  background-color: rgba(255, 255, 255, 0.15);	  --bs-dropdown-link-active-bg: #0d6efd;
}	  --bs-dropdown-link-disabled-color: #adb5bd;
.dropdown-menu-dark .dropdown-item.active, .dropdown-menu-dark .dropdown-item:active {	  --bs-dropdown-header-color: #adb5bd;
  color: #fff;	
  background-color: #0d6efd;	
}	
.dropdown-menu-dark .dropdown-item.disabled, .dropdown-menu-dark .dropdown-item:disabled {	
  color: #adb5bd;	
}	
.dropdown-menu-dark .dropdown-divider {	
  border-color: rgba(0, 0, 0, 0.15);	
}	
.dropdown-menu-dark .dropdown-item-text {	
  color: #dee2e6;	
}	
.dropdown-menu-dark .dropdown-header {	
  color: #adb5bd;	
}	}


.btn-group,	.btn-group,
@@ -3870,11 +3539,15 @@ textarea.form-control-lg {
  width: auto;	  width: auto;
}	}


.btn-group > .btn:not(:first-child),	.btn-group {
  border-radius: 0.375rem;
}
.btn-group > :not(.btn-check:first-child) + .btn,
.btn-group > .btn-group:not(:first-child) {	.btn-group > .btn-group:not(:first-child) {
  margin-left: -1px;	  margin-left: -1px;
}	}
.btn-group > .btn:not(:last-child):not(.dropdown-toggle),	.btn-group > .btn:not(:last-child):not(.dropdown-toggle),
.btn-group > .btn.dropdown-toggle-split:first-child,
.btn-group > .btn-group:not(:last-child) > .btn {	.btn-group > .btn-group:not(:last-child) > .btn {
  border-top-right-radius: 0;	  border-top-right-radius: 0;
  border-bottom-right-radius: 0;	  border-bottom-right-radius: 0;
@@ -3932,6 +3605,12 @@ textarea.form-control-lg {
}	}


.nav {	.nav {
  --bs-nav-link-padding-x: 1rem;
  --bs-nav-link-padding-y: 0.5rem;
  --bs-nav-link-font-weight: ;
  --bs-nav-link-color: var(--bs-link-color);
  --bs-nav-link-hover-color: var(--bs-link-hover-color);
  --bs-nav-link-disabled-color: #6c757d;
  display: flex;	  display: flex;
  flex-wrap: wrap;	  flex-wrap: wrap;
  padding-left: 0;	  padding-left: 0;
@@ -3941,8 +3620,10 @@ textarea.form-control-lg {


.nav-link {	.nav-link {
  display: block;	  display: block;
  padding: 0.5rem 1rem;	  padding: var(--bs-nav-link-padding-y) var(--bs-nav-link-padding-x);
  color: #0d6efd;	  font-size: var(--bs-nav-link-font-size);
  font-weight: var(--bs-nav-link-font-weight);
  color: var(--bs-nav-link-color);
  text-decoration: none;	  text-decoration: none;
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out;	  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out;
}	}
@@ -3952,54 +3633,71 @@ textarea.form-control-lg {
  }	  }
}	}
.nav-link:hover, .nav-link:focus {	.nav-link:hover, .nav-link:focus {
  color: #0a58ca;	  color: var(--bs-nav-link-hover-color);
}	}
.nav-link.disabled {	.nav-link.disabled {
  color: #6c757d;	  color: var(--bs-nav-link-disabled-color);
  pointer-events: none;	  pointer-events: none;
  cursor: default;	  cursor: default;
}	}


.nav-tabs {	.nav-tabs {
  border-bottom: 1px solid #dee2e6;	  --bs-nav-tabs-border-width: 1px;
  --bs-nav-tabs-border-color: #dee2e6;
  --bs-nav-tabs-border-radius: 0.375rem;
  --bs-nav-tabs-link-hover-border-color: #e9ecef #e9ecef #dee2e6;
  --bs-nav-tabs-link-active-color: #495057;
  --bs-nav-tabs-link-active-bg: #fff;
  --bs-nav-tabs-link-active-border-color: #dee2e6 #dee2e6 #fff;
  border-bottom: var(--bs-nav-tabs-border-width) solid var(--bs-nav-tabs-border-color);
}	}
.nav-tabs .nav-link {	.nav-tabs .nav-link {
  margin-bottom: -1px;	  margin-bottom: calc(-1 * var(--bs-nav-tabs-border-width));
  background: none;	  background: none;
  border: 1px solid transparent;	  border: var(--bs-nav-tabs-border-width) solid transparent;
  border-top-left-radius: 0.25rem;	  border-top-left-radius: var(--bs-nav-tabs-border-radius);
  border-top-right-radius: 0.25rem;	  border-top-right-radius: var(--bs-nav-tabs-border-radius);
}	}
.nav-tabs .nav-link:hover, .nav-tabs .nav-link:focus {	.nav-tabs .nav-link:hover, .nav-tabs .nav-link:focus {
  border-color: #e9ecef #e9ecef #dee2e6;	
  isolation: isolate;	  isolation: isolate;
  border-color: var(--bs-nav-tabs-link-hover-border-color);
}	}
.nav-tabs .nav-link.disabled {	.nav-tabs .nav-link.disabled, .nav-tabs .nav-link:disabled {
  color: #6c757d;	  color: var(--bs-nav-link-disabled-color);
  background-color: transparent;	  background-color: transparent;
  border-color: transparent;	  border-color: transparent;
}	}
.nav-tabs .nav-link.active,	.nav-tabs .nav-link.active,
.nav-tabs .nav-item.show .nav-link {	.nav-tabs .nav-item.show .nav-link {
  color: #495057;	  color: var(--bs-nav-tabs-link-active-color);
  background-color: #fff;	  background-color: var(--bs-nav-tabs-link-active-bg);
  border-color: #dee2e6 #dee2e6 #fff;	  border-color: var(--bs-nav-tabs-link-active-border-color);
}	}
.nav-tabs .dropdown-menu {	.nav-tabs .dropdown-menu {
  margin-top: -1px;	  margin-top: calc(-1 * var(--bs-nav-tabs-border-width));
  border-top-left-radius: 0;	  border-top-left-radius: 0;
  border-top-right-radius: 0;	  border-top-right-radius: 0;
}	}


.nav-pills {
  --bs-nav-pills-border-radius: 0.375rem;
  --bs-nav-pills-link-active-color: #fff;
  --bs-nav-pills-link-active-bg: #0d6efd;
}
.nav-pills .nav-link {	.nav-pills .nav-link {
  background: none;	  background: none;
  border: 0;	  border: 0;
  border-radius: 0.25rem;	  border-radius: var(--bs-nav-pills-border-radius);
}
.nav-pills .nav-link:disabled {
  color: var(--bs-nav-link-disabled-color);
  background-color: transparent;
  border-color: transparent;
}	}
.nav-pills .nav-link.active,	.nav-pills .nav-link.active,
.nav-pills .show > .nav-link {	.nav-pills .show > .nav-link {
  color: #fff;	  color: var(--bs-nav-pills-link-active-color);
  background-color: #0d6efd;	  background-color: var(--bs-nav-pills-link-active-bg);
}	}


.nav-fill > .nav-link,	.nav-fill > .nav-link,
@@ -4028,13 +3726,32 @@ textarea.form-control-lg {
}	}


.navbar {	.navbar {
  --bs-navbar-padding-x: 0;
  --bs-navbar-padding-y: 0.5rem;
  --bs-navbar-color: rgba(0, 0, 0, 0.55);
  --bs-navbar-hover-color: rgba(0, 0, 0, 0.7);
  --bs-navbar-disabled-color: rgba(0, 0, 0, 0.3);
  --bs-navbar-active-color: rgba(0, 0, 0, 0.9);
  --bs-navbar-brand-padding-y: 0.3125rem;
  --bs-navbar-brand-margin-end: 1rem;
  --bs-navbar-brand-font-size: 1.25rem;
  --bs-navbar-brand-color: rgba(0, 0, 0, 0.9);
  --bs-navbar-brand-hover-color: rgba(0, 0, 0, 0.9);
  --bs-navbar-nav-link-padding-x: 0.5rem;
  --bs-navbar-toggler-padding-y: 0.25rem;
  --bs-navbar-toggler-padding-x: 0.75rem;
  --bs-navbar-toggler-font-size: 1.25rem;
  --bs-navbar-toggler-icon-bg: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'%3e%3cpath stroke='rgba%280, 0, 0, 0.55%29' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e");
  --bs-navbar-toggler-border-color: rgba(0, 0, 0, 0.1);
  --bs-navbar-toggler-border-radius: 0.375rem;
  --bs-navbar-toggler-focus-width: 0.25rem;
  --bs-navbar-toggler-transition: box-shadow 0.15s ease-in-out;
  position: relative;	  position: relative;
  display: flex;	  display: flex;
  flex-wrap: wrap;	  flex-wrap: wrap;
  align-items: center;	  align-items: center;
  justify-content: space-between;	  justify-content: space-between;
  padding-top: 0.5rem;	  padding: var(--bs-navbar-padding-y) var(--bs-navbar-padding-x);
  padding-bottom: 0.5rem;	
}	}
.navbar > .container,	.navbar > .container,
.navbar > .container-fluid,	.navbar > .container-fluid,
@@ -4049,23 +3766,34 @@ textarea.form-control-lg {
  justify-content: space-between;	  justify-content: space-between;
}	}
.navbar-brand {	.navbar-brand {
  padding-top: 0.3125rem;	  padding-top: var(--bs-navbar-brand-padding-y);
  padding-bottom: 0.3125rem;	  padding-bottom: var(--bs-navbar-brand-padding-y);
  margin-right: 1rem;	  margin-right: var(--bs-navbar-brand-margin-end);
  font-size: 1.25rem;	  font-size: var(--bs-navbar-brand-font-size);
  color: var(--bs-navbar-brand-color);
  text-decoration: none;	  text-decoration: none;
  white-space: nowrap;	  white-space: nowrap;
}	}
.navbar-brand:hover, .navbar-brand:focus {
  color: var(--bs-navbar-brand-hover-color);
}

.navbar-nav {	.navbar-nav {
  --bs-nav-link-padding-x: 0;
  --bs-nav-link-padding-y: 0.5rem;
  --bs-nav-link-font-weight: ;
  --bs-nav-link-color: var(--bs-navbar-color);
  --bs-nav-link-hover-color: var(--bs-navbar-hover-color);
  --bs-nav-link-disabled-color: var(--bs-navbar-disabled-color);
  display: flex;	  display: flex;
  flex-direction: column;	  flex-direction: column;
  padding-left: 0;	  padding-left: 0;
  margin-bottom: 0;	  margin-bottom: 0;
  list-style: none;	  list-style: none;
}	}
.navbar-nav .nav-link {	.navbar-nav .show > .nav-link,
  padding-right: 0;	.navbar-nav .nav-link.active {
  padding-left: 0;	  color: var(--bs-navbar-active-color);
}	}
.navbar-nav .dropdown-menu {	.navbar-nav .dropdown-menu {
  position: static;	  position: static;
@@ -4074,6 +3802,12 @@ textarea.form-control-lg {
.navbar-text {	.navbar-text {
  padding-top: 0.5rem;	  padding-top: 0.5rem;
  padding-bottom: 0.5rem;	  padding-bottom: 0.5rem;
  color: var(--bs-navbar-color);
}
.navbar-text a,
.navbar-text a:hover,
.navbar-text a:focus {
  color: var(--bs-navbar-active-color);
}	}


.navbar-collapse {	.navbar-collapse {
@@ -4083,13 +3817,14 @@ textarea.form-control-lg {
}	}


.navbar-toggler {	.navbar-toggler {
  padding: 0.25rem 0.75rem;	  padding: var(--bs-navbar-toggler-padding-y) var(--bs-navbar-toggler-padding-x);
  font-size: 1.25rem;	  font-size: var(--bs-navbar-toggler-font-size);
  line-height: 1;	  line-height: 1;
  color: var(--bs-navbar-color);
  background-color: transparent;	  background-color: transparent;
  border: 1px solid transparent;	  border: var(--bs-border-width) solid var(--bs-navbar-toggler-border-color);
  border-radius: 0.25rem;	  border-radius: var(--bs-navbar-toggler-border-radius);
  transition: box-shadow 0.15s ease-in-out;	  transition: var(--bs-navbar-toggler-transition);
}	}
@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
  .navbar-toggler {	  .navbar-toggler {
@@ -4102,14 +3837,15 @@ textarea.form-control-lg {
.navbar-toggler:focus {	.navbar-toggler:focus {
  text-decoration: none;	  text-decoration: none;
  outline: 0;	  outline: 0;
  box-shadow: 0 0 0 0.25rem;	  box-shadow: 0 0 0 var(--bs-navbar-toggler-focus-width);
}	}


.navbar-toggler-icon {	.navbar-toggler-icon {
  display: inline-block;	  display: inline-block;
  width: 1.5em;	  width: 1.5em;
  height: 1.5em;	  height: 1.5em;
  vertical-align: middle;	  vertical-align: middle;
  background-image: var(--bs-navbar-toggler-icon-bg);
  background-repeat: no-repeat;	  background-repeat: no-repeat;
  background-position: center;	  background-position: center;
  background-size: 100%;	  background-size: 100%;
@@ -4132,8 +3868,8 @@ textarea.form-control-lg {
    position: absolute;	    position: absolute;
  }	  }
  .navbar-expand-sm .navbar-nav .nav-link {	  .navbar-expand-sm .navbar-nav .nav-link {
    padding-right: 0.5rem;	    padding-right: var(--bs-navbar-nav-link-padding-x);
    padding-left: 0.5rem;	    padding-left: var(--bs-navbar-nav-link-padding-x);
  }	  }
  .navbar-expand-sm .navbar-nav-scroll {	  .navbar-expand-sm .navbar-nav-scroll {
    overflow: visible;	    overflow: visible;
@@ -4145,28 +3881,22 @@ textarea.form-control-lg {
  .navbar-expand-sm .navbar-toggler {	  .navbar-expand-sm .navbar-toggler {
    display: none;	    display: none;
  }	  }
  .navbar-expand-sm .offcanvas-header {	
    display: none;	
  }	
  .navbar-expand-sm .offcanvas {	  .navbar-expand-sm .offcanvas {
    position: inherit;	    position: static;
    bottom: 0;	    z-index: auto;
    z-index: 1000;	
    flex-grow: 1;	    flex-grow: 1;
    width: auto !important;
    height: auto !important;
    visibility: visible !important;	    visibility: visible !important;
    background-color: transparent;	    background-color: transparent !important;
    border-right: 0;	    border: 0 !important;
    border-left: 0;	    transform: none !important;
    transition: none;	    transition: none;
    transform: none;	
  }	  }
  .navbar-expand-sm .offcanvas-top,	  .navbar-expand-sm .offcanvas .offcanvas-header {
.navbar-expand-sm .offcanvas-bottom {	    display: none;
    height: auto;	
    border-top: 0;	
    border-bottom: 0;	
  }	  }
  .navbar-expand-sm .offcanvas-body {	  .navbar-expand-sm .offcanvas .offcanvas-body {
    display: flex;	    display: flex;
    flex-grow: 0;	    flex-grow: 0;
    padding: 0;	    padding: 0;
@@ -4185,8 +3915,8 @@ textarea.form-control-lg {
    position: absolute;	    position: absolute;
  }	  }
  .navbar-expand-md .navbar-nav .nav-link {	  .navbar-expand-md .navbar-nav .nav-link {
    padding-right: 0.5rem;	    padding-right: var(--bs-navbar-nav-link-padding-x);
    padding-left: 0.5rem;	    padding-left: var(--bs-navbar-nav-link-padding-x);
  }	  }
  .navbar-expand-md .navbar-nav-scroll {	  .navbar-expand-md .navbar-nav-scroll {
    overflow: visible;	    overflow: visible;
@@ -4198,28 +3928,22 @@ textarea.form-control-lg {
  .navbar-expand-md .navbar-toggler {	  .navbar-expand-md .navbar-toggler {
    display: none;	    display: none;
  }	  }
  .navbar-expand-md .offcanvas-header {	
    display: none;	
  }	
  .navbar-expand-md .offcanvas {	  .navbar-expand-md .offcanvas {
    position: inherit;	    position: static;
    bottom: 0;	    z-index: auto;
    z-index: 1000;	
    flex-grow: 1;	    flex-grow: 1;
    width: auto !important;
    height: auto !important;
    visibility: visible !important;	    visibility: visible !important;
    background-color: transparent;	    background-color: transparent !important;
    border-right: 0;	    border: 0 !important;
    border-left: 0;	    transform: none !important;
    transition: none;	    transition: none;
    transform: none;	
  }	  }
  .navbar-expand-md .offcanvas-top,	  .navbar-expand-md .offcanvas .offcanvas-header {
.navbar-expand-md .offcanvas-bottom {	    display: none;
    height: auto;	
    border-top: 0;	
    border-bottom: 0;	
  }	  }
  .navbar-expand-md .offcanvas-body {	  .navbar-expand-md .offcanvas .offcanvas-body {
    display: flex;	    display: flex;
    flex-grow: 0;	    flex-grow: 0;
    padding: 0;	    padding: 0;
@@ -4238,8 +3962,8 @@ textarea.form-control-lg {
    position: absolute;	    position: absolute;
  }	  }
  .navbar-expand-lg .navbar-nav .nav-link {	  .navbar-expand-lg .navbar-nav .nav-link {
    padding-right: 0.5rem;	    padding-right: var(--bs-navbar-nav-link-padding-x);
    padding-left: 0.5rem;	    padding-left: var(--bs-navbar-nav-link-padding-x);
  }	  }
  .navbar-expand-lg .navbar-nav-scroll {	  .navbar-expand-lg .navbar-nav-scroll {
    overflow: visible;	    overflow: visible;
@@ -4251,28 +3975,22 @@ textarea.form-control-lg {
  .navbar-expand-lg .navbar-toggler {	  .navbar-expand-lg .navbar-toggler {
    display: none;	    display: none;
  }	  }
  .navbar-expand-lg .offcanvas-header {	
    display: none;	
  }	
  .navbar-expand-lg .offcanvas {	  .navbar-expand-lg .offcanvas {
    position: inherit;	    position: static;
    bottom: 0;	    z-index: auto;
    z-index: 1000;	
    flex-grow: 1;	    flex-grow: 1;
    width: auto !important;
    height: auto !important;
    visibility: visible !important;	    visibility: visible !important;
    background-color: transparent;	    background-color: transparent !important;
    border-right: 0;	    border: 0 !important;
    border-left: 0;	    transform: none !important;
    transition: none;	    transition: none;
    transform: none;	
  }	  }
  .navbar-expand-lg .offcanvas-top,	  .navbar-expand-lg .offcanvas .offcanvas-header {
.navbar-expand-lg .offcanvas-bottom {	    display: none;
    height: auto;	
    border-top: 0;	
    border-bottom: 0;	
  }	  }
  .navbar-expand-lg .offcanvas-body {	  .navbar-expand-lg .offcanvas .offcanvas-body {
    display: flex;	    display: flex;
    flex-grow: 0;	    flex-grow: 0;
    padding: 0;	    padding: 0;
@@ -4291,8 +4009,8 @@ textarea.form-control-lg {
    position: absolute;	    position: absolute;
  }	  }
  .navbar-expand-xl .navbar-nav .nav-link {	  .navbar-expand-xl .navbar-nav .nav-link {
    padding-right: 0.5rem;	    padding-right: var(--bs-navbar-nav-link-padding-x);
    padding-left: 0.5rem;	    padding-left: var(--bs-navbar-nav-link-padding-x);
  }	  }
  .navbar-expand-xl .navbar-nav-scroll {	  .navbar-expand-xl .navbar-nav-scroll {
    overflow: visible;	    overflow: visible;
@@ -4304,28 +4022,22 @@ textarea.form-control-lg {
  .navbar-expand-xl .navbar-toggler {	  .navbar-expand-xl .navbar-toggler {
    display: none;	    display: none;
  }	  }
  .navbar-expand-xl .offcanvas-header {	
    display: none;	
  }	
  .navbar-expand-xl .offcanvas {	  .navbar-expand-xl .offcanvas {
    position: inherit;	    position: static;
    bottom: 0;	    z-index: auto;
    z-index: 1000;	
    flex-grow: 1;	    flex-grow: 1;
    width: auto !important;
    height: auto !important;
    visibility: visible !important;	    visibility: visible !important;
    background-color: transparent;	    background-color: transparent !important;
    border-right: 0;	    border: 0 !important;
    border-left: 0;	    transform: none !important;
    transition: none;	    transition: none;
    transform: none;	
  }	  }
  .navbar-expand-xl .offcanvas-top,	  .navbar-expand-xl .offcanvas .offcanvas-header {
.navbar-expand-xl .offcanvas-bottom {	    display: none;
    height: auto;	
    border-top: 0;	
    border-bottom: 0;	
  }	  }
  .navbar-expand-xl .offcanvas-body {	  .navbar-expand-xl .offcanvas .offcanvas-body {
    display: flex;	    display: flex;
    flex-grow: 0;	    flex-grow: 0;
    padding: 0;	    padding: 0;
@@ -4344,8 +4056,8 @@ textarea.form-control-lg {
    position: absolute;	    position: absolute;
  }	  }
  .navbar-expand-xxl .navbar-nav .nav-link {	  .navbar-expand-xxl .navbar-nav .nav-link {
    padding-right: 0.5rem;	    padding-right: var(--bs-navbar-nav-link-padding-x);
    padding-left: 0.5rem;	    padding-left: var(--bs-navbar-nav-link-padding-x);
  }	  }
  .navbar-expand-xxl .navbar-nav-scroll {	  .navbar-expand-xxl .navbar-nav-scroll {
    overflow: visible;	    overflow: visible;
@@ -4357,28 +4069,22 @@ textarea.form-control-lg {
  .navbar-expand-xxl .navbar-toggler {	  .navbar-expand-xxl .navbar-toggler {
    display: none;	    display: none;
  }	  }
  .navbar-expand-xxl .offcanvas-header {	
    display: none;	
  }	
  .navbar-expand-xxl .offcanvas {	  .navbar-expand-xxl .offcanvas {
    position: inherit;	    position: static;
    bottom: 0;	    z-index: auto;
    z-index: 1000;	
    flex-grow: 1;	    flex-grow: 1;
    width: auto !important;
    height: auto !important;
    visibility: visible !important;	    visibility: visible !important;
    background-color: transparent;	    background-color: transparent !important;
    border-right: 0;	    border: 0 !important;
    border-left: 0;	    transform: none !important;
    transition: none;	    transition: none;
    transform: none;	
  }	  }
  .navbar-expand-xxl .offcanvas-top,	  .navbar-expand-xxl .offcanvas .offcanvas-header {
.navbar-expand-xxl .offcanvas-bottom {	    display: none;
    height: auto;	
    border-top: 0;	
    border-bottom: 0;	
  }	  }
  .navbar-expand-xxl .offcanvas-body {	  .navbar-expand-xxl .offcanvas .offcanvas-body {
    display: flex;	    display: flex;
    flex-grow: 0;	    flex-grow: 0;
    padding: 0;	    padding: 0;
@@ -4396,8 +4102,8 @@ textarea.form-control-lg {
  position: absolute;	  position: absolute;
}	}
.navbar-expand .navbar-nav .nav-link {	.navbar-expand .navbar-nav .nav-link {
  padding-right: 0.5rem;	  padding-right: var(--bs-navbar-nav-link-padding-x);
  padding-left: 0.5rem;	  padding-left: var(--bs-navbar-nav-link-padding-x);
}	}
.navbar-expand .navbar-nav-scroll {	.navbar-expand .navbar-nav-scroll {
  overflow: visible;	  overflow: visible;
@@ -4409,114 +4115,67 @@ textarea.form-control-lg {
.navbar-expand .navbar-toggler {	.navbar-expand .navbar-toggler {
  display: none;	  display: none;
}	}
.navbar-expand .offcanvas-header {	
  display: none;	
}	
.navbar-expand .offcanvas {	.navbar-expand .offcanvas {
  position: inherit;	  position: static;
  bottom: 0;	  z-index: auto;
  z-index: 1000;	
  flex-grow: 1;	  flex-grow: 1;
  width: auto !important;
  height: auto !important;
  visibility: visible !important;	  visibility: visible !important;
  background-color: transparent;	  background-color: transparent !important;
  border-right: 0;	  border: 0 !important;
  border-left: 0;	  transform: none !important;
  transition: none;	  transition: none;
  transform: none;	
}	}
.navbar-expand .offcanvas-top,	.navbar-expand .offcanvas .offcanvas-header {
.navbar-expand .offcanvas-bottom {	  display: none;
  height: auto;	
  border-top: 0;	
  border-bottom: 0;	
}	}
.navbar-expand .offcanvas-body {	.navbar-expand .offcanvas .offcanvas-body {
  display: flex;	  display: flex;
  flex-grow: 0;	  flex-grow: 0;
  padding: 0;	  padding: 0;
  overflow-y: visible;	  overflow-y: visible;
}	}


.navbar-light .navbar-brand {	.navbar-dark {
  color: rgba(0, 0, 0, 0.9);	  --bs-navbar-color: rgba(255, 255, 255, 0.55);
}	  --bs-navbar-hover-color: rgba(255, 255, 255, 0.75);
.navbar-light .navbar-brand:hover, .navbar-light .navbar-brand:focus {	  --bs-navbar-disabled-color: rgba(255, 255, 255, 0.25);
  color: rgba(0, 0, 0, 0.9);	  --bs-navbar-active-color: #fff;
}	  --bs-navbar-brand-color: #fff;
.navbar-light .navbar-nav .nav-link {	  --bs-navbar-brand-hover-color: #fff;
  color: rgba(0, 0, 0, 0.55);	  --bs-navbar-toggler-border-color: rgba(255, 255, 255, 0.1);
}	  --bs-navbar-toggler-icon-bg: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'%3e%3cpath stroke='rgba%28255, 255, 255, 0.55%29' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e");
.navbar-light .navbar-nav .nav-link:hover, .navbar-light .navbar-nav .nav-link:focus {	
  color: rgba(0, 0, 0, 0.7);	
}	
.navbar-light .navbar-nav .nav-link.disabled {	
  color: rgba(0, 0, 0, 0.3);	
}	
.navbar-light .navbar-nav .show > .nav-link,	
.navbar-light .navbar-nav .nav-link.active {	
  color: rgba(0, 0, 0, 0.9);	
}	
.navbar-light .navbar-toggler {	
  color: rgba(0, 0, 0, 0.55);	
  border-color: rgba(0, 0, 0, 0.1);	
}	
.navbar-light .navbar-toggler-icon {	
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'%3e%3cpath stroke='rgba%280, 0, 0, 0.55%29' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e");	
}	
.navbar-light .navbar-text {	
  color: rgba(0, 0, 0, 0.55);	
}	
.navbar-light .navbar-text a,	
.navbar-light .navbar-text a:hover,	
.navbar-light .navbar-text a:focus {	
  color: rgba(0, 0, 0, 0.9);	
}	

.navbar-dark .navbar-brand {	
  color: #fff;	
}	
.navbar-dark .navbar-brand:hover, .navbar-dark .navbar-brand:focus {	
  color: #fff;	
}	
.navbar-dark .navbar-nav .nav-link {	
  color: rgba(255, 255, 255, 0.55);	
}	
.navbar-dark .navbar-nav .nav-link:hover, .navbar-dark .navbar-nav .nav-link:focus {	
  color: rgba(255, 255, 255, 0.75);	
}	
.navbar-dark .navbar-nav .nav-link.disabled {	
  color: rgba(255, 255, 255, 0.25);	
}	
.navbar-dark .navbar-nav .show > .nav-link,	
.navbar-dark .navbar-nav .nav-link.active {	
  color: #fff;	
}	
.navbar-dark .navbar-toggler {	
  color: rgba(255, 255, 255, 0.55);	
  border-color: rgba(255, 255, 255, 0.1);	
}	
.navbar-dark .navbar-toggler-icon {	
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'%3e%3cpath stroke='rgba%28255, 255, 255, 0.55%29' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e");	
}	
.navbar-dark .navbar-text {	
  color: rgba(255, 255, 255, 0.55);	
}	
.navbar-dark .navbar-text a,	
.navbar-dark .navbar-text a:hover,	
.navbar-dark .navbar-text a:focus {	
  color: #fff;	
}	}


.card {	.card {
  --bs-card-spacer-y: 1rem;
  --bs-card-spacer-x: 1rem;
  --bs-card-title-spacer-y: 0.5rem;
  --bs-card-border-width: 1px;
  --bs-card-border-color: var(--bs-border-color-translucent);
  --bs-card-border-radius: 0.375rem;
  --bs-card-box-shadow: ;
  --bs-card-inner-border-radius: calc(0.375rem - 1px);
  --bs-card-cap-padding-y: 0.5rem;
  --bs-card-cap-padding-x: 1rem;
  --bs-card-cap-bg: rgba(0, 0, 0, 0.03);
  --bs-card-cap-color: ;
  --bs-card-height: ;
  --bs-card-color: ;
  --bs-card-bg: #fff;
  --bs-card-img-overlay-padding: 1rem;
  --bs-card-group-margin: 0.75rem;
  position: relative;	  position: relative;
  display: flex;	  display: flex;
  flex-direction: column;	  flex-direction: column;
  min-width: 0;	  min-width: 0;
  height: var(--bs-card-height);
  word-wrap: break-word;	  word-wrap: break-word;
  background-color: #fff;	  background-color: var(--bs-card-bg);
  background-clip: border-box;	  background-clip: border-box;
  border: 1px solid rgba(0, 0, 0, 0.125);	  border: var(--bs-card-border-width) solid var(--bs-card-border-color);
  border-radius: 0.25rem;	  border-radius: var(--bs-card-border-radius);
}	}
.card > hr {	.card > hr {
  margin-right: 0;	  margin-right: 0;
@@ -4528,13 +4187,13 @@ textarea.form-control-lg {
}	}
.card > .list-group:first-child {	.card > .list-group:first-child {
  border-top-width: 0;	  border-top-width: 0;
  border-top-left-radius: calc(0.25rem - 1px);	  border-top-left-radius: var(--bs-card-inner-border-radius);
  border-top-right-radius: calc(0.25rem - 1px);	  border-top-right-radius: var(--bs-card-inner-border-radius);
}	}
.card > .list-group:last-child {	.card > .list-group:last-child {
  border-bottom-width: 0;	  border-bottom-width: 0;
  border-bottom-right-radius: calc(0.25rem - 1px);	  border-bottom-right-radius: var(--bs-card-inner-border-radius);
  border-bottom-left-radius: calc(0.25rem - 1px);	  border-bottom-left-radius: var(--bs-card-inner-border-radius);
}	}
.card > .card-header + .list-group,	.card > .card-header + .list-group,
.card > .list-group + .card-footer {	.card > .list-group + .card-footer {
@@ -4543,15 +4202,16 @@ textarea.form-control-lg {


.card-body {	.card-body {
  flex: 1 1 auto;	  flex: 1 1 auto;
  padding: 1rem 1rem;	  padding: var(--bs-card-spacer-y) var(--bs-card-spacer-x);
  color: var(--bs-card-color);
}	}


.card-title {	.card-title {
  margin-bottom: 0.5rem;	  margin-bottom: var(--bs-card-title-spacer-y);
}	}


.card-subtitle {	.card-subtitle {
  margin-top: -0.25rem;	  margin-top: calc(-0.5 * var(--bs-card-title-spacer-y));
  margin-bottom: 0;	  margin-bottom: 0;
}	}


@@ -4560,38 +4220,44 @@ textarea.form-control-lg {
}	}


.card-link + .card-link {	.card-link + .card-link {
  margin-left: 1rem;	  margin-left: var(--bs-card-spacer-x);
}	}


.card-header {	.card-header {
  padding: 0.5rem 1rem;	  padding: var(--bs-card-cap-padding-y) var(--bs-card-cap-padding-x);
  margin-bottom: 0;	  margin-bottom: 0;
  background-color: rgba(0, 0, 0, 0.03);	  color: var(--bs-card-cap-color);
  border-bottom: 1px solid rgba(0, 0, 0, 0.125);	  background-color: var(--bs-card-cap-bg);
  border-bottom: var(--bs-card-border-width) solid var(--bs-card-border-color);
}	}
.card-header:first-child {	.card-header:first-child {
  border-radius: calc(0.25rem - 1px) calc(0.25rem - 1px) 0 0;	  border-radius: var(--bs-card-inner-border-radius) var(--bs-card-inner-border-radius) 0 0;
}	}


.card-footer {	.card-footer {
  padding: 0.5rem 1rem;	  padding: var(--bs-card-cap-padding-y) var(--bs-card-cap-padding-x);
  background-color: rgba(0, 0, 0, 0.03);	  color: var(--bs-card-cap-color);
  border-top: 1px solid rgba(0, 0, 0, 0.125);	  background-color: var(--bs-card-cap-bg);
  border-top: var(--bs-card-border-width) solid var(--bs-card-border-color);
}	}
.card-footer:last-child {	.card-footer:last-child {
  border-radius: 0 0 calc(0.25rem - 1px) calc(0.25rem - 1px);	  border-radius: 0 0 var(--bs-card-inner-border-radius) var(--bs-card-inner-border-radius);
}	}


.card-header-tabs {	.card-header-tabs {
  margin-right: -0.5rem;	  margin-right: calc(-0.5 * var(--bs-card-cap-padding-x));
  margin-bottom: -0.5rem;	  margin-bottom: calc(-1 * var(--bs-card-cap-padding-y));
  margin-left: -0.5rem;	  margin-left: calc(-0.5 * var(--bs-card-cap-padding-x));
  border-bottom: 0;	  border-bottom: 0;
}	}
.card-header-tabs .nav-link.active {
  background-color: var(--bs-card-bg);
  border-bottom-color: var(--bs-card-bg);
}


.card-header-pills {	.card-header-pills {
  margin-right: -0.5rem;	  margin-right: calc(-0.5 * var(--bs-card-cap-padding-x));
  margin-left: -0.5rem;	  margin-left: calc(-0.5 * var(--bs-card-cap-padding-x));
}	}


.card-img-overlay {	.card-img-overlay {
@@ -4600,8 +4266,8 @@ textarea.form-control-lg {
  right: 0;	  right: 0;
  bottom: 0;	  bottom: 0;
  left: 0;	  left: 0;
  padding: 1rem;	  padding: var(--bs-card-img-overlay-padding);
  border-radius: calc(0.25rem - 1px);	  border-radius: var(--bs-card-inner-border-radius);
}	}


.card-img,	.card-img,
@@ -4612,18 +4278,18 @@ textarea.form-control-lg {


.card-img,	.card-img,
.card-img-top {	.card-img-top {
  border-top-left-radius: calc(0.25rem - 1px);	  border-top-left-radius: var(--bs-card-inner-border-radius);
  border-top-right-radius: calc(0.25rem - 1px);	  border-top-right-radius: var(--bs-card-inner-border-radius);
}	}


.card-img,	.card-img,
.card-img-bottom {	.card-img-bottom {
  border-bottom-right-radius: calc(0.25rem - 1px);	  border-bottom-right-radius: var(--bs-card-inner-border-radius);
  border-bottom-left-radius: calc(0.25rem - 1px);	  border-bottom-left-radius: var(--bs-card-inner-border-radius);
}	}


.card-group > .card {	.card-group > .card {
  margin-bottom: 0.75rem;	  margin-bottom: var(--bs-card-group-margin);
}	}
@media (min-width: 576px) {	@media (min-width: 576px) {
  .card-group {	  .card-group {
@@ -4643,66 +4309,91 @@ textarea.form-control-lg {
    border-bottom-right-radius: 0;	    border-bottom-right-radius: 0;
  }	  }
  .card-group > .card:not(:last-child) .card-img-top,	  .card-group > .card:not(:last-child) .card-img-top,
.card-group > .card:not(:last-child) .card-header {	  .card-group > .card:not(:last-child) .card-header {
    border-top-right-radius: 0;	    border-top-right-radius: 0;
  }	  }
  .card-group > .card:not(:last-child) .card-img-bottom,	  .card-group > .card:not(:last-child) .card-img-bottom,
.card-group > .card:not(:last-child) .card-footer {	  .card-group > .card:not(:last-child) .card-footer {
    border-bottom-right-radius: 0;	    border-bottom-right-radius: 0;
  }	  }
  .card-group > .card:not(:first-child) {	  .card-group > .card:not(:first-child) {
    border-top-left-radius: 0;	    border-top-left-radius: 0;
    border-bottom-left-radius: 0;	    border-bottom-left-radius: 0;
  }	  }
  .card-group > .card:not(:first-child) .card-img-top,	  .card-group > .card:not(:first-child) .card-img-top,
.card-group > .card:not(:first-child) .card-header {	  .card-group > .card:not(:first-child) .card-header {
    border-top-left-radius: 0;	    border-top-left-radius: 0;
  }	  }
  .card-group > .card:not(:first-child) .card-img-bottom,	  .card-group > .card:not(:first-child) .card-img-bottom,
.card-group > .card:not(:first-child) .card-footer {	  .card-group > .card:not(:first-child) .card-footer {
    border-bottom-left-radius: 0;	    border-bottom-left-radius: 0;
  }	  }
}	}


.accordion {
  --bs-accordion-color: #212529;
  --bs-accordion-bg: #fff;
  --bs-accordion-transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out, border-radius 0.15s ease;
  --bs-accordion-border-color: var(--bs-border-color);
  --bs-accordion-border-width: 1px;
  --bs-accordion-border-radius: 0.375rem;
  --bs-accordion-inner-border-radius: calc(0.375rem - 1px);
  --bs-accordion-btn-padding-x: 1.25rem;
  --bs-accordion-btn-padding-y: 1rem;
  --bs-accordion-btn-color: #212529;
  --bs-accordion-btn-bg: var(--bs-accordion-bg);
  --bs-accordion-btn-icon: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16' fill='%23212529'%3e%3cpath fill-rule='evenodd' d='M1.646 4.646a.5.5 0 0 1 .708 0L8 10.293l5.646-5.647a.5.5 0 0 1 .708.708l-6 6a.5.5 0 0 1-.708 0l-6-6a.5.5 0 0 1 0-.708z'/%3e%3c/svg%3e");
  --bs-accordion-btn-icon-width: 1.25rem;
  --bs-accordion-btn-icon-transform: rotate(-180deg);
  --bs-accordion-btn-icon-transition: transform 0.2s ease-in-out;
  --bs-accordion-btn-active-icon: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16' fill='%230c63e4'%3e%3cpath fill-rule='evenodd' d='M1.646 4.646a.5.5 0 0 1 .708 0L8 10.293l5.646-5.647a.5.5 0 0 1 .708.708l-6 6a.5.5 0 0 1-.708 0l-6-6a.5.5 0 0 1 0-.708z'/%3e%3c/svg%3e");
  --bs-accordion-btn-focus-border-color: #86b7fe;
  --bs-accordion-btn-focus-box-shadow: 0 0 0 0.25rem rgba(13, 110, 253, 0.25);
  --bs-accordion-body-padding-x: 1.25rem;
  --bs-accordion-body-padding-y: 1rem;
  --bs-accordion-active-color: #0c63e4;
  --bs-accordion-active-bg: #e7f1ff;
}

.accordion-button {	.accordion-button {
  position: relative;	  position: relative;
  display: flex;	  display: flex;
  align-items: center;	  align-items: center;
  width: 100%;	  width: 100%;
  padding: 1rem 1.25rem;	  padding: var(--bs-accordion-btn-padding-y) var(--bs-accordion-btn-padding-x);
  font-size: 1rem;	  font-size: 1rem;
  color: #212529;	  color: var(--bs-accordion-btn-color);
  text-align: left;	  text-align: left;
  background-color: #fff;	  background-color: var(--bs-accordion-btn-bg);
  border: 0;	  border: 0;
  border-radius: 0;	  border-radius: 0;
  overflow-anchor: none;	  overflow-anchor: none;
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out, border-radius 0.15s ease;	  transition: var(--bs-accordion-transition);
}	}
@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
  .accordion-button {	  .accordion-button {
    transition: none;	    transition: none;
  }	  }
}	}
.accordion-button:not(.collapsed) {	.accordion-button:not(.collapsed) {
  color: #0c63e4;	  color: var(--bs-accordion-active-color);
  background-color: #e7f1ff;	  background-color: var(--bs-accordion-active-bg);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.125);	  box-shadow: inset 0 calc(-1 * var(--bs-accordion-border-width)) 0 var(--bs-accordion-border-color);
}	}
.accordion-button:not(.collapsed)::after {	.accordion-button:not(.collapsed)::after {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16' fill='%230c63e4'%3e%3cpath fill-rule='evenodd' d='M1.646 4.646a.5.5 0 0 1 .708 0L8 10.293l5.646-5.647a.5.5 0 0 1 .708.708l-6 6a.5.5 0 0 1-.708 0l-6-6a.5.5 0 0 1 0-.708z'/%3e%3c/svg%3e");	  background-image: var(--bs-accordion-btn-active-icon);
  transform: rotate(-180deg);	  transform: var(--bs-accordion-btn-icon-transform);
}	}
.accordion-button::after {	.accordion-button::after {
  flex-shrink: 0;	  flex-shrink: 0;
  width: 1.25rem;	  width: var(--bs-accordion-btn-icon-width);
  height: 1.25rem;	  height: var(--bs-accordion-btn-icon-width);
  margin-left: auto;	  margin-left: auto;
  content: "";	  content: "";
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16' fill='%23212529'%3e%3cpath fill-rule='evenodd' d='M1.646 4.646a.5.5 0 0 1 .708 0L8 10.293l5.646-5.647a.5.5 0 0 1 .708.708l-6 6a.5.5 0 0 1-.708 0l-6-6a.5.5 0 0 1 0-.708z'/%3e%3c/svg%3e");	  background-image: var(--bs-accordion-btn-icon);
  background-repeat: no-repeat;	  background-repeat: no-repeat;
  background-size: 1.25rem;	  background-size: var(--bs-accordion-btn-icon-width);
  transition: transform 0.2s ease-in-out;	  transition: var(--bs-accordion-btn-icon-transition);
}	}
@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
  .accordion-button::after {	  .accordion-button::after {
@@ -4714,45 +4405,46 @@ textarea.form-control-lg {
}	}
.accordion-button:focus {	.accordion-button:focus {
  z-index: 3;	  z-index: 3;
  border-color: #86b7fe;	  border-color: var(--bs-accordion-btn-focus-border-color);
  outline: 0;	  outline: 0;
  box-shadow: 0 0 0 0.25rem rgba(13, 110, 253, 0.25);	  box-shadow: var(--bs-accordion-btn-focus-box-shadow);
}	}


.accordion-header {	.accordion-header {
  margin-bottom: 0;	  margin-bottom: 0;
}	}


.accordion-item {	.accordion-item {
  background-color: #fff;	  color: var(--bs-accordion-color);
  border: 1px solid rgba(0, 0, 0, 0.125);	  background-color: var(--bs-accordion-bg);
  border: var(--bs-accordion-border-width) solid var(--bs-accordion-border-color);
}	}
.accordion-item:first-of-type {	.accordion-item:first-of-type {
  border-top-left-radius: 0.25rem;	  border-top-left-radius: var(--bs-accordion-border-radius);
  border-top-right-radius: 0.25rem;	  border-top-right-radius: var(--bs-accordion-border-radius);
}	}
.accordion-item:first-of-type .accordion-button {	.accordion-item:first-of-type .accordion-button {
  border-top-left-radius: calc(0.25rem - 1px);	  border-top-left-radius: var(--bs-accordion-inner-border-radius);
  border-top-right-radius: calc(0.25rem - 1px);	  border-top-right-radius: var(--bs-accordion-inner-border-radius);
}	}
.accordion-item:not(:first-of-type) {	.accordion-item:not(:first-of-type) {
  border-top: 0;	  border-top: 0;
}	}
.accordion-item:last-of-type {	.accordion-item:last-of-type {
  border-bottom-right-radius: 0.25rem;	  border-bottom-right-radius: var(--bs-accordion-border-radius);
  border-bottom-left-radius: 0.25rem;	  border-bottom-left-radius: var(--bs-accordion-border-radius);
}	}
.accordion-item:last-of-type .accordion-button.collapsed {	.accordion-item:last-of-type .accordion-button.collapsed {
  border-bottom-right-radius: calc(0.25rem - 1px);	  border-bottom-right-radius: var(--bs-accordion-inner-border-radius);
  border-bottom-left-radius: calc(0.25rem - 1px);	  border-bottom-left-radius: var(--bs-accordion-inner-border-radius);
}	}
.accordion-item:last-of-type .accordion-collapse {	.accordion-item:last-of-type .accordion-collapse {
  border-bottom-right-radius: 0.25rem;	  border-bottom-right-radius: var(--bs-accordion-border-radius);
  border-bottom-left-radius: 0.25rem;	  border-bottom-left-radius: var(--bs-accordion-border-radius);
}	}


.accordion-body {	.accordion-body {
  padding: 1rem 1.25rem;	  padding: var(--bs-accordion-body-padding-y) var(--bs-accordion-body-padding-x);
}	}


.accordion-flush .accordion-collapse {	.accordion-flush .accordion-collapse {
@@ -4769,32 +4461,63 @@ textarea.form-control-lg {
.accordion-flush .accordion-item:last-child {	.accordion-flush .accordion-item:last-child {
  border-bottom: 0;	  border-bottom: 0;
}	}
.accordion-flush .accordion-item .accordion-button {	.accordion-flush .accordion-item .accordion-button, .accordion-flush .accordion-item .accordion-button.collapsed {
  border-radius: 0;	  border-radius: 0;
}	}


.breadcrumb {	.breadcrumb {
  --bs-breadcrumb-padding-x: 0;
  --bs-breadcrumb-padding-y: 0;
  --bs-breadcrumb-margin-bottom: 1rem;
  --bs-breadcrumb-bg: ;
  --bs-breadcrumb-border-radius: ;
  --bs-breadcrumb-divider-color: #6c757d;
  --bs-breadcrumb-item-padding-x: 0.5rem;
  --bs-breadcrumb-item-active-color: #6c757d;
  display: flex;	  display: flex;
  flex-wrap: wrap;	  flex-wrap: wrap;
  padding: 0 0;	  padding: var(--bs-breadcrumb-padding-y) var(--bs-breadcrumb-padding-x);
  margin-bottom: 1rem;	  margin-bottom: var(--bs-breadcrumb-margin-bottom);
  font-size: var(--bs-breadcrumb-font-size);
  list-style: none;	  list-style: none;
  background-color: var(--bs-breadcrumb-bg);
  border-radius: var(--bs-breadcrumb-border-radius);
}	}


.breadcrumb-item + .breadcrumb-item {	.breadcrumb-item + .breadcrumb-item {
  padding-left: 0.5rem;	  padding-left: var(--bs-breadcrumb-item-padding-x);
}	}
.breadcrumb-item + .breadcrumb-item::before {	.breadcrumb-item + .breadcrumb-item::before {
  float: left;	  float: left;
  padding-right: 0.5rem;	  padding-right: var(--bs-breadcrumb-item-padding-x);
  color: #6c757d;	  color: var(--bs-breadcrumb-divider-color);
  content: var(--bs-breadcrumb-divider, "/") /* rtl: var(--bs-breadcrumb-divider, "/") */;	  content: var(--bs-breadcrumb-divider, "/") /* rtl: var(--bs-breadcrumb-divider, "/") */;
}	}
.breadcrumb-item.active {	.breadcrumb-item.active {
  color: #6c757d;	  color: var(--bs-breadcrumb-item-active-color);
}	}


.pagination {	.pagination {
  --bs-pagination-padding-x: 0.75rem;
  --bs-pagination-padding-y: 0.375rem;
  --bs-pagination-font-size: 1rem;
  --bs-pagination-color: var(--bs-link-color);
  --bs-pagination-bg: #fff;
  --bs-pagination-border-width: 1px;
  --bs-pagination-border-color: #dee2e6;
  --bs-pagination-border-radius: 0.375rem;
  --bs-pagination-hover-color: var(--bs-link-hover-color);
  --bs-pagination-hover-bg: #e9ecef;
  --bs-pagination-hover-border-color: #dee2e6;
  --bs-pagination-focus-color: var(--bs-link-hover-color);
  --bs-pagination-focus-bg: #e9ecef;
  --bs-pagination-focus-box-shadow: 0 0 0 0.25rem rgba(13, 110, 253, 0.25);
  --bs-pagination-active-color: #fff;
  --bs-pagination-active-bg: #0d6efd;
  --bs-pagination-active-border-color: #0d6efd;
  --bs-pagination-disabled-color: #6c757d;
  --bs-pagination-disabled-bg: #fff;
  --bs-pagination-disabled-border-color: #dee2e6;
  display: flex;	  display: flex;
  padding-left: 0;	  padding-left: 0;
  list-style: none;	  list-style: none;
@@ -4803,10 +4526,12 @@ textarea.form-control-lg {
.page-link {	.page-link {
  position: relative;	  position: relative;
  display: block;	  display: block;
  color: #0d6efd;	  padding: var(--bs-pagination-padding-y) var(--bs-pagination-padding-x);
  font-size: var(--bs-pagination-font-size);
  color: var(--bs-pagination-color);
  text-decoration: none;	  text-decoration: none;
  background-color: #fff;	  background-color: var(--bs-pagination-bg);
  border: 1px solid #dee2e6;	  border: var(--bs-pagination-border-width) solid var(--bs-pagination-border-color);
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;	  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
}	}
@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
@@ -4816,84 +4541,73 @@ textarea.form-control-lg {
}	}
.page-link:hover {	.page-link:hover {
  z-index: 2;	  z-index: 2;
  color: #0a58ca;	  color: var(--bs-pagination-hover-color);
  background-color: #e9ecef;	  background-color: var(--bs-pagination-hover-bg);
  border-color: #dee2e6;	  border-color: var(--bs-pagination-hover-border-color);
}	}
.page-link:focus {	.page-link:focus {
  z-index: 3;	  z-index: 3;
  color: #0a58ca;	  color: var(--bs-pagination-focus-color);
  background-color: #e9ecef;	  background-color: var(--bs-pagination-focus-bg);
  outline: 0;	  outline: 0;
  box-shadow: 0 0 0 0.25rem rgba(13, 110, 253, 0.25);	  box-shadow: var(--bs-pagination-focus-box-shadow);
}	

.page-item:not(:first-child) .page-link {	
  margin-left: -1px;	
}	}
.page-item.active .page-link {	.page-link.active, .active > .page-link {
  z-index: 3;	  z-index: 3;
  color: #fff;	  color: var(--bs-pagination-active-color);
  background-color: #0d6efd;	  background-color: var(--bs-pagination-active-bg);
  border-color: #0d6efd;	  border-color: var(--bs-pagination-active-border-color);
}	}
.page-item.disabled .page-link {	.page-link.disabled, .disabled > .page-link {
  color: #6c757d;	  color: var(--bs-pagination-disabled-color);
  pointer-events: none;	  pointer-events: none;
  background-color: #fff;	  background-color: var(--bs-pagination-disabled-bg);
  border-color: #dee2e6;	  border-color: var(--bs-pagination-disabled-border-color);
}	}


.page-link {	.page-item:not(:first-child) .page-link {
  padding: 0.375rem 0.75rem;	  margin-left: -1px;
}	}

.page-item:first-child .page-link {	.page-item:first-child .page-link {
  border-top-left-radius: 0.25rem;	  border-top-left-radius: var(--bs-pagination-border-radius);
  border-bottom-left-radius: 0.25rem;	  border-bottom-left-radius: var(--bs-pagination-border-radius);
}	}
.page-item:last-child .page-link {	.page-item:last-child .page-link {
  border-top-right-radius: 0.25rem;	  border-top-right-radius: var(--bs-pagination-border-radius);
  border-bottom-right-radius: 0.25rem;	  border-bottom-right-radius: var(--bs-pagination-border-radius);
}	}


.pagination-lg .page-link {	.pagination-lg {
  padding: 0.75rem 1.5rem;	  --bs-pagination-padding-x: 1.5rem;
  font-size: 1.25rem;	  --bs-pagination-padding-y: 0.75rem;
}	  --bs-pagination-font-size: 1.25rem;
.pagination-lg .page-item:first-child .page-link {	  --bs-pagination-border-radius: 0.5rem;
  border-top-left-radius: 0.3rem;	
  border-bottom-left-radius: 0.3rem;	
}	
.pagination-lg .page-item:last-child .page-link {	
  border-top-right-radius: 0.3rem;	
  border-bottom-right-radius: 0.3rem;	
}	}


.pagination-sm .page-link {	.pagination-sm {
  padding: 0.25rem 0.5rem;	  --bs-pagination-padding-x: 0.5rem;
  font-size: 0.875rem;	  --bs-pagination-padding-y: 0.25rem;
}	  --bs-pagination-font-size: 0.875rem;
.pagination-sm .page-item:first-child .page-link {	  --bs-pagination-border-radius: 0.25rem;
  border-top-left-radius: 0.2rem;	
  border-bottom-left-radius: 0.2rem;	
}	
.pagination-sm .page-item:last-child .page-link {	
  border-top-right-radius: 0.2rem;	
  border-bottom-right-radius: 0.2rem;	
}	}


.badge {	.badge {
  --bs-badge-padding-x: 0.65em;
  --bs-badge-padding-y: 0.35em;
  --bs-badge-font-size: 0.75em;
  --bs-badge-font-weight: 700;
  --bs-badge-color: #fff;
  --bs-badge-border-radius: 0.375rem;
  display: inline-block;	  display: inline-block;
  padding: 0.35em 0.65em;	  padding: var(--bs-badge-padding-y) var(--bs-badge-padding-x);
  font-size: 0.75em;	  font-size: var(--bs-badge-font-size);
  font-weight: 700;	  font-weight: var(--bs-badge-font-weight);
  line-height: 1;	  line-height: 1;
  color: #fff;	  color: var(--bs-badge-color);
  text-align: center;	  text-align: center;
  white-space: nowrap;	  white-space: nowrap;
  vertical-align: baseline;	  vertical-align: baseline;
  border-radius: 0.25rem;	  border-radius: var(--bs-badge-border-radius);
}	}
.badge:empty {	.badge:empty {
  display: none;	  display: none;
@@ -4905,11 +4619,21 @@ textarea.form-control-lg {
}	}


.alert {	.alert {
  --bs-alert-bg: transparent;
  --bs-alert-padding-x: 1rem;
  --bs-alert-padding-y: 1rem;
  --bs-alert-margin-bottom: 1rem;
  --bs-alert-color: inherit;
  --bs-alert-border-color: transparent;
  --bs-alert-border: 1px solid var(--bs-alert-border-color);
  --bs-alert-border-radius: 0.375rem;
  position: relative;	  position: relative;
  padding: 1rem 1rem;	  padding: var(--bs-alert-padding-y) var(--bs-alert-padding-x);
  margin-bottom: 1rem;	  margin-bottom: var(--bs-alert-margin-bottom);
  border: 1px solid transparent;	  color: var(--bs-alert-color);
  border-radius: 0.25rem;	  background-color: var(--bs-alert-bg);
  border: var(--bs-alert-border);
  border-radius: var(--bs-alert-border-radius);
}	}


.alert-heading {	.alert-heading {
@@ -4932,107 +4656,109 @@ textarea.form-control-lg {
}	}


.alert-primary {	.alert-primary {
  color: #084298;	  --bs-alert-color: #084298;
  background-color: #cfe2ff;	  --bs-alert-bg: #cfe2ff;
  border-color: #b6d4fe;	  --bs-alert-border-color: #b6d4fe;
}	}
.alert-primary .alert-link {	.alert-primary .alert-link {
  color: #06357a;	  color: #06357a;
}	}


.alert-secondary {	.alert-secondary {
  color: #41464b;	  --bs-alert-color: #41464b;
  background-color: #e2e3e5;	  --bs-alert-bg: #e2e3e5;
  border-color: #d3d6d8;	  --bs-alert-border-color: #d3d6d8;
}	}
.alert-secondary .alert-link {	.alert-secondary .alert-link {
  color: #34383c;	  color: #34383c;
}	}


.alert-success {	.alert-success {
  color: #0f5132;	  --bs-alert-color: #0f5132;
  background-color: #d1e7dd;	  --bs-alert-bg: #d1e7dd;
  border-color: #badbcc;	  --bs-alert-border-color: #badbcc;
}	}
.alert-success .alert-link {	.alert-success .alert-link {
  color: #0c4128;	  color: #0c4128;
}	}


.alert-info {	.alert-info {
  color: #055160;	  --bs-alert-color: #055160;
  background-color: #cff4fc;	  --bs-alert-bg: #cff4fc;
  border-color: #b6effb;	  --bs-alert-border-color: #b6effb;
}	}
.alert-info .alert-link {	.alert-info .alert-link {
  color: #04414d;	  color: #04414d;
}	}


.alert-warning {	.alert-warning {
  color: #664d03;	  --bs-alert-color: #664d03;
  background-color: #fff3cd;	  --bs-alert-bg: #fff3cd;
  border-color: #ffecb5;	  --bs-alert-border-color: #ffecb5;
}	}
.alert-warning .alert-link {	.alert-warning .alert-link {
  color: #523e02;	  color: #523e02;
}	}


.alert-danger {	.alert-danger {
  color: #842029;	  --bs-alert-color: #842029;
  background-color: #f8d7da;	  --bs-alert-bg: #f8d7da;
  border-color: #f5c2c7;	  --bs-alert-border-color: #f5c2c7;
}	}
.alert-danger .alert-link {	.alert-danger .alert-link {
  color: #6a1a21;	  color: #6a1a21;
}	}


.alert-light {	.alert-light {
  color: #636464;	  --bs-alert-color: #636464;
  background-color: #fefefe;	  --bs-alert-bg: #fefefe;
  border-color: #fdfdfe;	  --bs-alert-border-color: #fdfdfe;
}	}
.alert-light .alert-link {	.alert-light .alert-link {
  color: #4f5050;	  color: #4f5050;
}	}


.alert-dark {	.alert-dark {
  color: #141619;	  --bs-alert-color: #141619;
  background-color: #d3d3d4;	  --bs-alert-bg: #d3d3d4;
  border-color: #bcbebf;	  --bs-alert-border-color: #bcbebf;
}	}
.alert-dark .alert-link {	.alert-dark .alert-link {
  color: #101214;	  color: #101214;
}	}


@-webkit-keyframes progress-bar-stripes {	
  0% {	
    background-position-x: 1rem;	
  }	
}	

@keyframes progress-bar-stripes {	@keyframes progress-bar-stripes {
  0% {	  0% {
    background-position-x: 1rem;	    background-position-x: 1rem;
  }	  }
}	}
.progress {	.progress {
  --bs-progress-height: 1rem;
  --bs-progress-font-size: 0.75rem;
  --bs-progress-bg: #e9ecef;
  --bs-progress-border-radius: 0.375rem;
  --bs-progress-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.075);
  --bs-progress-bar-color: #fff;
  --bs-progress-bar-bg: #0d6efd;
  --bs-progress-bar-transition: width 0.6s ease;
  display: flex;	  display: flex;
  height: 1rem;	  height: var(--bs-progress-height);
  overflow: hidden;	  overflow: hidden;
  font-size: 0.75rem;	  font-size: var(--bs-progress-font-size);
  background-color: #e9ecef;	  background-color: var(--bs-progress-bg);
  border-radius: 0.25rem;	  border-radius: var(--bs-progress-border-radius);
}	}


.progress-bar {	.progress-bar {
  display: flex;	  display: flex;
  flex-direction: column;	  flex-direction: column;
  justify-content: center;	  justify-content: center;
  overflow: hidden;	  overflow: hidden;
  color: #fff;	  color: var(--bs-progress-bar-color);
  text-align: center;	  text-align: center;
  white-space: nowrap;	  white-space: nowrap;
  background-color: #0d6efd;	  background-color: var(--bs-progress-bar-bg);
  transition: width 0.6s ease;	  transition: var(--bs-progress-bar-transition);
}	}
@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
  .progress-bar {	  .progress-bar {
@@ -5042,61 +4768,76 @@ textarea.form-control-lg {


.progress-bar-striped {	.progress-bar-striped {
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);	  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 1rem 1rem;	  background-size: var(--bs-progress-height) var(--bs-progress-height);
}	}


.progress-bar-animated {	.progress-bar-animated {
  -webkit-animation: 1s linear infinite progress-bar-stripes;	  animation: 1s linear infinite progress-bar-stripes;
          animation: 1s linear infinite progress-bar-stripes;	
}	}
@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
  .progress-bar-animated {	  .progress-bar-animated {
    -webkit-animation: none;	    animation: none;
            animation: none;	
  }	  }
}	}


.list-group {	.list-group {
  --bs-list-group-color: #212529;
  --bs-list-group-bg: #fff;
  --bs-list-group-border-color: rgba(0, 0, 0, 0.125);
  --bs-list-group-border-width: 1px;
  --bs-list-group-border-radius: 0.375rem;
  --bs-list-group-item-padding-x: 1rem;
  --bs-list-group-item-padding-y: 0.5rem;
  --bs-list-group-action-color: #495057;
  --bs-list-group-action-hover-color: #495057;
  --bs-list-group-action-hover-bg: #f8f9fa;
  --bs-list-group-action-active-color: #212529;
  --bs-list-group-action-active-bg: #e9ecef;
  --bs-list-group-disabled-color: #6c757d;
  --bs-list-group-disabled-bg: #fff;
  --bs-list-group-active-color: #fff;
  --bs-list-group-active-bg: #0d6efd;
  --bs-list-group-active-border-color: #0d6efd;
  display: flex;	  display: flex;
  flex-direction: column;	  flex-direction: column;
  padding-left: 0;	  padding-left: 0;
  margin-bottom: 0;	  margin-bottom: 0;
  border-radius: 0.25rem;	  border-radius: var(--bs-list-group-border-radius);
}	}


.list-group-numbered {	.list-group-numbered {
  list-style-type: none;	  list-style-type: none;
  counter-reset: section;	  counter-reset: section;
}	}
.list-group-numbered > li::before {	.list-group-numbered > .list-group-item::before {
  content: counters(section, ".") ". ";	  content: counters(section, ".") ". ";
  counter-increment: section;	  counter-increment: section;
}	}


.list-group-item-action {	.list-group-item-action {
  width: 100%;	  width: 100%;
  color: #495057;	  color: var(--bs-list-group-action-color);
  text-align: inherit;	  text-align: inherit;
}	}
.list-group-item-action:hover, .list-group-item-action:focus {	.list-group-item-action:hover, .list-group-item-action:focus {
  z-index: 1;	  z-index: 1;
  color: #495057;	  color: var(--bs-list-group-action-hover-color);
  text-decoration: none;	  text-decoration: none;
  background-color: #f8f9fa;	  background-color: var(--bs-list-group-action-hover-bg);
}	}
.list-group-item-action:active {	.list-group-item-action:active {
  color: #212529;	  color: var(--bs-list-group-action-active-color);
  background-color: #e9ecef;	  background-color: var(--bs-list-group-action-active-bg);
}	}


.list-group-item {	.list-group-item {
  position: relative;	  position: relative;
  display: block;	  display: block;
  padding: 0.5rem 1rem;	  padding: var(--bs-list-group-item-padding-y) var(--bs-list-group-item-padding-x);
  color: #212529;	  color: var(--bs-list-group-color);
  text-decoration: none;	  text-decoration: none;
  background-color: #fff;	  background-color: var(--bs-list-group-bg);
  border: 1px solid rgba(0, 0, 0, 0.125);	  border: var(--bs-list-group-border-width) solid var(--bs-list-group-border-color);
}	}
.list-group-item:first-child {	.list-group-item:first-child {
  border-top-left-radius: inherit;	  border-top-left-radius: inherit;
@@ -5107,172 +4848,172 @@ textarea.form-control-lg {
  border-bottom-left-radius: inherit;	  border-bottom-left-radius: inherit;
}	}
.list-group-item.disabled, .list-group-item:disabled {	.list-group-item.disabled, .list-group-item:disabled {
  color: #6c757d;	  color: var(--bs-list-group-disabled-color);
  pointer-events: none;	  pointer-events: none;
  background-color: #fff;	  background-color: var(--bs-list-group-disabled-bg);
}	}
.list-group-item.active {	.list-group-item.active {
  z-index: 2;	  z-index: 2;
  color: #fff;	  color: var(--bs-list-group-active-color);
  background-color: #0d6efd;	  background-color: var(--bs-list-group-active-bg);
  border-color: #0d6efd;	  border-color: var(--bs-list-group-active-border-color);
}	}
.list-group-item + .list-group-item {	.list-group-item + .list-group-item {
  border-top-width: 0;	  border-top-width: 0;
}	}
.list-group-item + .list-group-item.active {	.list-group-item + .list-group-item.active {
  margin-top: -1px;	  margin-top: calc(-1 * var(--bs-list-group-border-width));
  border-top-width: 1px;	  border-top-width: var(--bs-list-group-border-width);
}	}


.list-group-horizontal {	.list-group-horizontal {
  flex-direction: row;	  flex-direction: row;
}	}
.list-group-horizontal > .list-group-item:first-child {	.list-group-horizontal > .list-group-item:first-child:not(:last-child) {
  border-bottom-left-radius: 0.25rem;	  border-bottom-left-radius: var(--bs-list-group-border-radius);
  border-top-right-radius: 0;	  border-top-right-radius: 0;
}	}
.list-group-horizontal > .list-group-item:last-child {	.list-group-horizontal > .list-group-item:last-child:not(:first-child) {
  border-top-right-radius: 0.25rem;	  border-top-right-radius: var(--bs-list-group-border-radius);
  border-bottom-left-radius: 0;	  border-bottom-left-radius: 0;
}	}
.list-group-horizontal > .list-group-item.active {	.list-group-horizontal > .list-group-item.active {
  margin-top: 0;	  margin-top: 0;
}	}
.list-group-horizontal > .list-group-item + .list-group-item {	.list-group-horizontal > .list-group-item + .list-group-item {
  border-top-width: 1px;	  border-top-width: var(--bs-list-group-border-width);
  border-left-width: 0;	  border-left-width: 0;
}	}
.list-group-horizontal > .list-group-item + .list-group-item.active {	.list-group-horizontal > .list-group-item + .list-group-item.active {
  margin-left: -1px;	  margin-left: calc(-1 * var(--bs-list-group-border-width));
  border-left-width: 1px;	  border-left-width: var(--bs-list-group-border-width);
}	}


@media (min-width: 576px) {	@media (min-width: 576px) {
  .list-group-horizontal-sm {	  .list-group-horizontal-sm {
    flex-direction: row;	    flex-direction: row;
  }	  }
  .list-group-horizontal-sm > .list-group-item:first-child {	  .list-group-horizontal-sm > .list-group-item:first-child:not(:last-child) {
    border-bottom-left-radius: 0.25rem;	    border-bottom-left-radius: var(--bs-list-group-border-radius);
    border-top-right-radius: 0;	    border-top-right-radius: 0;
  }	  }
  .list-group-horizontal-sm > .list-group-item:last-child {	  .list-group-horizontal-sm > .list-group-item:last-child:not(:first-child) {
    border-top-right-radius: 0.25rem;	    border-top-right-radius: var(--bs-list-group-border-radius);
    border-bottom-left-radius: 0;	    border-bottom-left-radius: 0;
  }	  }
  .list-group-horizontal-sm > .list-group-item.active {	  .list-group-horizontal-sm > .list-group-item.active {
    margin-top: 0;	    margin-top: 0;
  }	  }
  .list-group-horizontal-sm > .list-group-item + .list-group-item {	  .list-group-horizontal-sm > .list-group-item + .list-group-item {
    border-top-width: 1px;	    border-top-width: var(--bs-list-group-border-width);
    border-left-width: 0;	    border-left-width: 0;
  }	  }
  .list-group-horizontal-sm > .list-group-item + .list-group-item.active {	  .list-group-horizontal-sm > .list-group-item + .list-group-item.active {
    margin-left: -1px;	    margin-left: calc(-1 * var(--bs-list-group-border-width));
    border-left-width: 1px;	    border-left-width: var(--bs-list-group-border-width);
  }	  }
}	}
@media (min-width: 768px) {	@media (min-width: 768px) {
  .list-group-horizontal-md {	  .list-group-horizontal-md {
    flex-direction: row;	    flex-direction: row;
  }	  }
  .list-group-horizontal-md > .list-group-item:first-child {	  .list-group-horizontal-md > .list-group-item:first-child:not(:last-child) {
    border-bottom-left-radius: 0.25rem;	    border-bottom-left-radius: var(--bs-list-group-border-radius);
    border-top-right-radius: 0;	    border-top-right-radius: 0;
  }	  }
  .list-group-horizontal-md > .list-group-item:last-child {	  .list-group-horizontal-md > .list-group-item:last-child:not(:first-child) {
    border-top-right-radius: 0.25rem;	    border-top-right-radius: var(--bs-list-group-border-radius);
    border-bottom-left-radius: 0;	    border-bottom-left-radius: 0;
  }	  }
  .list-group-horizontal-md > .list-group-item.active {	  .list-group-horizontal-md > .list-group-item.active {
    margin-top: 0;	    margin-top: 0;
  }	  }
  .list-group-horizontal-md > .list-group-item + .list-group-item {	  .list-group-horizontal-md > .list-group-item + .list-group-item {
    border-top-width: 1px;	    border-top-width: var(--bs-list-group-border-width);
    border-left-width: 0;	    border-left-width: 0;
  }	  }
  .list-group-horizontal-md > .list-group-item + .list-group-item.active {	  .list-group-horizontal-md > .list-group-item + .list-group-item.active {
    margin-left: -1px;	    margin-left: calc(-1 * var(--bs-list-group-border-width));
    border-left-width: 1px;	    border-left-width: var(--bs-list-group-border-width);
  }	  }
}	}
@media (min-width: 992px) {	@media (min-width: 992px) {
  .list-group-horizontal-lg {	  .list-group-horizontal-lg {
    flex-direction: row;	    flex-direction: row;
  }	  }
  .list-group-horizontal-lg > .list-group-item:first-child {	  .list-group-horizontal-lg > .list-group-item:first-child:not(:last-child) {
    border-bottom-left-radius: 0.25rem;	    border-bottom-left-radius: var(--bs-list-group-border-radius);
    border-top-right-radius: 0;	    border-top-right-radius: 0;
  }	  }
  .list-group-horizontal-lg > .list-group-item:last-child {	  .list-group-horizontal-lg > .list-group-item:last-child:not(:first-child) {
    border-top-right-radius: 0.25rem;	    border-top-right-radius: var(--bs-list-group-border-radius);
    border-bottom-left-radius: 0;	    border-bottom-left-radius: 0;
  }	  }
  .list-group-horizontal-lg > .list-group-item.active {	  .list-group-horizontal-lg > .list-group-item.active {
    margin-top: 0;	    margin-top: 0;
  }	  }
  .list-group-horizontal-lg > .list-group-item + .list-group-item {	  .list-group-horizontal-lg > .list-group-item + .list-group-item {
    border-top-width: 1px;	    border-top-width: var(--bs-list-group-border-width);
    border-left-width: 0;	    border-left-width: 0;
  }	  }
  .list-group-horizontal-lg > .list-group-item + .list-group-item.active {	  .list-group-horizontal-lg > .list-group-item + .list-group-item.active {
    margin-left: -1px;	    margin-left: calc(-1 * var(--bs-list-group-border-width));
    border-left-width: 1px;	    border-left-width: var(--bs-list-group-border-width);
  }	  }
}	}
@media (min-width: 1200px) {	@media (min-width: 1200px) {
  .list-group-horizontal-xl {	  .list-group-horizontal-xl {
    flex-direction: row;	    flex-direction: row;
  }	  }
  .list-group-horizontal-xl > .list-group-item:first-child {	  .list-group-horizontal-xl > .list-group-item:first-child:not(:last-child) {
    border-bottom-left-radius: 0.25rem;	    border-bottom-left-radius: var(--bs-list-group-border-radius);
    border-top-right-radius: 0;	    border-top-right-radius: 0;
  }	  }
  .list-group-horizontal-xl > .list-group-item:last-child {	  .list-group-horizontal-xl > .list-group-item:last-child:not(:first-child) {
    border-top-right-radius: 0.25rem;	    border-top-right-radius: var(--bs-list-group-border-radius);
    border-bottom-left-radius: 0;	    border-bottom-left-radius: 0;
  }	  }
  .list-group-horizontal-xl > .list-group-item.active {	  .list-group-horizontal-xl > .list-group-item.active {
    margin-top: 0;	    margin-top: 0;
  }	  }
  .list-group-horizontal-xl > .list-group-item + .list-group-item {	  .list-group-horizontal-xl > .list-group-item + .list-group-item {
    border-top-width: 1px;	    border-top-width: var(--bs-list-group-border-width);
    border-left-width: 0;	    border-left-width: 0;
  }	  }
  .list-group-horizontal-xl > .list-group-item + .list-group-item.active {	  .list-group-horizontal-xl > .list-group-item + .list-group-item.active {
    margin-left: -1px;	    margin-left: calc(-1 * var(--bs-list-group-border-width));
    border-left-width: 1px;	    border-left-width: var(--bs-list-group-border-width);
  }	  }
}	}
@media (min-width: 1400px) {	@media (min-width: 1400px) {
  .list-group-horizontal-xxl {	  .list-group-horizontal-xxl {
    flex-direction: row;	    flex-direction: row;
  }	  }
  .list-group-horizontal-xxl > .list-group-item:first-child {	  .list-group-horizontal-xxl > .list-group-item:first-child:not(:last-child) {
    border-bottom-left-radius: 0.25rem;	    border-bottom-left-radius: var(--bs-list-group-border-radius);
    border-top-right-radius: 0;	    border-top-right-radius: 0;
  }	  }
  .list-group-horizontal-xxl > .list-group-item:last-child {	  .list-group-horizontal-xxl > .list-group-item:last-child:not(:first-child) {
    border-top-right-radius: 0.25rem;	    border-top-right-radius: var(--bs-list-group-border-radius);
    border-bottom-left-radius: 0;	    border-bottom-left-radius: 0;
  }	  }
  .list-group-horizontal-xxl > .list-group-item.active {	  .list-group-horizontal-xxl > .list-group-item.active {
    margin-top: 0;	    margin-top: 0;
  }	  }
  .list-group-horizontal-xxl > .list-group-item + .list-group-item {	  .list-group-horizontal-xxl > .list-group-item + .list-group-item {
    border-top-width: 1px;	    border-top-width: var(--bs-list-group-border-width);
    border-left-width: 0;	    border-left-width: 0;
  }	  }
  .list-group-horizontal-xxl > .list-group-item + .list-group-item.active {	  .list-group-horizontal-xxl > .list-group-item + .list-group-item.active {
    margin-left: -1px;	    margin-left: calc(-1 * var(--bs-list-group-border-width));
    border-left-width: 1px;	    border-left-width: var(--bs-list-group-border-width);
  }	  }
}	}
.list-group-flush {	.list-group-flush {
  border-radius: 0;	  border-radius: 0;
}	}
.list-group-flush > .list-group-item {	.list-group-flush > .list-group-item {
  border-width: 0 0 1px;	  border-width: 0 0 var(--bs-list-group-border-width);
}	}
.list-group-flush > .list-group-item:last-child {	.list-group-flush > .list-group-item:last-child {
  border-bottom-width: 0;	  border-bottom-width: 0;
@@ -5396,9 +5137,9 @@ textarea.form-control-lg {
  height: 1em;	  height: 1em;
  padding: 0.25em 0.25em;	  padding: 0.25em 0.25em;
  color: #000;	  color: #000;
  background: transparent url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16' fill='%23000'%3e%3cpath d='M.293.293a1 1 0 011.414 0L8 6.586 14.293.293a1 1 0 111.414 1.414L9.414 8l6.293 6.293a1 1 0 01-1.414 1.414L8 9.414l-6.293 6.293a1 1 0 01-1.414-1.414L6.586 8 .293 1.707a1 1 0 010-1.414z'/%3e%3c/svg%3e") center/1em auto no-repeat;	  background: transparent url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16' fill='%23000'%3e%3cpath d='M.293.293a1 1 0 0 1 1.414 0L8 6.586 14.293.293a1 1 0 1 1 1.414 1.414L9.414 8l6.293 6.293a1 1 0 0 1-1.414 1.414L8 9.414l-6.293 6.293a1 1 0 0 1-1.414-1.414L6.586 8 .293 1.707a1 1 0 0 1 0-1.414z'/%3e%3c/svg%3e") center/1em auto no-repeat;
  border: 0;	  border: 0;
  border-radius: 0.25rem;	  border-radius: 0.375rem;
  opacity: 0.5;	  opacity: 0.5;
}	}
.btn-close:hover {	.btn-close:hover {
@@ -5415,7 +5156,6 @@ textarea.form-control-lg {
  pointer-events: none;	  pointer-events: none;
  -webkit-user-select: none;	  -webkit-user-select: none;
     -moz-user-select: none;	     -moz-user-select: none;
      -ms-user-select: none;	
          user-select: none;	          user-select: none;
  opacity: 0.25;	  opacity: 0.25;
}	}
@@ -5425,15 +5165,31 @@ textarea.form-control-lg {
}	}


.toast {	.toast {
  width: 350px;	  --bs-toast-zindex: 1090;
  --bs-toast-padding-x: 0.75rem;
  --bs-toast-padding-y: 0.5rem;
  --bs-toast-spacing: 1.5rem;
  --bs-toast-max-width: 350px;
  --bs-toast-font-size: 0.875rem;
  --bs-toast-color: ;
  --bs-toast-bg: rgba(255, 255, 255, 0.85);
  --bs-toast-border-width: 1px;
  --bs-toast-border-color: var(--bs-border-color-translucent);
  --bs-toast-border-radius: 0.375rem;
  --bs-toast-box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15);
  --bs-toast-header-color: #6c757d;
  --bs-toast-header-bg: rgba(255, 255, 255, 0.85);
  --bs-toast-header-border-color: rgba(0, 0, 0, 0.05);
  width: var(--bs-toast-max-width);
  max-width: 100%;	  max-width: 100%;
  font-size: 0.875rem;	  font-size: var(--bs-toast-font-size);
  color: var(--bs-toast-color);
  pointer-events: auto;	  pointer-events: auto;
  background-color: rgba(255, 255, 255, 0.85);	  background-color: var(--bs-toast-bg);
  background-clip: padding-box;	  background-clip: padding-box;
  border: 1px solid rgba(0, 0, 0, 0.1);	  border: var(--bs-toast-border-width) solid var(--bs-toast-border-color);
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15);	  box-shadow: var(--bs-toast-box-shadow);
  border-radius: 0.25rem;	  border-radius: var(--bs-toast-border-radius);
}	}
.toast.showing {	.toast.showing {
  opacity: 0;	  opacity: 0;
@@ -5443,42 +5199,65 @@ textarea.form-control-lg {
}	}


.toast-container {	.toast-container {
  width: -webkit-max-content;	  --bs-toast-zindex: 1090;
  position: absolute;
  z-index: var(--bs-toast-zindex);
  width: -moz-max-content;	  width: -moz-max-content;
  width: max-content;	  width: max-content;
  max-width: 100%;	  max-width: 100%;
  pointer-events: none;	  pointer-events: none;
}	}
.toast-container > :not(:last-child) {	.toast-container > :not(:last-child) {
  margin-bottom: 0.75rem;	  margin-bottom: var(--bs-toast-spacing);
}	}


.toast-header {	.toast-header {
  display: flex;	  display: flex;
  align-items: center;	  align-items: center;
  padding: 0.5rem 0.75rem;	  padding: var(--bs-toast-padding-y) var(--bs-toast-padding-x);
  color: #6c757d;	  color: var(--bs-toast-header-color);
  background-color: rgba(255, 255, 255, 0.85);	  background-color: var(--bs-toast-header-bg);
  background-clip: padding-box;	  background-clip: padding-box;
  border-bottom: 1px solid rgba(0, 0, 0, 0.05);	  border-bottom: var(--bs-toast-border-width) solid var(--bs-toast-header-border-color);
  border-top-left-radius: calc(0.25rem - 1px);	  border-top-left-radius: calc(var(--bs-toast-border-radius) - var(--bs-toast-border-width));
  border-top-right-radius: calc(0.25rem - 1px);	  border-top-right-radius: calc(var(--bs-toast-border-radius) - var(--bs-toast-border-width));
}	}
.toast-header .btn-close {	.toast-header .btn-close {
  margin-right: -0.375rem;	  margin-right: calc(-0.5 * var(--bs-toast-padding-x));
  margin-left: 0.75rem;	  margin-left: var(--bs-toast-padding-x);
}	}


.toast-body {	.toast-body {
  padding: 0.75rem;	  padding: var(--bs-toast-padding-x);
  word-wrap: break-word;	  word-wrap: break-word;
}	}


.modal {	.modal {
  --bs-modal-zindex: 1055;
  --bs-modal-width: 500px;
  --bs-modal-padding: 1rem;
  --bs-modal-margin: 0.5rem;
  --bs-modal-color: ;
  --bs-modal-bg: #fff;
  --bs-modal-border-color: var(--bs-border-color-translucent);
  --bs-modal-border-width: 1px;
  --bs-modal-border-radius: 0.5rem;
  --bs-modal-box-shadow: 0 0.125rem 0.25rem rgba(0, 0, 0, 0.075);
  --bs-modal-inner-border-radius: calc(0.5rem - 1px);
  --bs-modal-header-padding-x: 1rem;
  --bs-modal-header-padding-y: 1rem;
  --bs-modal-header-padding: 1rem 1rem;
  --bs-modal-header-border-color: var(--bs-border-color);
  --bs-modal-header-border-width: 1px;
  --bs-modal-title-line-height: 1.5;
  --bs-modal-footer-gap: 0.5rem;
  --bs-modal-footer-bg: ;
  --bs-modal-footer-border-color: var(--bs-border-color);
  --bs-modal-footer-border-width: 1px;
  position: fixed;	  position: fixed;
  top: 0;	  top: 0;
  left: 0;	  left: 0;
  z-index: 1055;	  z-index: var(--bs-modal-zindex);
  display: none;	  display: none;
  width: 100%;	  width: 100%;
  height: 100%;	  height: 100%;
@@ -5490,7 +5269,7 @@ textarea.form-control-lg {
.modal-dialog {	.modal-dialog {
  position: relative;	  position: relative;
  width: auto;	  width: auto;
  margin: 0.5rem;	  margin: var(--bs-modal-margin);
  pointer-events: none;	  pointer-events: none;
}	}
.modal.fade .modal-dialog {	.modal.fade .modal-dialog {
@@ -5510,7 +5289,7 @@ textarea.form-control-lg {
}	}


.modal-dialog-scrollable {	.modal-dialog-scrollable {
  height: calc(100% - 1rem);	  height: calc(100% - var(--bs-modal-margin) * 2);
}	}
.modal-dialog-scrollable .modal-content {	.modal-dialog-scrollable .modal-content {
  max-height: 100%;	  max-height: 100%;
@@ -5523,106 +5302,107 @@ textarea.form-control-lg {
.modal-dialog-centered {	.modal-dialog-centered {
  display: flex;	  display: flex;
  align-items: center;	  align-items: center;
  min-height: calc(100% - 1rem);	  min-height: calc(100% - var(--bs-modal-margin) * 2);
}	}


.modal-content {	.modal-content {
  position: relative;	  position: relative;
  display: flex;	  display: flex;
  flex-direction: column;	  flex-direction: column;
  width: 100%;	  width: 100%;
  color: var(--bs-modal-color);
  pointer-events: auto;	  pointer-events: auto;
  background-color: #fff;	  background-color: var(--bs-modal-bg);
  background-clip: padding-box;	  background-clip: padding-box;
  border: 1px solid rgba(0, 0, 0, 0.2);	  border: var(--bs-modal-border-width) solid var(--bs-modal-border-color);
  border-radius: 0.3rem;	  border-radius: var(--bs-modal-border-radius);
  outline: 0;	  outline: 0;
}	}


.modal-backdrop {	.modal-backdrop {
  --bs-backdrop-zindex: 1050;
  --bs-backdrop-bg: #000;
  --bs-backdrop-opacity: 0.5;
  position: fixed;	  position: fixed;
  top: 0;	  top: 0;
  left: 0;	  left: 0;
  z-index: 1050;	  z-index: var(--bs-backdrop-zindex);
  width: 100vw;	  width: 100vw;
  height: 100vh;	  height: 100vh;
  background-color: #000;	  background-color: var(--bs-backdrop-bg);
}	}
.modal-backdrop.fade {	.modal-backdrop.fade {
  opacity: 0;	  opacity: 0;
}	}
.modal-backdrop.show {	.modal-backdrop.show {
  opacity: 0.5;	  opacity: var(--bs-backdrop-opacity);
}	}


.modal-header {	.modal-header {
  display: flex;	  display: flex;
  flex-shrink: 0;	  flex-shrink: 0;
  align-items: center;	  align-items: center;
  justify-content: space-between;	  justify-content: space-between;
  padding: 1rem 1rem;	  padding: var(--bs-modal-header-padding);
  border-bottom: 1px solid #dee2e6;	  border-bottom: var(--bs-modal-header-border-width) solid var(--bs-modal-header-border-color);
  border-top-left-radius: calc(0.3rem - 1px);	  border-top-left-radius: var(--bs-modal-inner-border-radius);
  border-top-right-radius: calc(0.3rem - 1px);	  border-top-right-radius: var(--bs-modal-inner-border-radius);
}	}
.modal-header .btn-close {	.modal-header .btn-close {
  padding: 0.5rem 0.5rem;	  padding: calc(var(--bs-modal-header-padding-y) * 0.5) calc(var(--bs-modal-header-padding-x) * 0.5);
  margin: -0.5rem -0.5rem -0.5rem auto;	  margin: calc(-0.5 * var(--bs-modal-header-padding-y)) calc(-0.5 * var(--bs-modal-header-padding-x)) calc(-0.5 * var(--bs-modal-header-padding-y)) auto;
}	}


.modal-title {	.modal-title {
  margin-bottom: 0;	  margin-bottom: 0;
  line-height: 1.5;	  line-height: var(--bs-modal-title-line-height);
}	}


.modal-body {	.modal-body {
  position: relative;	  position: relative;
  flex: 1 1 auto;	  flex: 1 1 auto;
  padding: 1rem;	  padding: var(--bs-modal-padding);
}	}


.modal-footer {	.modal-footer {
  display: flex;	  display: flex;
  flex-wrap: wrap;	
  flex-shrink: 0;	  flex-shrink: 0;
  flex-wrap: wrap;
  align-items: center;	  align-items: center;
  justify-content: flex-end;	  justify-content: flex-end;
  padding: 0.75rem;	  padding: calc(var(--bs-modal-padding) - var(--bs-modal-footer-gap) * 0.5);
  border-top: 1px solid #dee2e6;	  background-color: var(--bs-modal-footer-bg);
  border-bottom-right-radius: calc(0.3rem - 1px);	  border-top: var(--bs-modal-footer-border-width) solid var(--bs-modal-footer-border-color);
  border-bottom-left-radius: calc(0.3rem - 1px);	  border-bottom-right-radius: var(--bs-modal-inner-border-radius);
  border-bottom-left-radius: var(--bs-modal-inner-border-radius);
}	}
.modal-footer > * {	.modal-footer > * {
  margin: 0.25rem;	  margin: calc(var(--bs-modal-footer-gap) * 0.5);
}	}


@media (min-width: 576px) {	@media (min-width: 576px) {
  .modal-dialog {	  .modal {
    max-width: 500px;	    --bs-modal-margin: 1.75rem;
    margin: 1.75rem auto;	    --bs-modal-box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15);
  }	

  .modal-dialog-scrollable {	
    height: calc(100% - 3.5rem);	
  }	  }

  .modal-dialog {
  .modal-dialog-centered {	    max-width: var(--bs-modal-width);
    min-height: calc(100% - 3.5rem);	    margin-right: auto;
    margin-left: auto;
  }	  }

  .modal-sm {	  .modal-sm {
    max-width: 300px;	    --bs-modal-width: 300px;
  }	  }
}	}
@media (min-width: 992px) {	@media (min-width: 992px) {
  .modal-lg,	  .modal-lg,
.modal-xl {	  .modal-xl {
    max-width: 800px;	    --bs-modal-width: 800px;
  }	  }
}	}
@media (min-width: 1200px) {	@media (min-width: 1200px) {
  .modal-xl {	  .modal-xl {
    max-width: 1140px;	    --bs-modal-width: 1140px;
  }	  }
}	}
.modal-fullscreen {	.modal-fullscreen {
@@ -5636,15 +5416,13 @@ textarea.form-control-lg {
  border: 0;	  border: 0;
  border-radius: 0;	  border-radius: 0;
}	}
.modal-fullscreen .modal-header {	.modal-fullscreen .modal-header,
.modal-fullscreen .modal-footer {
  border-radius: 0;	  border-radius: 0;
}	}
.modal-fullscreen .modal-body {	.modal-fullscreen .modal-body {
  overflow-y: auto;	  overflow-y: auto;
}	}
.modal-fullscreen .modal-footer {	
  border-radius: 0;	
}	


@media (max-width: 575.98px) {	@media (max-width: 575.98px) {
  .modal-fullscreen-sm-down {	  .modal-fullscreen-sm-down {
@@ -5658,15 +5436,13 @@ textarea.form-control-lg {
    border: 0;	    border: 0;
    border-radius: 0;	    border-radius: 0;
  }	  }
  .modal-fullscreen-sm-down .modal-header {	  .modal-fullscreen-sm-down .modal-header,
  .modal-fullscreen-sm-down .modal-footer {
    border-radius: 0;	    border-radius: 0;
  }	  }
  .modal-fullscreen-sm-down .modal-body {	  .modal-fullscreen-sm-down .modal-body {
    overflow-y: auto;	    overflow-y: auto;
  }	  }
  .modal-fullscreen-sm-down .modal-footer {	
    border-radius: 0;	
  }	
}	}
@media (max-width: 767.98px) {	@media (max-width: 767.98px) {
  .modal-fullscreen-md-down {	  .modal-fullscreen-md-down {
@@ -5680,15 +5456,13 @@ textarea.form-control-lg {
    border: 0;	    border: 0;
    border-radius: 0;	    border-radius: 0;
  }	  }
  .modal-fullscreen-md-down .modal-header {	  .modal-fullscreen-md-down .modal-header,
  .modal-fullscreen-md-down .modal-footer {
    border-radius: 0;	    border-radius: 0;
  }	  }
  .modal-fullscreen-md-down .modal-body {	  .modal-fullscreen-md-down .modal-body {
    overflow-y: auto;	    overflow-y: auto;
  }	  }
  .modal-fullscreen-md-down .modal-footer {	
    border-radius: 0;	
  }	
}	}
@media (max-width: 991.98px) {	@media (max-width: 991.98px) {
  .modal-fullscreen-lg-down {	  .modal-fullscreen-lg-down {
@@ -5702,15 +5476,13 @@ textarea.form-control-lg {
    border: 0;	    border: 0;
    border-radius: 0;	    border-radius: 0;
  }	  }
  .modal-fullscreen-lg-down .modal-header {	  .modal-fullscreen-lg-down .modal-header,
  .modal-fullscreen-lg-down .modal-footer {
    border-radius: 0;	    border-radius: 0;
  }	  }
  .modal-fullscreen-lg-down .modal-body {	  .modal-fullscreen-lg-down .modal-body {
    overflow-y: auto;	    overflow-y: auto;
  }	  }
  .modal-fullscreen-lg-down .modal-footer {	
    border-radius: 0;	
  }	
}	}
@media (max-width: 1199.98px) {	@media (max-width: 1199.98px) {
  .modal-fullscreen-xl-down {	  .modal-fullscreen-xl-down {
@@ -5724,15 +5496,13 @@ textarea.form-control-lg {
    border: 0;	    border: 0;
    border-radius: 0;	    border-radius: 0;
  }	  }
  .modal-fullscreen-xl-down .modal-header {	  .modal-fullscreen-xl-down .modal-header,
  .modal-fullscreen-xl-down .modal-footer {
    border-radius: 0;	    border-radius: 0;
  }	  }
  .modal-fullscreen-xl-down .modal-body {	  .modal-fullscreen-xl-down .modal-body {
    overflow-y: auto;	    overflow-y: auto;
  }	  }
  .modal-fullscreen-xl-down .modal-footer {	
    border-radius: 0;	
  }	
}	}
@media (max-width: 1399.98px) {	@media (max-width: 1399.98px) {
  .modal-fullscreen-xxl-down {	  .modal-fullscreen-xxl-down {
@@ -5746,21 +5516,31 @@ textarea.form-control-lg {
    border: 0;	    border: 0;
    border-radius: 0;	    border-radius: 0;
  }	  }
  .modal-fullscreen-xxl-down .modal-header {	  .modal-fullscreen-xxl-down .modal-header,
  .modal-fullscreen-xxl-down .modal-footer {
    border-radius: 0;	    border-radius: 0;
  }	  }
  .modal-fullscreen-xxl-down .modal-body {	  .modal-fullscreen-xxl-down .modal-body {
    overflow-y: auto;	    overflow-y: auto;
  }	  }
  .modal-fullscreen-xxl-down .modal-footer {	
    border-radius: 0;	
  }	
}	}
.tooltip {	.tooltip {
  position: absolute;	  --bs-tooltip-zindex: 1080;
  z-index: 1080;	  --bs-tooltip-max-width: 200px;
  --bs-tooltip-padding-x: 0.5rem;
  --bs-tooltip-padding-y: 0.25rem;
  --bs-tooltip-margin: ;
  --bs-tooltip-font-size: 0.875rem;
  --bs-tooltip-color: #fff;
  --bs-tooltip-bg: #000;
  --bs-tooltip-border-radius: 0.375rem;
  --bs-tooltip-opacity: 0.9;
  --bs-tooltip-arrow-width: 0.8rem;
  --bs-tooltip-arrow-height: 0.4rem;
  z-index: var(--bs-tooltip-zindex);
  display: block;	  display: block;
  margin: 0;	  padding: var(--bs-tooltip-arrow-height);
  margin: var(--bs-tooltip-margin);
  font-family: var(--bs-font-sans-serif);	  font-family: var(--bs-font-sans-serif);
  font-style: normal;	  font-style: normal;
  font-weight: 400;	  font-weight: 400;
@@ -5772,21 +5552,20 @@ textarea.form-control-lg {
  text-transform: none;	  text-transform: none;
  letter-spacing: normal;	  letter-spacing: normal;
  word-break: normal;	  word-break: normal;
  word-spacing: normal;	
  white-space: normal;	  white-space: normal;
  word-spacing: normal;
  line-break: auto;	  line-break: auto;
  font-size: 0.875rem;	  font-size: var(--bs-tooltip-font-size);
  word-wrap: break-word;	  word-wrap: break-word;
  opacity: 0;	  opacity: 0;
}	}
.tooltip.show {	.tooltip.show {
  opacity: 0.9;	  opacity: var(--bs-tooltip-opacity);
}	}
.tooltip .tooltip-arrow {	.tooltip .tooltip-arrow {
  position: absolute;	
  display: block;	  display: block;
  width: 0.8rem;	  width: var(--bs-tooltip-arrow-width);
  height: 0.4rem;	  height: var(--bs-tooltip-arrow-height);
}	}
.tooltip .tooltip-arrow::before {	.tooltip .tooltip-arrow::before {
  position: absolute;	  position: absolute;
@@ -5795,74 +5574,83 @@ textarea.form-control-lg {
  border-style: solid;	  border-style: solid;
}	}


.bs-tooltip-top, .bs-tooltip-auto[data-popper-placement^=top] {	
  padding: 0.4rem 0;	
}	
.bs-tooltip-top .tooltip-arrow, .bs-tooltip-auto[data-popper-placement^=top] .tooltip-arrow {	.bs-tooltip-top .tooltip-arrow, .bs-tooltip-auto[data-popper-placement^=top] .tooltip-arrow {
  bottom: 0;	  bottom: 0;
}	}
.bs-tooltip-top .tooltip-arrow::before, .bs-tooltip-auto[data-popper-placement^=top] .tooltip-arrow::before {	.bs-tooltip-top .tooltip-arrow::before, .bs-tooltip-auto[data-popper-placement^=top] .tooltip-arrow::before {
  top: -1px;	  top: -1px;
  border-width: 0.4rem 0.4rem 0;	  border-width: var(--bs-tooltip-arrow-height) calc(var(--bs-tooltip-arrow-width) * 0.5) 0;
  border-top-color: #000;	  border-top-color: var(--bs-tooltip-bg);
}	}


.bs-tooltip-end, .bs-tooltip-auto[data-popper-placement^=right] {	/* rtl:begin:ignore */
  padding: 0 0.4rem;	
}	
.bs-tooltip-end .tooltip-arrow, .bs-tooltip-auto[data-popper-placement^=right] .tooltip-arrow {	.bs-tooltip-end .tooltip-arrow, .bs-tooltip-auto[data-popper-placement^=right] .tooltip-arrow {
  left: 0;	  left: 0;
  width: 0.4rem;	  width: var(--bs-tooltip-arrow-height);
  height: 0.8rem;	  height: var(--bs-tooltip-arrow-width);
}	}
.bs-tooltip-end .tooltip-arrow::before, .bs-tooltip-auto[data-popper-placement^=right] .tooltip-arrow::before {	.bs-tooltip-end .tooltip-arrow::before, .bs-tooltip-auto[data-popper-placement^=right] .tooltip-arrow::before {
  right: -1px;	  right: -1px;
  border-width: 0.4rem 0.4rem 0.4rem 0;	  border-width: calc(var(--bs-tooltip-arrow-width) * 0.5) var(--bs-tooltip-arrow-height) calc(var(--bs-tooltip-arrow-width) * 0.5) 0;
  border-right-color: #000;	  border-right-color: var(--bs-tooltip-bg);
}	}


.bs-tooltip-bottom, .bs-tooltip-auto[data-popper-placement^=bottom] {	/* rtl:end:ignore */
  padding: 0.4rem 0;	
}	
.bs-tooltip-bottom .tooltip-arrow, .bs-tooltip-auto[data-popper-placement^=bottom] .tooltip-arrow {	.bs-tooltip-bottom .tooltip-arrow, .bs-tooltip-auto[data-popper-placement^=bottom] .tooltip-arrow {
  top: 0;	  top: 0;
}	}
.bs-tooltip-bottom .tooltip-arrow::before, .bs-tooltip-auto[data-popper-placement^=bottom] .tooltip-arrow::before {	.bs-tooltip-bottom .tooltip-arrow::before, .bs-tooltip-auto[data-popper-placement^=bottom] .tooltip-arrow::before {
  bottom: -1px;	  bottom: -1px;
  border-width: 0 0.4rem 0.4rem;	  border-width: 0 calc(var(--bs-tooltip-arrow-width) * 0.5) var(--bs-tooltip-arrow-height);
  border-bottom-color: #000;	  border-bottom-color: var(--bs-tooltip-bg);
}	}


.bs-tooltip-start, .bs-tooltip-auto[data-popper-placement^=left] {	/* rtl:begin:ignore */
  padding: 0 0.4rem;	
}	
.bs-tooltip-start .tooltip-arrow, .bs-tooltip-auto[data-popper-placement^=left] .tooltip-arrow {	.bs-tooltip-start .tooltip-arrow, .bs-tooltip-auto[data-popper-placement^=left] .tooltip-arrow {
  right: 0;	  right: 0;
  width: 0.4rem;	  width: var(--bs-tooltip-arrow-height);
  height: 0.8rem;	  height: var(--bs-tooltip-arrow-width);
}	}
.bs-tooltip-start .tooltip-arrow::before, .bs-tooltip-auto[data-popper-placement^=left] .tooltip-arrow::before {	.bs-tooltip-start .tooltip-arrow::before, .bs-tooltip-auto[data-popper-placement^=left] .tooltip-arrow::before {
  left: -1px;	  left: -1px;
  border-width: 0.4rem 0 0.4rem 0.4rem;	  border-width: calc(var(--bs-tooltip-arrow-width) * 0.5) 0 calc(var(--bs-tooltip-arrow-width) * 0.5) var(--bs-tooltip-arrow-height);
  border-left-color: #000;	  border-left-color: var(--bs-tooltip-bg);
}	}


/* rtl:end:ignore */
.tooltip-inner {	.tooltip-inner {
  max-width: 200px;	  max-width: var(--bs-tooltip-max-width);
  padding: 0.25rem 0.5rem;	  padding: var(--bs-tooltip-padding-y) var(--bs-tooltip-padding-x);
  color: #fff;	  color: var(--bs-tooltip-color);
  text-align: center;	  text-align: center;
  background-color: #000;	  background-color: var(--bs-tooltip-bg);
  border-radius: 0.25rem;	  border-radius: var(--bs-tooltip-border-radius);
}	}


.popover {	.popover {
  position: absolute;	  --bs-popover-zindex: 1070;
  top: 0;	  --bs-popover-max-width: 276px;
  left: 0 /* rtl:ignore */;	  --bs-popover-font-size: 0.875rem;
  z-index: 1070;	  --bs-popover-bg: #fff;
  --bs-popover-border-width: 1px;
  --bs-popover-border-color: var(--bs-border-color-translucent);
  --bs-popover-border-radius: 0.5rem;
  --bs-popover-inner-border-radius: calc(0.5rem - 1px);
  --bs-popover-box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15);
  --bs-popover-header-padding-x: 1rem;
  --bs-popover-header-padding-y: 0.5rem;
  --bs-popover-header-font-size: 1rem;
  --bs-popover-header-color: ;
  --bs-popover-header-bg: #f0f0f0;
  --bs-popover-body-padding-x: 1rem;
  --bs-popover-body-padding-y: 1rem;
  --bs-popover-body-color: #212529;
  --bs-popover-arrow-width: 1rem;
  --bs-popover-arrow-height: 0.5rem;
  --bs-popover-arrow-border: var(--bs-popover-border-color);
  z-index: var(--bs-popover-zindex);
  display: block;	  display: block;
  max-width: 276px;	  max-width: var(--bs-popover-max-width);
  font-family: var(--bs-font-sans-serif);	  font-family: var(--bs-font-sans-serif);
  font-style: normal;	  font-style: normal;
  font-weight: 400;	  font-weight: 400;
@@ -5874,116 +5662,125 @@ textarea.form-control-lg {
  text-transform: none;	  text-transform: none;
  letter-spacing: normal;	  letter-spacing: normal;
  word-break: normal;	  word-break: normal;
  word-spacing: normal;	
  white-space: normal;	  white-space: normal;
  word-spacing: normal;
  line-break: auto;	  line-break: auto;
  font-size: 0.875rem;	  font-size: var(--bs-popover-font-size);
  word-wrap: break-word;	  word-wrap: break-word;
  background-color: #fff;	  background-color: var(--bs-popover-bg);
  background-clip: padding-box;	  background-clip: padding-box;
  border: 1px solid rgba(0, 0, 0, 0.2);	  border: var(--bs-popover-border-width) solid var(--bs-popover-border-color);
  border-radius: 0.3rem;	  border-radius: var(--bs-popover-border-radius);
}	}
.popover .popover-arrow {	.popover .popover-arrow {
  position: absolute;	
  display: block;	  display: block;
  width: 1rem;	  width: var(--bs-popover-arrow-width);
  height: 0.5rem;	  height: var(--bs-popover-arrow-height);
}	}
.popover .popover-arrow::before, .popover .popover-arrow::after {	.popover .popover-arrow::before, .popover .popover-arrow::after {
  position: absolute;	  position: absolute;
  display: block;	  display: block;
  content: "";	  content: "";
  border-color: transparent;	  border-color: transparent;
  border-style: solid;	  border-style: solid;
  border-width: 0;
}	}


.bs-popover-top > .popover-arrow, .bs-popover-auto[data-popper-placement^=top] > .popover-arrow {	.bs-popover-top > .popover-arrow, .bs-popover-auto[data-popper-placement^=top] > .popover-arrow {
  bottom: calc(-0.5rem - 1px);	  bottom: calc(-1 * (var(--bs-popover-arrow-height)) - var(--bs-popover-border-width));
}
.bs-popover-top > .popover-arrow::before, .bs-popover-auto[data-popper-placement^=top] > .popover-arrow::before, .bs-popover-top > .popover-arrow::after, .bs-popover-auto[data-popper-placement^=top] > .popover-arrow::after {
  border-width: var(--bs-popover-arrow-height) calc(var(--bs-popover-arrow-width) * 0.5) 0;
}	}
.bs-popover-top > .popover-arrow::before, .bs-popover-auto[data-popper-placement^=top] > .popover-arrow::before {	.bs-popover-top > .popover-arrow::before, .bs-popover-auto[data-popper-placement^=top] > .popover-arrow::before {
  bottom: 0;	  bottom: 0;
  border-width: 0.5rem 0.5rem 0;	  border-top-color: var(--bs-popover-arrow-border);
  border-top-color: rgba(0, 0, 0, 0.25);	
}	}
.bs-popover-top > .popover-arrow::after, .bs-popover-auto[data-popper-placement^=top] > .popover-arrow::after {	.bs-popover-top > .popover-arrow::after, .bs-popover-auto[data-popper-placement^=top] > .popover-arrow::after {
  bottom: 1px;	  bottom: var(--bs-popover-border-width);
  border-width: 0.5rem 0.5rem 0;	  border-top-color: var(--bs-popover-bg);
  border-top-color: #fff;	
}	}


/* rtl:begin:ignore */
.bs-popover-end > .popover-arrow, .bs-popover-auto[data-popper-placement^=right] > .popover-arrow {	.bs-popover-end > .popover-arrow, .bs-popover-auto[data-popper-placement^=right] > .popover-arrow {
  left: calc(-0.5rem - 1px);	  left: calc(-1 * (var(--bs-popover-arrow-height)) - var(--bs-popover-border-width));
  width: 0.5rem;	  width: var(--bs-popover-arrow-height);
  height: 1rem;	  height: var(--bs-popover-arrow-width);
}
.bs-popover-end > .popover-arrow::before, .bs-popover-auto[data-popper-placement^=right] > .popover-arrow::before, .bs-popover-end > .popover-arrow::after, .bs-popover-auto[data-popper-placement^=right] > .popover-arrow::after {
  border-width: calc(var(--bs-popover-arrow-width) * 0.5) var(--bs-popover-arrow-height) calc(var(--bs-popover-arrow-width) * 0.5) 0;
}	}
.bs-popover-end > .popover-arrow::before, .bs-popover-auto[data-popper-placement^=right] > .popover-arrow::before {	.bs-popover-end > .popover-arrow::before, .bs-popover-auto[data-popper-placement^=right] > .popover-arrow::before {
  left: 0;	  left: 0;
  border-width: 0.5rem 0.5rem 0.5rem 0;	  border-right-color: var(--bs-popover-arrow-border);
  border-right-color: rgba(0, 0, 0, 0.25);	
}	}
.bs-popover-end > .popover-arrow::after, .bs-popover-auto[data-popper-placement^=right] > .popover-arrow::after {	.bs-popover-end > .popover-arrow::after, .bs-popover-auto[data-popper-placement^=right] > .popover-arrow::after {
  left: 1px;	  left: var(--bs-popover-border-width);
  border-width: 0.5rem 0.5rem 0.5rem 0;	  border-right-color: var(--bs-popover-bg);
  border-right-color: #fff;	
}	}


/* rtl:end:ignore */
.bs-popover-bottom > .popover-arrow, .bs-popover-auto[data-popper-placement^=bottom] > .popover-arrow {	.bs-popover-bottom > .popover-arrow, .bs-popover-auto[data-popper-placement^=bottom] > .popover-arrow {
  top: calc(-0.5rem - 1px);	  top: calc(-1 * (var(--bs-popover-arrow-height)) - var(--bs-popover-border-width));
}
.bs-popover-bottom > .popover-arrow::before, .bs-popover-auto[data-popper-placement^=bottom] > .popover-arrow::before, .bs-popover-bottom > .popover-arrow::after, .bs-popover-auto[data-popper-placement^=bottom] > .popover-arrow::after {
  border-width: 0 calc(var(--bs-popover-arrow-width) * 0.5) var(--bs-popover-arrow-height);
}	}
.bs-popover-bottom > .popover-arrow::before, .bs-popover-auto[data-popper-placement^=bottom] > .popover-arrow::before {	.bs-popover-bottom > .popover-arrow::before, .bs-popover-auto[data-popper-placement^=bottom] > .popover-arrow::before {
  top: 0;	  top: 0;
  border-width: 0 0.5rem 0.5rem 0.5rem;	  border-bottom-color: var(--bs-popover-arrow-border);
  border-bottom-color: rgba(0, 0, 0, 0.25);	
}	}
.bs-popover-bottom > .popover-arrow::after, .bs-popover-auto[data-popper-placement^=bottom] > .popover-arrow::after {	.bs-popover-bottom > .popover-arrow::after, .bs-popover-auto[data-popper-placement^=bottom] > .popover-arrow::after {
  top: 1px;	  top: var(--bs-popover-border-width);
  border-width: 0 0.5rem 0.5rem 0.5rem;	  border-bottom-color: var(--bs-popover-bg);
  border-bottom-color: #fff;	
}	}
.bs-popover-bottom .popover-header::before, .bs-popover-auto[data-popper-placement^=bottom] .popover-header::before {	.bs-popover-bottom .popover-header::before, .bs-popover-auto[data-popper-placement^=bottom] .popover-header::before {
  position: absolute;	  position: absolute;
  top: 0;	  top: 0;
  left: 50%;	  left: 50%;
  display: block;	  display: block;
  width: 1rem;	  width: var(--bs-popover-arrow-width);
  margin-left: -0.5rem;	  margin-left: calc(-0.5 * var(--bs-popover-arrow-width));
  content: "";	  content: "";
  border-bottom: 1px solid #f0f0f0;	  border-bottom: var(--bs-popover-border-width) solid var(--bs-popover-header-bg);
}	}


/* rtl:begin:ignore */
.bs-popover-start > .popover-arrow, .bs-popover-auto[data-popper-placement^=left] > .popover-arrow {	.bs-popover-start > .popover-arrow, .bs-popover-auto[data-popper-placement^=left] > .popover-arrow {
  right: calc(-0.5rem - 1px);	  right: calc(-1 * (var(--bs-popover-arrow-height)) - var(--bs-popover-border-width));
  width: 0.5rem;	  width: var(--bs-popover-arrow-height);
  height: 1rem;	  height: var(--bs-popover-arrow-width);
}
.bs-popover-start > .popover-arrow::before, .bs-popover-auto[data-popper-placement^=left] > .popover-arrow::before, .bs-popover-start > .popover-arrow::after, .bs-popover-auto[data-popper-placement^=left] > .popover-arrow::after {
  border-width: calc(var(--bs-popover-arrow-width) * 0.5) 0 calc(var(--bs-popover-arrow-width) * 0.5) var(--bs-popover-arrow-height);
}	}
.bs-popover-start > .popover-arrow::before, .bs-popover-auto[data-popper-placement^=left] > .popover-arrow::before {	.bs-popover-start > .popover-arrow::before, .bs-popover-auto[data-popper-placement^=left] > .popover-arrow::before {
  right: 0;	  right: 0;
  border-width: 0.5rem 0 0.5rem 0.5rem;	  border-left-color: var(--bs-popover-arrow-border);
  border-left-color: rgba(0, 0, 0, 0.25);	
}	}
.bs-popover-start > .popover-arrow::after, .bs-popover-auto[data-popper-placement^=left] > .popover-arrow::after {	.bs-popover-start > .popover-arrow::after, .bs-popover-auto[data-popper-placement^=left] > .popover-arrow::after {
  right: 1px;	  right: var(--bs-popover-border-width);
  border-width: 0.5rem 0 0.5rem 0.5rem;	  border-left-color: var(--bs-popover-bg);
  border-left-color: #fff;	
}	}


/* rtl:end:ignore */
.popover-header {	.popover-header {
  padding: 0.5rem 1rem;	  padding: var(--bs-popover-header-padding-y) var(--bs-popover-header-padding-x);
  margin-bottom: 0;	  margin-bottom: 0;
  font-size: 1rem;	  font-size: var(--bs-popover-header-font-size);
  background-color: #f0f0f0;	  color: var(--bs-popover-header-color);
  border-bottom: 1px solid rgba(0, 0, 0, 0.2);	  background-color: var(--bs-popover-header-bg);
  border-top-left-radius: calc(0.3rem - 1px);	  border-bottom: var(--bs-popover-border-width) solid var(--bs-popover-border-color);
  border-top-right-radius: calc(0.3rem - 1px);	  border-top-left-radius: var(--bs-popover-inner-border-radius);
  border-top-right-radius: var(--bs-popover-inner-border-radius);
}	}
.popover-header:empty {	.popover-header:empty {
  display: none;	  display: none;
}	}


.popover-body {	.popover-body {
  padding: 1rem 1rem;	  padding: var(--bs-popover-body-padding-y) var(--bs-popover-body-padding-x);
  color: #212529;	  color: var(--bs-popover-body-color);
}	}


.carousel {	.carousel {
@@ -6027,7 +5824,6 @@ textarea.form-control-lg {
  display: block;	  display: block;
}	}


/* rtl:begin:ignore */	
.carousel-item-next:not(.carousel-item-start),	.carousel-item-next:not(.carousel-item-start),
.active.carousel-item-end {	.active.carousel-item-end {
  transform: translateX(100%);	  transform: translateX(100%);
@@ -6038,7 +5834,6 @@ textarea.form-control-lg {
  transform: translateX(-100%);	  transform: translateX(-100%);
}	}


/* rtl:end:ignore */	
.carousel-fade .carousel-item {	.carousel-fade .carousel-item {
  opacity: 0;	  opacity: 0;
  transition-property: opacity;	  transition-property: opacity;
@@ -6058,7 +5853,7 @@ textarea.form-control-lg {
}	}
@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
  .carousel-fade .active.carousel-item-start,	  .carousel-fade .active.carousel-item-start,
.carousel-fade .active.carousel-item-end {	  .carousel-fade .active.carousel-item-end {
    transition: none;	    transition: none;
  }	  }
}	}
@@ -6083,7 +5878,7 @@ textarea.form-control-lg {
}	}
@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
  .carousel-control-prev,	  .carousel-control-prev,
.carousel-control-next {	  .carousel-control-next {
    transition: none;	    transition: none;
  }	  }
}	}
@@ -6193,10 +5988,14 @@ textarea.form-control-lg {
  color: #000;	  color: #000;
}	}


@-webkit-keyframes spinner-border {	.spinner-grow,
  to {	.spinner-border {
    transform: rotate(360deg) /* rtl:ignore */;	  display: inline-block;
  }	  width: var(--bs-spinner-width);
  height: var(--bs-spinner-height);
  vertical-align: var(--bs-spinner-vertical-align);
  border-radius: 50%;
  animation: var(--bs-spinner-animation-speed) linear infinite var(--bs-spinner-animation-name);
}	}


@keyframes spinner-border {	@keyframes spinner-border {
@@ -6205,31 +6004,20 @@ textarea.form-control-lg {
  }	  }
}	}
.spinner-border {	.spinner-border {
  display: inline-block;	  --bs-spinner-width: 2rem;
  width: 2rem;	  --bs-spinner-height: 2rem;
  height: 2rem;	  --bs-spinner-vertical-align: -0.125em;
  vertical-align: -0.125em;	  --bs-spinner-border-width: 0.25em;
  border: 0.25em solid currentColor;	  --bs-spinner-animation-speed: 0.75s;
  --bs-spinner-animation-name: spinner-border;
  border: var(--bs-spinner-border-width) solid currentcolor;
  border-right-color: transparent;	  border-right-color: transparent;
  border-radius: 50%;	
  -webkit-animation: 0.75s linear infinite spinner-border;	
          animation: 0.75s linear infinite spinner-border;	
}	}


.spinner-border-sm {	.spinner-border-sm {
  width: 1rem;	  --bs-spinner-width: 1rem;
  height: 1rem;	  --bs-spinner-height: 1rem;
  border-width: 0.2em;	  --bs-spinner-border-width: 0.2em;
}	

@-webkit-keyframes spinner-grow {	
  0% {	
    transform: scale(0);	
  }	
  50% {	
    opacity: 1;	
    transform: none;	
  }	
}	}


@keyframes spinner-grow {	@keyframes spinner-grow {
@@ -6242,133 +6030,582 @@ textarea.form-control-lg {
  }	  }
}	}
.spinner-grow {	.spinner-grow {
  display: inline-block;	  --bs-spinner-width: 2rem;
  width: 2rem;	  --bs-spinner-height: 2rem;
  height: 2rem;	  --bs-spinner-vertical-align: -0.125em;
  vertical-align: -0.125em;	  --bs-spinner-animation-speed: 0.75s;
  background-color: currentColor;	  --bs-spinner-animation-name: spinner-grow;
  border-radius: 50%;	  background-color: currentcolor;
  opacity: 0;	  opacity: 0;
  -webkit-animation: 0.75s linear infinite spinner-grow;	
          animation: 0.75s linear infinite spinner-grow;	
}	}


.spinner-grow-sm {	.spinner-grow-sm {
  width: 1rem;	  --bs-spinner-width: 1rem;
  height: 1rem;	  --bs-spinner-height: 1rem;
}	}


@media (prefers-reduced-motion: reduce) {	@media (prefers-reduced-motion: reduce) {
  .spinner-border,	  .spinner-border,
.spinner-grow {	  .spinner-grow {
    -webkit-animation-duration: 1.5s;	    --bs-spinner-animation-speed: 1.5s;
            animation-duration: 1.5s;	
  }	  }
}	}
.offcanvas {	.offcanvas, .offcanvas-xxl, .offcanvas-xl, .offcanvas-lg, .offcanvas-md, .offcanvas-sm {
  position: fixed;	  --bs-offcanvas-zindex: 1045;
  bottom: 0;	  --bs-offcanvas-width: 400px;
  z-index: 1045;	  --bs-offcanvas-height: 30vh;
  display: flex;	  --bs-offcanvas-padding-x: 1rem;
  flex-direction: column;	  --bs-offcanvas-padding-y: 1rem;
  max-width: 100%;	  --bs-offcanvas-color: ;
  visibility: hidden;	  --bs-offcanvas-bg: #fff;
  background-color: #fff;	  --bs-offcanvas-border-width: 1px;
  background-clip: padding-box;	  --bs-offcanvas-border-color: var(--bs-border-color-translucent);
  outline: 0;	  --bs-offcanvas-box-shadow: 0 0.125rem 0.25rem rgba(0, 0, 0, 0.075);
  transition: transform 0.3s ease-in-out;	
}	}
@media (prefers-reduced-motion: reduce) {	
  .offcanvas {	@media (max-width: 575.98px) {
  .offcanvas-sm {
    position: fixed;
    bottom: 0;
    z-index: var(--bs-offcanvas-zindex);
    display: flex;
    flex-direction: column;
    max-width: 100%;
    color: var(--bs-offcanvas-color);
    visibility: hidden;
    background-color: var(--bs-offcanvas-bg);
    background-clip: padding-box;
    outline: 0;
    transition: transform 0.3s ease-in-out;
  }
}
@media (max-width: 575.98px) and (prefers-reduced-motion: reduce) {
  .offcanvas-sm {
    transition: none;	    transition: none;
  }	  }
}	}

@media (max-width: 575.98px) {
.offcanvas-backdrop {	  .offcanvas-sm.offcanvas-start {
  position: fixed;	    top: 0;
  top: 0;	    left: 0;
  left: 0;	    width: var(--bs-offcanvas-width);
  z-index: 1040;	    border-right: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
  width: 100vw;	    transform: translateX(-100%);
  height: 100vh;	  }
  background-color: #000;	
}	}
.offcanvas-backdrop.fade {	@media (max-width: 575.98px) {
  opacity: 0;	  .offcanvas-sm.offcanvas-end {
    top: 0;
    right: 0;
    width: var(--bs-offcanvas-width);
    border-left: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateX(100%);
  }
}	}
.offcanvas-backdrop.show {	@media (max-width: 575.98px) {
  opacity: 0.5;	  .offcanvas-sm.offcanvas-top {
    top: 0;
    right: 0;
    left: 0;
    height: var(--bs-offcanvas-height);
    max-height: 100%;
    border-bottom: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateY(-100%);
  }
}
@media (max-width: 575.98px) {
  .offcanvas-sm.offcanvas-bottom {
    right: 0;
    left: 0;
    height: var(--bs-offcanvas-height);
    max-height: 100%;
    border-top: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateY(100%);
  }
}
@media (max-width: 575.98px) {
  .offcanvas-sm.showing, .offcanvas-sm.show:not(.hiding) {
    transform: none;
  }
}
@media (max-width: 575.98px) {
  .offcanvas-sm.showing, .offcanvas-sm.hiding, .offcanvas-sm.show {
    visibility: visible;
  }
}
@media (min-width: 576px) {
  .offcanvas-sm {
    --bs-offcanvas-height: auto;
    --bs-offcanvas-border-width: 0;
    background-color: transparent !important;
  }
  .offcanvas-sm .offcanvas-header {
    display: none;
  }
  .offcanvas-sm .offcanvas-body {
    display: flex;
    flex-grow: 0;
    padding: 0;
    overflow-y: visible;
    background-color: transparent !important;
  }
}	}


.offcanvas-header {	@media (max-width: 767.98px) {
  display: flex;	  .offcanvas-md {
  align-items: center;	    position: fixed;
  justify-content: space-between;	    bottom: 0;
  padding: 1rem 1rem;	    z-index: var(--bs-offcanvas-zindex);
    display: flex;
    flex-direction: column;
    max-width: 100%;
    color: var(--bs-offcanvas-color);
    visibility: hidden;
    background-color: var(--bs-offcanvas-bg);
    background-clip: padding-box;
    outline: 0;
    transition: transform 0.3s ease-in-out;
  }
}
@media (max-width: 767.98px) and (prefers-reduced-motion: reduce) {
  .offcanvas-md {
    transition: none;
  }
}	}
.offcanvas-header .btn-close {	@media (max-width: 767.98px) {
  padding: 0.5rem 0.5rem;	  .offcanvas-md.offcanvas-start {
  margin-top: -0.5rem;	    top: 0;
  margin-right: -0.5rem;	    left: 0;
  margin-bottom: -0.5rem;	    width: var(--bs-offcanvas-width);
    border-right: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateX(-100%);
  }
}
@media (max-width: 767.98px) {
  .offcanvas-md.offcanvas-end {
    top: 0;
    right: 0;
    width: var(--bs-offcanvas-width);
    border-left: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateX(100%);
  }
}
@media (max-width: 767.98px) {
  .offcanvas-md.offcanvas-top {
    top: 0;
    right: 0;
    left: 0;
    height: var(--bs-offcanvas-height);
    max-height: 100%;
    border-bottom: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateY(-100%);
  }
}
@media (max-width: 767.98px) {
  .offcanvas-md.offcanvas-bottom {
    right: 0;
    left: 0;
    height: var(--bs-offcanvas-height);
    max-height: 100%;
    border-top: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateY(100%);
  }
}
@media (max-width: 767.98px) {
  .offcanvas-md.showing, .offcanvas-md.show:not(.hiding) {
    transform: none;
  }
}
@media (max-width: 767.98px) {
  .offcanvas-md.showing, .offcanvas-md.hiding, .offcanvas-md.show {
    visibility: visible;
  }
}
@media (min-width: 768px) {
  .offcanvas-md {
    --bs-offcanvas-height: auto;
    --bs-offcanvas-border-width: 0;
    background-color: transparent !important;
  }
  .offcanvas-md .offcanvas-header {
    display: none;
  }
  .offcanvas-md .offcanvas-body {
    display: flex;
    flex-grow: 0;
    padding: 0;
    overflow-y: visible;
    background-color: transparent !important;
  }
}	}


.offcanvas-title {	@media (max-width: 991.98px) {
  margin-bottom: 0;	  .offcanvas-lg {
  line-height: 1.5;	    position: fixed;
    bottom: 0;
    z-index: var(--bs-offcanvas-zindex);
    display: flex;
    flex-direction: column;
    max-width: 100%;
    color: var(--bs-offcanvas-color);
    visibility: hidden;
    background-color: var(--bs-offcanvas-bg);
    background-clip: padding-box;
    outline: 0;
    transition: transform 0.3s ease-in-out;
  }
}
@media (max-width: 991.98px) and (prefers-reduced-motion: reduce) {
  .offcanvas-lg {
    transition: none;
  }
}
@media (max-width: 991.98px) {
  .offcanvas-lg.offcanvas-start {
    top: 0;
    left: 0;
    width: var(--bs-offcanvas-width);
    border-right: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateX(-100%);
  }
}
@media (max-width: 991.98px) {
  .offcanvas-lg.offcanvas-end {
    top: 0;
    right: 0;
    width: var(--bs-offcanvas-width);
    border-left: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateX(100%);
  }
}
@media (max-width: 991.98px) {
  .offcanvas-lg.offcanvas-top {
    top: 0;
    right: 0;
    left: 0;
    height: var(--bs-offcanvas-height);
    max-height: 100%;
    border-bottom: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateY(-100%);
  }
}
@media (max-width: 991.98px) {
  .offcanvas-lg.offcanvas-bottom {
    right: 0;
    left: 0;
    height: var(--bs-offcanvas-height);
    max-height: 100%;
    border-top: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateY(100%);
  }
}
@media (max-width: 991.98px) {
  .offcanvas-lg.showing, .offcanvas-lg.show:not(.hiding) {
    transform: none;
  }
}
@media (max-width: 991.98px) {
  .offcanvas-lg.showing, .offcanvas-lg.hiding, .offcanvas-lg.show {
    visibility: visible;
  }
}
@media (min-width: 992px) {
  .offcanvas-lg {
    --bs-offcanvas-height: auto;
    --bs-offcanvas-border-width: 0;
    background-color: transparent !important;
  }
  .offcanvas-lg .offcanvas-header {
    display: none;
  }
  .offcanvas-lg .offcanvas-body {
    display: flex;
    flex-grow: 0;
    padding: 0;
    overflow-y: visible;
    background-color: transparent !important;
  }
}	}


.offcanvas-body {	@media (max-width: 1199.98px) {
  flex-grow: 1;	  .offcanvas-xl {
  padding: 1rem 1rem;	    position: fixed;
  overflow-y: auto;	    bottom: 0;
    z-index: var(--bs-offcanvas-zindex);
    display: flex;
    flex-direction: column;
    max-width: 100%;
    color: var(--bs-offcanvas-color);
    visibility: hidden;
    background-color: var(--bs-offcanvas-bg);
    background-clip: padding-box;
    outline: 0;
    transition: transform 0.3s ease-in-out;
  }
}
@media (max-width: 1199.98px) and (prefers-reduced-motion: reduce) {
  .offcanvas-xl {
    transition: none;
  }
}
@media (max-width: 1199.98px) {
  .offcanvas-xl.offcanvas-start {
    top: 0;
    left: 0;
    width: var(--bs-offcanvas-width);
    border-right: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateX(-100%);
  }
}
@media (max-width: 1199.98px) {
  .offcanvas-xl.offcanvas-end {
    top: 0;
    right: 0;
    width: var(--bs-offcanvas-width);
    border-left: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateX(100%);
  }
}
@media (max-width: 1199.98px) {
  .offcanvas-xl.offcanvas-top {
    top: 0;
    right: 0;
    left: 0;
    height: var(--bs-offcanvas-height);
    max-height: 100%;
    border-bottom: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateY(-100%);
  }
}
@media (max-width: 1199.98px) {
  .offcanvas-xl.offcanvas-bottom {
    right: 0;
    left: 0;
    height: var(--bs-offcanvas-height);
    max-height: 100%;
    border-top: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateY(100%);
  }
}
@media (max-width: 1199.98px) {
  .offcanvas-xl.showing, .offcanvas-xl.show:not(.hiding) {
    transform: none;
  }
}
@media (max-width: 1199.98px) {
  .offcanvas-xl.showing, .offcanvas-xl.hiding, .offcanvas-xl.show {
    visibility: visible;
  }
}
@media (min-width: 1200px) {
  .offcanvas-xl {
    --bs-offcanvas-height: auto;
    --bs-offcanvas-border-width: 0;
    background-color: transparent !important;
  }
  .offcanvas-xl .offcanvas-header {
    display: none;
  }
  .offcanvas-xl .offcanvas-body {
    display: flex;
    flex-grow: 0;
    padding: 0;
    overflow-y: visible;
    background-color: transparent !important;
  }
}

@media (max-width: 1399.98px) {
  .offcanvas-xxl {
    position: fixed;
    bottom: 0;
    z-index: var(--bs-offcanvas-zindex);
    display: flex;
    flex-direction: column;
    max-width: 100%;
    color: var(--bs-offcanvas-color);
    visibility: hidden;
    background-color: var(--bs-offcanvas-bg);
    background-clip: padding-box;
    outline: 0;
    transition: transform 0.3s ease-in-out;
  }
}
@media (max-width: 1399.98px) and (prefers-reduced-motion: reduce) {
  .offcanvas-xxl {
    transition: none;
  }
}
@media (max-width: 1399.98px) {
  .offcanvas-xxl.offcanvas-start {
    top: 0;
    left: 0;
    width: var(--bs-offcanvas-width);
    border-right: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateX(-100%);
  }
}
@media (max-width: 1399.98px) {
  .offcanvas-xxl.offcanvas-end {
    top: 0;
    right: 0;
    width: var(--bs-offcanvas-width);
    border-left: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateX(100%);
  }
}
@media (max-width: 1399.98px) {
  .offcanvas-xxl.offcanvas-top {
    top: 0;
    right: 0;
    left: 0;
    height: var(--bs-offcanvas-height);
    max-height: 100%;
    border-bottom: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateY(-100%);
  }
}
@media (max-width: 1399.98px) {
  .offcanvas-xxl.offcanvas-bottom {
    right: 0;
    left: 0;
    height: var(--bs-offcanvas-height);
    max-height: 100%;
    border-top: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
    transform: translateY(100%);
  }
}
@media (max-width: 1399.98px) {
  .offcanvas-xxl.showing, .offcanvas-xxl.show:not(.hiding) {
    transform: none;
  }
}
@media (max-width: 1399.98px) {
  .offcanvas-xxl.showing, .offcanvas-xxl.hiding, .offcanvas-xxl.show {
    visibility: visible;
  }
}
@media (min-width: 1400px) {
  .offcanvas-xxl {
    --bs-offcanvas-height: auto;
    --bs-offcanvas-border-width: 0;
    background-color: transparent !important;
  }
  .offcanvas-xxl .offcanvas-header {
    display: none;
  }
  .offcanvas-xxl .offcanvas-body {
    display: flex;
    flex-grow: 0;
    padding: 0;
    overflow-y: visible;
    background-color: transparent !important;
  }
}	}


.offcanvas-start {	.offcanvas {
  position: fixed;
  bottom: 0;
  z-index: var(--bs-offcanvas-zindex);
  display: flex;
  flex-direction: column;
  max-width: 100%;
  color: var(--bs-offcanvas-color);
  visibility: hidden;
  background-color: var(--bs-offcanvas-bg);
  background-clip: padding-box;
  outline: 0;
  transition: transform 0.3s ease-in-out;
}
@media (prefers-reduced-motion: reduce) {
  .offcanvas {
    transition: none;
  }
}
.offcanvas.offcanvas-start {
  top: 0;	  top: 0;
  left: 0;	  left: 0;
  width: 400px;	  width: var(--bs-offcanvas-width);
  border-right: 1px solid rgba(0, 0, 0, 0.2);	  border-right: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
  transform: translateX(-100%);	  transform: translateX(-100%);
}	}

.offcanvas.offcanvas-end {
.offcanvas-end {	
  top: 0;	  top: 0;
  right: 0;	  right: 0;
  width: 400px;	  width: var(--bs-offcanvas-width);
  border-left: 1px solid rgba(0, 0, 0, 0.2);	  border-left: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
  transform: translateX(100%);	  transform: translateX(100%);
}	}

.offcanvas.offcanvas-top {
.offcanvas-top {	
  top: 0;	  top: 0;
  right: 0;	  right: 0;
  left: 0;	  left: 0;
  height: 30vh;	  height: var(--bs-offcanvas-height);
  max-height: 100%;	  max-height: 100%;
  border-bottom: 1px solid rgba(0, 0, 0, 0.2);	  border-bottom: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
  transform: translateY(-100%);	  transform: translateY(-100%);
}	}

.offcanvas.offcanvas-bottom {
.offcanvas-bottom {	
  right: 0;	  right: 0;
  left: 0;	  left: 0;
  height: 30vh;	  height: var(--bs-offcanvas-height);
  max-height: 100%;	  max-height: 100%;
  border-top: 1px solid rgba(0, 0, 0, 0.2);	  border-top: var(--bs-offcanvas-border-width) solid var(--bs-offcanvas-border-color);
  transform: translateY(100%);	  transform: translateY(100%);
}	}

.offcanvas.showing, .offcanvas.show:not(.hiding) {
.offcanvas.show {	
  transform: none;	  transform: none;
}	}
.offcanvas.showing, .offcanvas.hiding, .offcanvas.show {
  visibility: visible;
}

.offcanvas-backdrop {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1040;
  width: 100vw;
  height: 100vh;
  background-color: #000;
}
.offcanvas-backdrop.fade {
  opacity: 0;
}
.offcanvas-backdrop.show {
  opacity: 0.5;
}

.offcanvas-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: var(--bs-offcanvas-padding-y) var(--bs-offcanvas-padding-x);
}
.offcanvas-header .btn-close {
  padding: calc(var(--bs-offcanvas-padding-y) * 0.5) calc(var(--bs-offcanvas-padding-x) * 0.5);
  margin-top: calc(-0.5 * var(--bs-offcanvas-padding-y));
  margin-right: calc(-0.5 * var(--bs-offcanvas-padding-x));
  margin-bottom: calc(-0.5 * var(--bs-offcanvas-padding-y));
}

.offcanvas-title {
  margin-bottom: 0;
  line-height: 1.5;
}

.offcanvas-body {
  flex-grow: 1;
  padding: var(--bs-offcanvas-padding-y) var(--bs-offcanvas-padding-x);
  overflow-y: auto;
}


.placeholder {	.placeholder {
  display: inline-block;	  display: inline-block;
  min-height: 1em;	  min-height: 1em;
  vertical-align: middle;	  vertical-align: middle;
  cursor: wait;	  cursor: wait;
  background-color: currentColor;	  background-color: currentcolor;
  opacity: 0.5;	  opacity: 0.5;
}	}
.placeholder.btn::before {	.placeholder.btn::before {
@@ -6389,14 +6626,7 @@ textarea.form-control-lg {
}	}


.placeholder-glow .placeholder {	.placeholder-glow .placeholder {
  -webkit-animation: placeholder-glow 2s ease-in-out infinite;	  animation: placeholder-glow 2s ease-in-out infinite;
          animation: placeholder-glow 2s ease-in-out infinite;	
}	

@-webkit-keyframes placeholder-glow {	
  50% {	
    opacity: 0.2;	
  }	
}	}


@keyframes placeholder-glow {	@keyframes placeholder-glow {
@@ -6409,15 +6639,7 @@ textarea.form-control-lg {
          mask-image: linear-gradient(130deg, #000 55%, rgba(0, 0, 0, 0.8) 75%, #000 95%);	          mask-image: linear-gradient(130deg, #000 55%, rgba(0, 0, 0, 0.8) 75%, #000 95%);
  -webkit-mask-size: 200% 100%;	  -webkit-mask-size: 200% 100%;
          mask-size: 200% 100%;	          mask-size: 200% 100%;
  -webkit-animation: placeholder-wave 2s linear infinite;	  animation: placeholder-wave 2s linear infinite;
          animation: placeholder-wave 2s linear infinite;	
}	

@-webkit-keyframes placeholder-wave {	
  100% {	
    -webkit-mask-position: -200% 0%;	
            mask-position: -200% 0%;	
  }	
}	}


@keyframes placeholder-wave {	@keyframes placeholder-wave {
@@ -6432,60 +6654,100 @@ textarea.form-control-lg {
  content: "";	  content: "";
}	}


.text-bg-primary {
  color: #fff !important;
  background-color: RGBA(13, 110, 253, var(--bs-bg-opacity, 1)) !important;
}

.text-bg-secondary {
  color: #fff !important;
  background-color: RGBA(108, 117, 125, var(--bs-bg-opacity, 1)) !important;
}

.text-bg-success {
  color: #fff !important;
  background-color: RGBA(25, 135, 84, var(--bs-bg-opacity, 1)) !important;
}

.text-bg-info {
  color: #000 !important;
  background-color: RGBA(13, 202, 240, var(--bs-bg-opacity, 1)) !important;
}

.text-bg-warning {
  color: #000 !important;
  background-color: RGBA(255, 193, 7, var(--bs-bg-opacity, 1)) !important;
}

.text-bg-danger {
  color: #fff !important;
  background-color: RGBA(220, 53, 69, var(--bs-bg-opacity, 1)) !important;
}

.text-bg-light {
  color: #000 !important;
  background-color: RGBA(248, 249, 250, var(--bs-bg-opacity, 1)) !important;
}

.text-bg-dark {
  color: #fff !important;
  background-color: RGBA(33, 37, 41, var(--bs-bg-opacity, 1)) !important;
}

.link-primary {	.link-primary {
  color: #0d6efd;	  color: #0d6efd !important;
}	}
.link-primary:hover, .link-primary:focus {	.link-primary:hover, .link-primary:focus {
  color: #0a58ca;	  color: #0a58ca !important;
}	}


.link-secondary {	.link-secondary {
  color: #6c757d;	  color: #6c757d !important;
}	}
.link-secondary:hover, .link-secondary:focus {	.link-secondary:hover, .link-secondary:focus {
  color: #565e64;	  color: #565e64 !important;
}	}


.link-success {	.link-success {
  color: #198754;	  color: #198754 !important;
}	}
.link-success:hover, .link-success:focus {	.link-success:hover, .link-success:focus {
  color: #146c43;	  color: #146c43 !important;
}	}


.link-info {	.link-info {
  color: #0dcaf0;	  color: #0dcaf0 !important;
}	}
.link-info:hover, .link-info:focus {	.link-info:hover, .link-info:focus {
  color: #3dd5f3;	  color: #3dd5f3 !important;
}	}


.link-warning {	.link-warning {
  color: #ffc107;	  color: #ffc107 !important;
}	}
.link-warning:hover, .link-warning:focus {	.link-warning:hover, .link-warning:focus {
  color: #ffcd39;	  color: #ffcd39 !important;
}	}


.link-danger {	.link-danger {
  color: #dc3545;	  color: #dc3545 !important;
}	}
.link-danger:hover, .link-danger:focus {	.link-danger:hover, .link-danger:focus {
  color: #b02a37;	  color: #b02a37 !important;
}	}


.link-light {	.link-light {
  color: #f8f9fa;	  color: #f8f9fa !important;
}	}
.link-light:hover, .link-light:focus {	.link-light:hover, .link-light:focus {
  color: #f9fafb;	  color: #f9fafb !important;
}	}


.link-dark {	.link-dark {
  color: #212529;	  color: #212529 !important;
}	}
.link-dark:hover, .link-dark:focus {	.link-dark:hover, .link-dark:focus {
  color: #1a1e21;	  color: #1a1e21 !important;
}	}


.ratio {	.ratio {
@@ -6538,51 +6800,76 @@ textarea.form-control-lg {
}	}


.sticky-top {	.sticky-top {
  position: -webkit-sticky;	
  position: sticky;	  position: sticky;
  top: 0;	  top: 0;
  z-index: 1020;	  z-index: 1020;
}	}


.sticky-bottom {
  position: sticky;
  bottom: 0;
  z-index: 1020;
}

@media (min-width: 576px) {	@media (min-width: 576px) {
  .sticky-sm-top {	  .sticky-sm-top {
    position: -webkit-sticky;	
    position: sticky;	    position: sticky;
    top: 0;	    top: 0;
    z-index: 1020;	    z-index: 1020;
  }	  }
  .sticky-sm-bottom {
    position: sticky;
    bottom: 0;
    z-index: 1020;
  }
}	}
@media (min-width: 768px) {	@media (min-width: 768px) {
  .sticky-md-top {	  .sticky-md-top {
    position: -webkit-sticky;	
    position: sticky;	    position: sticky;
    top: 0;	    top: 0;
    z-index: 1020;	    z-index: 1020;
  }	  }
  .sticky-md-bottom {
    position: sticky;
    bottom: 0;
    z-index: 1020;
  }
}	}
@media (min-width: 992px) {	@media (min-width: 992px) {
  .sticky-lg-top {	  .sticky-lg-top {
    position: -webkit-sticky;	
    position: sticky;	    position: sticky;
    top: 0;	    top: 0;
    z-index: 1020;	    z-index: 1020;
  }	  }
  .sticky-lg-bottom {
    position: sticky;
    bottom: 0;
    z-index: 1020;
  }
}	}
@media (min-width: 1200px) {	@media (min-width: 1200px) {
  .sticky-xl-top {	  .sticky-xl-top {
    position: -webkit-sticky;	
    position: sticky;	    position: sticky;
    top: 0;	    top: 0;
    z-index: 1020;	    z-index: 1020;
  }	  }
  .sticky-xl-bottom {
    position: sticky;
    bottom: 0;
    z-index: 1020;
  }
}	}
@media (min-width: 1400px) {	@media (min-width: 1400px) {
  .sticky-xxl-top {	  .sticky-xxl-top {
    position: -webkit-sticky;	
    position: sticky;	    position: sticky;
    top: 0;	    top: 0;
    z-index: 1020;	    z-index: 1020;
  }	  }
  .sticky-xxl-bottom {
    position: sticky;
    bottom: 0;
    z-index: 1020;
  }
}	}
.hstack {	.hstack {
  display: flex;	  display: flex;
@@ -6632,7 +6919,7 @@ textarea.form-control-lg {
  align-self: stretch;	  align-self: stretch;
  width: 1px;	  width: 1px;
  min-height: 1em;	  min-height: 1em;
  background-color: currentColor;	  background-color: currentcolor;
  opacity: 0.25;	  opacity: 0.25;
}	}


@@ -6781,7 +7068,6 @@ textarea.form-control-lg {
}	}


.position-sticky {	.position-sticky {
  position: -webkit-sticky !important;	
  position: sticky !important;	  position: sticky !important;
}	}


@@ -6846,99 +7132,128 @@ textarea.form-control-lg {
}	}


.border {	.border {
  border: 1px solid #dee2e6 !important;	  border: var(--bs-border-width) var(--bs-border-style) var(--bs-border-color) !important;
}	}


.border-0 {	.border-0 {
  border: 0 !important;	  border: 0 !important;
}	}


.border-top {	.border-top {
  border-top: 1px solid #dee2e6 !important;	  border-top: var(--bs-border-width) var(--bs-border-style) var(--bs-border-color) !important;
}	}


.border-top-0 {	.border-top-0 {
  border-top: 0 !important;	  border-top: 0 !important;
}	}


.border-end {	.border-end {
  border-right: 1px solid #dee2e6 !important;	  border-right: var(--bs-border-width) var(--bs-border-style) var(--bs-border-color) !important;
}	}


.border-end-0 {	.border-end-0 {
  border-right: 0 !important;	  border-right: 0 !important;
}	}


.border-bottom {	.border-bottom {
  border-bottom: 1px solid #dee2e6 !important;	  border-bottom: var(--bs-border-width) var(--bs-border-style) var(--bs-border-color) !important;
}	}


.border-bottom-0 {	.border-bottom-0 {
  border-bottom: 0 !important;	  border-bottom: 0 !important;
}	}


.border-start {	.border-start {
  border-left: 1px solid #dee2e6 !important;	  border-left: var(--bs-border-width) var(--bs-border-style) var(--bs-border-color) !important;
}	}


.border-start-0 {	.border-start-0 {
  border-left: 0 !important;	  border-left: 0 !important;
}	}


.border-primary {	.border-primary {
  border-color: #0d6efd !important;	  --bs-border-opacity: 1;
  border-color: rgba(var(--bs-primary-rgb), var(--bs-border-opacity)) !important;
}	}


.border-secondary {	.border-secondary {
  border-color: #6c757d !important;	  --bs-border-opacity: 1;
  border-color: rgba(var(--bs-secondary-rgb), var(--bs-border-opacity)) !important;
}	}


.border-success {	.border-success {
  border-color: #198754 !important;	  --bs-border-opacity: 1;
  border-color: rgba(var(--bs-success-rgb), var(--bs-border-opacity)) !important;
}	}


.border-info {	.border-info {
  border-color: #0dcaf0 !important;	  --bs-border-opacity: 1;
  border-color: rgba(var(--bs-info-rgb), var(--bs-border-opacity)) !important;
}	}


.border-warning {	.border-warning {
  border-color: #ffc107 !important;	  --bs-border-opacity: 1;
  border-color: rgba(var(--bs-warning-rgb), var(--bs-border-opacity)) !important;
}	}


.border-danger {	.border-danger {
  border-color: #dc3545 !important;	  --bs-border-opacity: 1;
  border-color: rgba(var(--bs-danger-rgb), var(--bs-border-opacity)) !important;
}	}


.border-light {	.border-light {
  border-color: #f8f9fa !important;	  --bs-border-opacity: 1;
  border-color: rgba(var(--bs-light-rgb), var(--bs-border-opacity)) !important;
}	}


.border-dark {	.border-dark {
  border-color: #212529 !important;	  --bs-border-opacity: 1;
  border-color: rgba(var(--bs-dark-rgb), var(--bs-border-opacity)) !important;
}	}


.border-white {	.border-white {
  border-color: #fff !important;	  --bs-border-opacity: 1;
  border-color: rgba(var(--bs-white-rgb), var(--bs-border-opacity)) !important;
}	}


.border-1 {	.border-1 {
  border-width: 1px !important;	  --bs-border-width: 1px;
}	}


.border-2 {	.border-2 {
  border-width: 2px !important;	  --bs-border-width: 2px;
}

.border-3 {
  --bs-border-width: 3px;
}

.border-4 {
  --bs-border-width: 4px;
}

.border-5 {
  --bs-border-width: 5px;
}

.border-opacity-10 {
  --bs-border-opacity: 0.1;
}

.border-opacity-25 {
  --bs-border-opacity: 0.25;
}	}


.border-3 {	.border-opacity-50 {
  border-width: 3px !important;	  --bs-border-opacity: 0.5;
}	}


.border-4 {	.border-opacity-75 {
  border-width: 4px !important;	  --bs-border-opacity: 0.75;
}	}


.border-5 {	.border-opacity-100 {
  border-width: 5px !important;	  --bs-border-opacity: 1;
}	}


.w-25 {	.w-25 {
@@ -7053,30 +7368,6 @@ textarea.form-control-lg {
  flex-wrap: wrap-reverse !important;	  flex-wrap: wrap-reverse !important;
}	}


.gap-0 {	
  gap: 0 !important;	
}	

.gap-1 {	
  gap: 0.25rem !important;	
}	

.gap-2 {	
  gap: 0.5rem !important;	
}	

.gap-3 {	
  gap: 1rem !important;	
}	

.gap-4 {	
  gap: 1.5rem !important;	
}	

.gap-5 {	
  gap: 3rem !important;	
}	

.justify-content-start {	.justify-content-start {
  justify-content: flex-start !important;	  justify-content: flex-start !important;
}	}
@@ -7591,6 +7882,30 @@ textarea.form-control-lg {
  padding-left: 3rem !important;	  padding-left: 3rem !important;
}	}


.gap-0 {
  gap: 0 !important;
}

.gap-1 {
  gap: 0.25rem !important;
}

.gap-2 {
  gap: 0.5rem !important;
}

.gap-3 {
  gap: 1rem !important;
}

.gap-4 {
  gap: 1.5rem !important;
}

.gap-5 {
  gap: 3rem !important;
}

.font-monospace {	.font-monospace {
  font-family: var(--bs-font-monospace) !important;	  font-family: var(--bs-font-monospace) !important;
}	}
@@ -7643,6 +7958,10 @@ textarea.form-control-lg {
  font-weight: 700 !important;	  font-weight: 700 !important;
}	}


.fw-semibold {
  font-weight: 600 !important;
}

.fw-bolder {	.fw-bolder {
  font-weight: bolder !important;	  font-weight: bolder !important;
}	}
@@ -7898,14 +8217,12 @@ textarea.form-control-lg {
.user-select-auto {	.user-select-auto {
  -webkit-user-select: auto !important;	  -webkit-user-select: auto !important;
     -moz-user-select: auto !important;	     -moz-user-select: auto !important;
      -ms-user-select: auto !important;	
          user-select: auto !important;	          user-select: auto !important;
}	}


.user-select-none {	.user-select-none {
  -webkit-user-select: none !important;	  -webkit-user-select: none !important;
     -moz-user-select: none !important;	     -moz-user-select: none !important;
      -ms-user-select: none !important;	
          user-select: none !important;	          user-select: none !important;
}	}


@@ -7918,51 +8235,59 @@ textarea.form-control-lg {
}	}


.rounded {	.rounded {
  border-radius: 0.25rem !important;	  border-radius: var(--bs-border-radius) !important;
}	}


.rounded-0 {	.rounded-0 {
  border-radius: 0 !important;	  border-radius: 0 !important;
}	}


.rounded-1 {	.rounded-1 {
  border-radius: 0.2rem !important;	  border-radius: var(--bs-border-radius-sm) !important;
}	}


.rounded-2 {	.rounded-2 {
  border-radius: 0.25rem !important;	  border-radius: var(--bs-border-radius) !important;
}	}


.rounded-3 {	.rounded-3 {
  border-radius: 0.3rem !important;	  border-radius: var(--bs-border-radius-lg) !important;
}

.rounded-4 {
  border-radius: var(--bs-border-radius-xl) !important;
}

.rounded-5 {
  border-radius: var(--bs-border-radius-2xl) !important;
}	}


.rounded-circle {	.rounded-circle {
  border-radius: 50% !important;	  border-radius: 50% !important;
}	}


.rounded-pill {	.rounded-pill {
  border-radius: 50rem !important;	  border-radius: var(--bs-border-radius-pill) !important;
}	}


.rounded-top {	.rounded-top {
  border-top-left-radius: 0.25rem !important;	  border-top-left-radius: var(--bs-border-radius) !important;
  border-top-right-radius: 0.25rem !important;	  border-top-right-radius: var(--bs-border-radius) !important;
}	}


.rounded-end {	.rounded-end {
  border-top-right-radius: 0.25rem !important;	  border-top-right-radius: var(--bs-border-radius) !important;
  border-bottom-right-radius: 0.25rem !important;	  border-bottom-right-radius: var(--bs-border-radius) !important;
}	}


.rounded-bottom {	.rounded-bottom {
  border-bottom-right-radius: 0.25rem !important;	  border-bottom-right-radius: var(--bs-border-radius) !important;
  border-bottom-left-radius: 0.25rem !important;	  border-bottom-left-radius: var(--bs-border-radius) !important;
}	}


.rounded-start {	.rounded-start {
  border-bottom-left-radius: 0.25rem !important;	  border-bottom-left-radius: var(--bs-border-radius) !important;
  border-top-left-radius: 0.25rem !important;	  border-top-left-radius: var(--bs-border-radius) !important;
}	}


.visible {	.visible {
@@ -7977,649 +8302,494 @@ textarea.form-control-lg {
  .float-sm-start {	  .float-sm-start {
    float: left !important;	    float: left !important;
  }	  }

  .float-sm-end {	  .float-sm-end {
    float: right !important;	    float: right !important;
  }	  }

  .float-sm-none {	  .float-sm-none {
    float: none !important;	    float: none !important;
  }	  }

  .d-sm-inline {	  .d-sm-inline {
    display: inline !important;	    display: inline !important;
  }	  }

  .d-sm-inline-block {	  .d-sm-inline-block {
    display: inline-block !important;	    display: inline-block !important;
  }	  }

  .d-sm-block {	  .d-sm-block {
    display: block !important;	    display: block !important;
  }	  }

  .d-sm-grid {	  .d-sm-grid {
    display: grid !important;	    display: grid !important;
  }	  }

  .d-sm-table {	  .d-sm-table {
    display: table !important;	    display: table !important;
  }	  }

  .d-sm-table-row {	  .d-sm-table-row {
    display: table-row !important;	    display: table-row !important;
  }	  }

  .d-sm-table-cell {	  .d-sm-table-cell {
    display: table-cell !important;	    display: table-cell !important;
  }	  }

  .d-sm-flex {	  .d-sm-flex {
    display: flex !important;	    display: flex !important;
  }	  }

  .d-sm-inline-flex {	  .d-sm-inline-flex {
    display: inline-flex !important;	    display: inline-flex !important;
  }	  }

  .d-sm-none {	  .d-sm-none {
    display: none !important;	    display: none !important;
  }	  }

  .flex-sm-fill {	  .flex-sm-fill {
    flex: 1 1 auto !important;	    flex: 1 1 auto !important;
  }	  }

  .flex-sm-row {	  .flex-sm-row {
    flex-direction: row !important;	    flex-direction: row !important;
  }	  }

  .flex-sm-column {	  .flex-sm-column {
    flex-direction: column !important;	    flex-direction: column !important;
  }	  }

  .flex-sm-row-reverse {	  .flex-sm-row-reverse {
    flex-direction: row-reverse !important;	    flex-direction: row-reverse !important;
  }	  }

  .flex-sm-column-reverse {	  .flex-sm-column-reverse {
    flex-direction: column-reverse !important;	    flex-direction: column-reverse !important;
  }	  }

  .flex-sm-grow-0 {	  .flex-sm-grow-0 {
    flex-grow: 0 !important;	    flex-grow: 0 !important;
  }	  }

  .flex-sm-grow-1 {	  .flex-sm-grow-1 {
    flex-grow: 1 !important;	    flex-grow: 1 !important;
  }	  }

  .flex-sm-shrink-0 {	  .flex-sm-shrink-0 {
    flex-shrink: 0 !important;	    flex-shrink: 0 !important;
  }	  }

  .flex-sm-shrink-1 {	  .flex-sm-shrink-1 {
    flex-shrink: 1 !important;	    flex-shrink: 1 !important;
  }	  }

  .flex-sm-wrap {	  .flex-sm-wrap {
    flex-wrap: wrap !important;	    flex-wrap: wrap !important;
  }	  }

  .flex-sm-nowrap {	  .flex-sm-nowrap {
    flex-wrap: nowrap !important;	    flex-wrap: nowrap !important;
  }	  }

  .flex-sm-wrap-reverse {	  .flex-sm-wrap-reverse {
    flex-wrap: wrap-reverse !important;	    flex-wrap: wrap-reverse !important;
  }	  }

  .gap-sm-0 {	
    gap: 0 !important;	
  }	

  .gap-sm-1 {	
    gap: 0.25rem !important;	
  }	

  .gap-sm-2 {	
    gap: 0.5rem !important;	
  }	

  .gap-sm-3 {	
    gap: 1rem !important;	
  }	

  .gap-sm-4 {	
    gap: 1.5rem !important;	
  }	

  .gap-sm-5 {	
    gap: 3rem !important;	
  }	

  .justify-content-sm-start {	  .justify-content-sm-start {
    justify-content: flex-start !important;	    justify-content: flex-start !important;
  }	  }

  .justify-content-sm-end {	  .justify-content-sm-end {
    justify-content: flex-end !important;	    justify-content: flex-end !important;
  }	  }

  .justify-content-sm-center {	  .justify-content-sm-center {
    justify-content: center !important;	    justify-content: center !important;
  }	  }

  .justify-content-sm-between {	  .justify-content-sm-between {
    justify-content: space-between !important;	    justify-content: space-between !important;
  }	  }

  .justify-content-sm-around {	  .justify-content-sm-around {
    justify-content: space-around !important;	    justify-content: space-around !important;
  }	  }

  .justify-content-sm-evenly {	  .justify-content-sm-evenly {
    justify-content: space-evenly !important;	    justify-content: space-evenly !important;
  }	  }

  .align-items-sm-start {	  .align-items-sm-start {
    align-items: flex-start !important;	    align-items: flex-start !important;
  }	  }

  .align-items-sm-end {	  .align-items-sm-end {
    align-items: flex-end !important;	    align-items: flex-end !important;
  }	  }

  .align-items-sm-center {	  .align-items-sm-center {
    align-items: center !important;	    align-items: center !important;
  }	  }

  .align-items-sm-baseline {	  .align-items-sm-baseline {
    align-items: baseline !important;	    align-items: baseline !important;
  }	  }

  .align-items-sm-stretch {	  .align-items-sm-stretch {
    align-items: stretch !important;	    align-items: stretch !important;
  }	  }

  .align-content-sm-start {	  .align-content-sm-start {
    align-content: flex-start !important;	    align-content: flex-start !important;
  }	  }

  .align-content-sm-end {	  .align-content-sm-end {
    align-content: flex-end !important;	    align-content: flex-end !important;
  }	  }

  .align-content-sm-center {	  .align-content-sm-center {
    align-content: center !important;	    align-content: center !important;
  }	  }

  .align-content-sm-between {	  .align-content-sm-between {
    align-content: space-between !important;	    align-content: space-between !important;
  }	  }

  .align-content-sm-around {	  .align-content-sm-around {
    align-content: space-around !important;	    align-content: space-around !important;
  }	  }

  .align-content-sm-stretch {	  .align-content-sm-stretch {
    align-content: stretch !important;	    align-content: stretch !important;
  }	  }

  .align-self-sm-auto {	  .align-self-sm-auto {
    align-self: auto !important;	    align-self: auto !important;
  }	  }

  .align-self-sm-start {	  .align-self-sm-start {
    align-self: flex-start !important;	    align-self: flex-start !important;
  }	  }

  .align-self-sm-end {	  .align-self-sm-end {
    align-self: flex-end !important;	    align-self: flex-end !important;
  }	  }

  .align-self-sm-center {	  .align-self-sm-center {
    align-self: center !important;	    align-self: center !important;
  }	  }

  .align-self-sm-baseline {	  .align-self-sm-baseline {
    align-self: baseline !important;	    align-self: baseline !important;
  }	  }

  .align-self-sm-stretch {	  .align-self-sm-stretch {
    align-self: stretch !important;	    align-self: stretch !important;
  }	  }

  .order-sm-first {	  .order-sm-first {
    order: -1 !important;	    order: -1 !important;
  }	  }

  .order-sm-0 {	  .order-sm-0 {
    order: 0 !important;	    order: 0 !important;
  }	  }

  .order-sm-1 {	  .order-sm-1 {
    order: 1 !important;	    order: 1 !important;
  }	  }

  .order-sm-2 {	  .order-sm-2 {
    order: 2 !important;	    order: 2 !important;
  }	  }

  .order-sm-3 {	  .order-sm-3 {
    order: 3 !important;	    order: 3 !important;
  }	  }

  .order-sm-4 {	  .order-sm-4 {
    order: 4 !important;	    order: 4 !important;
  }	  }

  .order-sm-5 {	  .order-sm-5 {
    order: 5 !important;	    order: 5 !important;
  }	  }

  .order-sm-last {	  .order-sm-last {
    order: 6 !important;	    order: 6 !important;
  }	  }

  .m-sm-0 {	  .m-sm-0 {
    margin: 0 !important;	    margin: 0 !important;
  }	  }

  .m-sm-1 {	  .m-sm-1 {
    margin: 0.25rem !important;	    margin: 0.25rem !important;
  }	  }

  .m-sm-2 {	  .m-sm-2 {
    margin: 0.5rem !important;	    margin: 0.5rem !important;
  }	  }

  .m-sm-3 {	  .m-sm-3 {
    margin: 1rem !important;	    margin: 1rem !important;
  }	  }

  .m-sm-4 {	  .m-sm-4 {
    margin: 1.5rem !important;	    margin: 1.5rem !important;
  }	  }

  .m-sm-5 {	  .m-sm-5 {
    margin: 3rem !important;	    margin: 3rem !important;
  }	  }

  .m-sm-auto {	  .m-sm-auto {
    margin: auto !important;	    margin: auto !important;
  }	  }

  .mx-sm-0 {	  .mx-sm-0 {
    margin-right: 0 !important;	    margin-right: 0 !important;
    margin-left: 0 !important;	    margin-left: 0 !important;
  }	  }

  .mx-sm-1 {	  .mx-sm-1 {
    margin-right: 0.25rem !important;	    margin-right: 0.25rem !important;
    margin-left: 0.25rem !important;	    margin-left: 0.25rem !important;
  }	  }

  .mx-sm-2 {	  .mx-sm-2 {
    margin-right: 0.5rem !important;	    margin-right: 0.5rem !important;
    margin-left: 0.5rem !important;	    margin-left: 0.5rem !important;
  }	  }

  .mx-sm-3 {	  .mx-sm-3 {
    margin-right: 1rem !important;	    margin-right: 1rem !important;
    margin-left: 1rem !important;	    margin-left: 1rem !important;
  }	  }

  .mx-sm-4 {	  .mx-sm-4 {
    margin-right: 1.5rem !important;	    margin-right: 1.5rem !important;
    margin-left: 1.5rem !important;	    margin-left: 1.5rem !important;
  }	  }

  .mx-sm-5 {	  .mx-sm-5 {
    margin-right: 3rem !important;	    margin-right: 3rem !important;
    margin-left: 3rem !important;	    margin-left: 3rem !important;
  }	  }

  .mx-sm-auto {	  .mx-sm-auto {
    margin-right: auto !important;	    margin-right: auto !important;
    margin-left: auto !important;	    margin-left: auto !important;
  }	  }

  .my-sm-0 {	  .my-sm-0 {
    margin-top: 0 !important;	    margin-top: 0 !important;
    margin-bottom: 0 !important;	    margin-bottom: 0 !important;
  }	  }

  .my-sm-1 {	  .my-sm-1 {
    margin-top: 0.25rem !important;	    margin-top: 0.25rem !important;
    margin-bottom: 0.25rem !important;	    margin-bottom: 0.25rem !important;
  }	  }

  .my-sm-2 {	  .my-sm-2 {
    margin-top: 0.5rem !important;	    margin-top: 0.5rem !important;
    margin-bottom: 0.5rem !important;	    margin-bottom: 0.5rem !important;
  }	  }

  .my-sm-3 {	  .my-sm-3 {
    margin-top: 1rem !important;	    margin-top: 1rem !important;
    margin-bottom: 1rem !important;	    margin-bottom: 1rem !important;
  }	  }

  .my-sm-4 {	  .my-sm-4 {
    margin-top: 1.5rem !important;	    margin-top: 1.5rem !important;
    margin-bottom: 1.5rem !important;	    margin-bottom: 1.5rem !important;
  }	  }

  .my-sm-5 {	  .my-sm-5 {
    margin-top: 3rem !important;	    margin-top: 3rem !important;
    margin-bottom: 3rem !important;	    margin-bottom: 3rem !important;
  }	  }

  .my-sm-auto {	  .my-sm-auto {
    margin-top: auto !important;	    margin-top: auto !important;
    margin-bottom: auto !important;	    margin-bottom: auto !important;
  }	  }

  .mt-sm-0 {	  .mt-sm-0 {
    margin-top: 0 !important;	    margin-top: 0 !important;
  }	  }

  .mt-sm-1 {	  .mt-sm-1 {
    margin-top: 0.25rem !important;	    margin-top: 0.25rem !important;
  }	  }

  .mt-sm-2 {	  .mt-sm-2 {
    margin-top: 0.5rem !important;	    margin-top: 0.5rem !important;
  }	  }

  .mt-sm-3 {	  .mt-sm-3 {
    margin-top: 1rem !important;	    margin-top: 1rem !important;
  }	  }

  .mt-sm-4 {	  .mt-sm-4 {
    margin-top: 1.5rem !important;	    margin-top: 1.5rem !important;
  }	  }

  .mt-sm-5 {	  .mt-sm-5 {
    margin-top: 3rem !important;	    margin-top: 3rem !important;
  }	  }

  .mt-sm-auto {	  .mt-sm-auto {
    margin-top: auto !important;	    margin-top: auto !important;
  }	  }

  .me-sm-0 {	  .me-sm-0 {
    margin-right: 0 !important;	    margin-right: 0 !important;
  }	  }

  .me-sm-1 {	  .me-sm-1 {
    margin-right: 0.25rem !important;	    margin-right: 0.25rem !important;
  }	  }

  .me-sm-2 {	  .me-sm-2 {
    margin-right: 0.5rem !important;	    margin-right: 0.5rem !important;
  }	  }

  .me-sm-3 {	  .me-sm-3 {
    margin-right: 1rem !important;	    margin-right: 1rem !important;
  }	  }

  .me-sm-4 {	  .me-sm-4 {
    margin-right: 1.5rem !important;	    margin-right: 1.5rem !important;
  }	  }

  .me-sm-5 {	  .me-sm-5 {
    margin-right: 3rem !important;	    margin-right: 3rem !important;
  }	  }

  .me-sm-auto {	  .me-sm-auto {
    margin-right: auto !important;	    margin-right: auto !important;
  }	  }

  .mb-sm-0 {	  .mb-sm-0 {
    margin-bottom: 0 !important;	    margin-bottom: 0 !important;
  }	  }

  .mb-sm-1 {	  .mb-sm-1 {
    margin-bottom: 0.25rem !important;	    margin-bottom: 0.25rem !important;
  }	  }

  .mb-sm-2 {	  .mb-sm-2 {
    margin-bottom: 0.5rem !important;	    margin-bottom: 0.5rem !important;
  }	  }

  .mb-sm-3 {	  .mb-sm-3 {
    margin-bottom: 1rem !important;	    margin-bottom: 1rem !important;
  }	  }

  .mb-sm-4 {	  .mb-sm-4 {
    margin-bottom: 1.5rem !important;	    margin-bottom: 1.5rem !important;
  }	  }

  .mb-sm-5 {	  .mb-sm-5 {
    margin-bottom: 3rem !important;	    margin-bottom: 3rem !important;
  }	  }

  .mb-sm-auto {	  .mb-sm-auto {
    margin-bottom: auto !important;	    margin-bottom: auto !important;
  }	  }

  .ms-sm-0 {	  .ms-sm-0 {
    margin-left: 0 !important;	    margin-left: 0 !important;
  }	  }

  .ms-sm-1 {	  .ms-sm-1 {
    margin-left: 0.25rem !important;	    margin-left: 0.25rem !important;
  }	  }

  .ms-sm-2 {	  .ms-sm-2 {
    margin-left: 0.5rem !important;	    margin-left: 0.5rem !important;
  }	  }

  .ms-sm-3 {	  .ms-sm-3 {
    margin-left: 1rem !important;	    margin-left: 1rem !important;
  }	  }

  .ms-sm-4 {	  .ms-sm-4 {
    margin-left: 1.5rem !important;	    margin-left: 1.5rem !important;
  }	  }

  .ms-sm-5 {	  .ms-sm-5 {
    margin-left: 3rem !important;	    margin-left: 3rem !important;
  }	  }

  .ms-sm-auto {	  .ms-sm-auto {
    margin-left: auto !important;	    margin-left: auto !important;
  }	  }

  .p-sm-0 {	  .p-sm-0 {
    padding: 0 !important;	    padding: 0 !important;
  }	  }

  .p-sm-1 {	  .p-sm-1 {
    padding: 0.25rem !important;	    padding: 0.25rem !important;
  }	  }

  .p-sm-2 {	  .p-sm-2 {
    padding: 0.5rem !important;	    padding: 0.5rem !important;
  }	  }

  .p-sm-3 {	  .p-sm-3 {
    padding: 1rem !important;	    padding: 1rem !important;
  }	  }

  .p-sm-4 {	  .p-sm-4 {
    padding: 1.5rem !important;	    padding: 1.5rem !important;
  }	  }

  .p-sm-5 {	  .p-sm-5 {
    padding: 3rem !important;	    padding: 3rem !important;
  }	  }

  .px-sm-0 {	  .px-sm-0 {
    padding-right: 0 !important;	    padding-right: 0 !important;
    padding-left: 0 !important;	    padding-left: 0 !important;
  }	  }

  .px-sm-1 {	  .px-sm-1 {
    padding-right: 0.25rem !important;	    padding-right: 0.25rem !important;
    padding-left: 0.25rem !important;	    padding-left: 0.25rem !important;
  }	  }

  .px-sm-2 {	  .px-sm-2 {
    padding-right: 0.5rem !important;	    padding-right: 0.5rem !important;
    padding-left: 0.5rem !important;	    padding-left: 0.5rem !important;
  }	  }

  .px-sm-3 {	  .px-sm-3 {
    padding-right: 1rem !important;	    padding-right: 1rem !important;
    padding-left: 1rem !important;	    padding-left: 1rem !important;
  }	  }

  .px-sm-4 {	  .px-sm-4 {
    padding-right: 1.5rem !important;	    padding-right: 1.5rem !important;
    padding-left: 1.5rem !important;	    padding-left: 1.5rem !important;
  }	  }

  .px-sm-5 {	  .px-sm-5 {
    padding-right: 3rem !important;	    padding-right: 3rem !important;
    padding-left: 3rem !important;	    padding-left: 3rem !important;
  }	  }

  .py-sm-0 {	  .py-sm-0 {
    padding-top: 0 !important;	    padding-top: 0 !important;
    padding-bottom: 0 !important;	    padding-bottom: 0 !important;
  }	  }

  .py-sm-1 {	  .py-sm-1 {
    padding-top: 0.25rem !important;	    padding-top: 0.25rem !important;
    padding-bottom: 0.25rem !important;	    padding-bottom: 0.25rem !important;
  }	  }

  .py-sm-2 {	  .py-sm-2 {
    padding-top: 0.5rem !important;	    padding-top: 0.5rem !important;
    padding-bottom: 0.5rem !important;	    padding-bottom: 0.5rem !important;
  }	  }

  .py-sm-3 {	  .py-sm-3 {
    padding-top: 1rem !important;	    padding-top: 1rem !important;
    padding-bottom: 1rem !important;	    padding-bottom: 1rem !important;
  }	  }

  .py-sm-4 {	  .py-sm-4 {
    padding-top: 1.5rem !important;	    padding-top: 1.5rem !important;
    padding-bottom: 1.5rem !important;	    padding-bottom: 1.5rem !important;
  }	  }

  .py-sm-5 {	  .py-sm-5 {
    padding-top: 3rem !important;	    padding-top: 3rem !important;
    padding-bottom: 3rem !important;	    padding-bottom: 3rem !important;
  }	  }

  .pt-sm-0 {	  .pt-sm-0 {
    padding-top: 0 !important;	    padding-top: 0 !important;
  }	  }

  .pt-sm-1 {	  .pt-sm-1 {
    padding-top: 0.25rem !important;	    padding-top: 0.25rem !important;
  }	  }

  .pt-sm-2 {	  .pt-sm-2 {
    padding-top: 0.5rem !important;	    padding-top: 0.5rem !important;
  }	  }

  .pt-sm-3 {	  .pt-sm-3 {
    padding-top: 1rem !important;	    padding-top: 1rem !important;
  }	  }

  .pt-sm-4 {	  .pt-sm-4 {
    padding-top: 1.5rem !important;	    padding-top: 1.5rem !important;
  }	  }

  .pt-sm-5 {	  .pt-sm-5 {
    padding-top: 3rem !important;	    padding-top: 3rem !important;
  }	  }

  .pe-sm-0 {	  .pe-sm-0 {
    padding-right: 0 !important;	    padding-right: 0 !important;
  }	  }

  .pe-sm-1 {	  .pe-sm-1 {
    padding-right: 0.25rem !important;	    padding-right: 0.25rem !important;
  }	  }

  .pe-sm-2 {	  .pe-sm-2 {
    padding-right: 0.5rem !important;	    padding-right: 0.5rem !important;
  }	  }

  .pe-sm-3 {	  .pe-sm-3 {
    padding-right: 1rem !important;	    padding-right: 1rem !important;
  }	  }

  .pe-sm-4 {	  .pe-sm-4 {
    padding-right: 1.5rem !important;	    padding-right: 1.5rem !important;
  }	  }

  .pe-sm-5 {	  .pe-sm-5 {
    padding-right: 3rem !important;	    padding-right: 3rem !important;
  }	  }

  .pb-sm-0 {	  .pb-sm-0 {
    padding-bottom: 0 !important;	    padding-bottom: 0 !important;
  }	  }

  .pb-sm-1 {	  .pb-sm-1 {
    padding-bottom: 0.25rem !important;	    padding-bottom: 0.25rem !important;
  }	  }

  .pb-sm-2 {	  .pb-sm-2 {
    padding-bottom: 0.5rem !important;	    padding-bottom: 0.5rem !important;
  }	  }

  .pb-sm-3 {	  .pb-sm-3 {
    padding-bottom: 1rem !important;	    padding-bottom: 1rem !important;
  }	  }

  .pb-sm-4 {	  .pb-sm-4 {
    padding-bottom: 1.5rem !important;	    padding-bottom: 1.5rem !important;
  }	  }

  .pb-sm-5 {	  .pb-sm-5 {
    padding-bottom: 3rem !important;	    padding-bottom: 3rem !important;
  }	  }

  .ps-sm-0 {	  .ps-sm-0 {
    padding-left: 0 !important;	    padding-left: 0 !important;
  }	  }

  .ps-sm-1 {	  .ps-sm-1 {
    padding-left: 0.25rem !important;	    padding-left: 0.25rem !important;
  }	  }

  .ps-sm-2 {	  .ps-sm-2 {
    padding-left: 0.5rem !important;	    padding-left: 0.5rem !important;
  }	  }

  .ps-sm-3 {	  .ps-sm-3 {
    padding-left: 1rem !important;	    padding-left: 1rem !important;
  }	  }

  .ps-sm-4 {	  .ps-sm-4 {
    padding-left: 1.5rem !important;	    padding-left: 1.5rem !important;
  }	  }

  .ps-sm-5 {	  .ps-sm-5 {
    padding-left: 3rem !important;	    padding-left: 3rem !important;
  }	  }

  .gap-sm-0 {
    gap: 0 !important;
  }
  .gap-sm-1 {
    gap: 0.25rem !important;
  }
  .gap-sm-2 {
    gap: 0.5rem !important;
  }
  .gap-sm-3 {
    gap: 1rem !important;
  }
  .gap-sm-4 {
    gap: 1.5rem !important;
  }
  .gap-sm-5 {
    gap: 3rem !important;
  }
  .text-sm-start {	  .text-sm-start {
    text-align: left !important;	    text-align: left !important;
  }	  }

  .text-sm-end {	  .text-sm-end {
    text-align: right !important;	    text-align: right !important;
  }	  }

  .text-sm-center {	  .text-sm-center {
    text-align: center !important;	    text-align: center !important;
  }	  }
@@ -8628,649 +8798,494 @@ textarea.form-control-lg {
  .float-md-start {	  .float-md-start {
    float: left !important;	    float: left !important;
  }	  }

  .float-md-end {	  .float-md-end {
    float: right !important;	    float: right !important;
  }	  }

  .float-md-none {	  .float-md-none {
    float: none !important;	    float: none !important;
  }	  }

  .d-md-inline {	  .d-md-inline {
    display: inline !important;	    display: inline !important;
  }	  }

  .d-md-inline-block {	  .d-md-inline-block {
    display: inline-block !important;	    display: inline-block !important;
  }	  }

  .d-md-block {	  .d-md-block {
    display: block !important;	    display: block !important;
  }	  }

  .d-md-grid {	  .d-md-grid {
    display: grid !important;	    display: grid !important;
  }	  }

  .d-md-table {	  .d-md-table {
    display: table !important;	    display: table !important;
  }	  }

  .d-md-table-row {	  .d-md-table-row {
    display: table-row !important;	    display: table-row !important;
  }	  }

  .d-md-table-cell {	  .d-md-table-cell {
    display: table-cell !important;	    display: table-cell !important;
  }	  }

  .d-md-flex {	  .d-md-flex {
    display: flex !important;	    display: flex !important;
  }	  }

  .d-md-inline-flex {	  .d-md-inline-flex {
    display: inline-flex !important;	    display: inline-flex !important;
  }	  }

  .d-md-none {	  .d-md-none {
    display: none !important;	    display: none !important;
  }	  }

  .flex-md-fill {	  .flex-md-fill {
    flex: 1 1 auto !important;	    flex: 1 1 auto !important;
  }	  }

  .flex-md-row {	  .flex-md-row {
    flex-direction: row !important;	    flex-direction: row !important;
  }	  }

  .flex-md-column {	  .flex-md-column {
    flex-direction: column !important;	    flex-direction: column !important;
  }	  }

  .flex-md-row-reverse {	  .flex-md-row-reverse {
    flex-direction: row-reverse !important;	    flex-direction: row-reverse !important;
  }	  }

  .flex-md-column-reverse {	  .flex-md-column-reverse {
    flex-direction: column-reverse !important;	    flex-direction: column-reverse !important;
  }	  }

  .flex-md-grow-0 {	  .flex-md-grow-0 {
    flex-grow: 0 !important;	    flex-grow: 0 !important;
  }	  }

  .flex-md-grow-1 {	  .flex-md-grow-1 {
    flex-grow: 1 !important;	    flex-grow: 1 !important;
  }	  }

  .flex-md-shrink-0 {	  .flex-md-shrink-0 {
    flex-shrink: 0 !important;	    flex-shrink: 0 !important;
  }	  }

  .flex-md-shrink-1 {	  .flex-md-shrink-1 {
    flex-shrink: 1 !important;	    flex-shrink: 1 !important;
  }	  }

  .flex-md-wrap {	  .flex-md-wrap {
    flex-wrap: wrap !important;	    flex-wrap: wrap !important;
  }	  }

  .flex-md-nowrap {	  .flex-md-nowrap {
    flex-wrap: nowrap !important;	    flex-wrap: nowrap !important;
  }	  }

  .flex-md-wrap-reverse {	  .flex-md-wrap-reverse {
    flex-wrap: wrap-reverse !important;	    flex-wrap: wrap-reverse !important;
  }	  }

  .gap-md-0 {	
    gap: 0 !important;	
  }	

  .gap-md-1 {	
    gap: 0.25rem !important;	
  }	

  .gap-md-2 {	
    gap: 0.5rem !important;	
  }	

  .gap-md-3 {	
    gap: 1rem !important;	
  }	

  .gap-md-4 {	
    gap: 1.5rem !important;	
  }	

  .gap-md-5 {	
    gap: 3rem !important;	
  }	

  .justify-content-md-start {	  .justify-content-md-start {
    justify-content: flex-start !important;	    justify-content: flex-start !important;
  }	  }

  .justify-content-md-end {	  .justify-content-md-end {
    justify-content: flex-end !important;	    justify-content: flex-end !important;
  }	  }

  .justify-content-md-center {	  .justify-content-md-center {
    justify-content: center !important;	    justify-content: center !important;
  }	  }

  .justify-content-md-between {	  .justify-content-md-between {
    justify-content: space-between !important;	    justify-content: space-between !important;
  }	  }

  .justify-content-md-around {	  .justify-content-md-around {
    justify-content: space-around !important;	    justify-content: space-around !important;
  }	  }

  .justify-content-md-evenly {	  .justify-content-md-evenly {
    justify-content: space-evenly !important;	    justify-content: space-evenly !important;
  }	  }

  .align-items-md-start {	  .align-items-md-start {
    align-items: flex-start !important;	    align-items: flex-start !important;
  }	  }

  .align-items-md-end {	  .align-items-md-end {
    align-items: flex-end !important;	    align-items: flex-end !important;
  }	  }

  .align-items-md-center {	  .align-items-md-center {
    align-items: center !important;	    align-items: center !important;
  }	  }

  .align-items-md-baseline {	  .align-items-md-baseline {
    align-items: baseline !important;	    align-items: baseline !important;
  }	  }

  .align-items-md-stretch {	  .align-items-md-stretch {
    align-items: stretch !important;	    align-items: stretch !important;
  }	  }

  .align-content-md-start {	  .align-content-md-start {
    align-content: flex-start !important;	    align-content: flex-start !important;
  }	  }

  .align-content-md-end {	  .align-content-md-end {
    align-content: flex-end !important;	    align-content: flex-end !important;
  }	  }

  .align-content-md-center {	  .align-content-md-center {
    align-content: center !important;	    align-content: center !important;
  }	  }

  .align-content-md-between {	  .align-content-md-between {
    align-content: space-between !important;	    align-content: space-between !important;
  }	  }

  .align-content-md-around {	  .align-content-md-around {
    align-content: space-around !important;	    align-content: space-around !important;
  }	  }

  .align-content-md-stretch {	  .align-content-md-stretch {
    align-content: stretch !important;	    align-content: stretch !important;
  }	  }

  .align-self-md-auto {	  .align-self-md-auto {
    align-self: auto !important;	    align-self: auto !important;
  }	  }

  .align-self-md-start {	  .align-self-md-start {
    align-self: flex-start !important;	    align-self: flex-start !important;
  }	  }

  .align-self-md-end {	  .align-self-md-end {
    align-self: flex-end !important;	    align-self: flex-end !important;
  }	  }

  .align-self-md-center {	  .align-self-md-center {
    align-self: center !important;	    align-self: center !important;
  }	  }

  .align-self-md-baseline {	  .align-self-md-baseline {
    align-self: baseline !important;	    align-self: baseline !important;
  }	  }

  .align-self-md-stretch {	  .align-self-md-stretch {
    align-self: stretch !important;	    align-self: stretch !important;
  }	  }

  .order-md-first {	  .order-md-first {
    order: -1 !important;	    order: -1 !important;
  }	  }

  .order-md-0 {	  .order-md-0 {
    order: 0 !important;	    order: 0 !important;
  }	  }

  .order-md-1 {	  .order-md-1 {
    order: 1 !important;	    order: 1 !important;
  }	  }

  .order-md-2 {	  .order-md-2 {
    order: 2 !important;	    order: 2 !important;
  }	  }

  .order-md-3 {	  .order-md-3 {
    order: 3 !important;	    order: 3 !important;
  }	  }

  .order-md-4 {	  .order-md-4 {
    order: 4 !important;	    order: 4 !important;
  }	  }

  .order-md-5 {	  .order-md-5 {
    order: 5 !important;	    order: 5 !important;
  }	  }

  .order-md-last {	  .order-md-last {
    order: 6 !important;	    order: 6 !important;
  }	  }

  .m-md-0 {	  .m-md-0 {
    margin: 0 !important;	    margin: 0 !important;
  }	  }

  .m-md-1 {	  .m-md-1 {
    margin: 0.25rem !important;	    margin: 0.25rem !important;
  }	  }

  .m-md-2 {	  .m-md-2 {
    margin: 0.5rem !important;	    margin: 0.5rem !important;
  }	  }

  .m-md-3 {	  .m-md-3 {
    margin: 1rem !important;	    margin: 1rem !important;
  }	  }

  .m-md-4 {	  .m-md-4 {
    margin: 1.5rem !important;	    margin: 1.5rem !important;
  }	  }

  .m-md-5 {	  .m-md-5 {
    margin: 3rem !important;	    margin: 3rem !important;
  }	  }

  .m-md-auto {	  .m-md-auto {
    margin: auto !important;	    margin: auto !important;
  }	  }

  .mx-md-0 {	  .mx-md-0 {
    margin-right: 0 !important;	    margin-right: 0 !important;
    margin-left: 0 !important;	    margin-left: 0 !important;
  }	  }

  .mx-md-1 {	  .mx-md-1 {
    margin-right: 0.25rem !important;	    margin-right: 0.25rem !important;
    margin-left: 0.25rem !important;	    margin-left: 0.25rem !important;
  }	  }

  .mx-md-2 {	  .mx-md-2 {
    margin-right: 0.5rem !important;	    margin-right: 0.5rem !important;
    margin-left: 0.5rem !important;	    margin-left: 0.5rem !important;
  }	  }

  .mx-md-3 {	  .mx-md-3 {
    margin-right: 1rem !important;	    margin-right: 1rem !important;
    margin-left: 1rem !important;	    margin-left: 1rem !important;
  }	  }

  .mx-md-4 {	  .mx-md-4 {
    margin-right: 1.5rem !important;	    margin-right: 1.5rem !important;
    margin-left: 1.5rem !important;	    margin-left: 1.5rem !important;
  }	  }

  .mx-md-5 {	  .mx-md-5 {
    margin-right: 3rem !important;	    margin-right: 3rem !important;
    margin-left: 3rem !important;	    margin-left: 3rem !important;
  }	  }

  .mx-md-auto {	  .mx-md-auto {
    margin-right: auto !important;	    margin-right: auto !important;
    margin-left: auto !important;	    margin-left: auto !important;
  }	  }

  .my-md-0 {	  .my-md-0 {
    margin-top: 0 !important;	    margin-top: 0 !important;
    margin-bottom: 0 !important;	    margin-bottom: 0 !important;
  }	  }

  .my-md-1 {	  .my-md-1 {
    margin-top: 0.25rem !important;	    margin-top: 0.25rem !important;
    margin-bottom: 0.25rem !important;	    margin-bottom: 0.25rem !important;
  }	  }

  .my-md-2 {	  .my-md-2 {
    margin-top: 0.5rem !important;	    margin-top: 0.5rem !important;
    margin-bottom: 0.5rem !important;	    margin-bottom: 0.5rem !important;
  }	  }

  .my-md-3 {	  .my-md-3 {
    margin-top: 1rem !important;	    margin-top: 1rem !important;
    margin-bottom: 1rem !important;	    margin-bottom: 1rem !important;
  }	  }

  .my-md-4 {	  .my-md-4 {
    margin-top: 1.5rem !important;	    margin-top: 1.5rem !important;
    margin-bottom: 1.5rem !important;	    margin-bottom: 1.5rem !important;
  }	  }

  .my-md-5 {	  .my-md-5 {
    margin-top: 3rem !important;	    margin-top: 3rem !important;
    margin-bottom: 3rem !important;	    margin-bottom: 3rem !important;
  }	  }

  .my-md-auto {	  .my-md-auto {
    margin-top: auto !important;	    margin-top: auto !important;
    margin-bottom: auto !important;	    margin-bottom: auto !important;
  }	  }

  .mt-md-0 {	  .mt-md-0 {
    margin-top: 0 !important;	    margin-top: 0 !important;
  }	  }

  .mt-md-1 {	  .mt-md-1 {
    margin-top: 0.25rem !important;	    margin-top: 0.25rem !important;
  }	  }

  .mt-md-2 {	  .mt-md-2 {
    margin-top: 0.5rem !important;	    margin-top: 0.5rem !important;
  }	  }

  .mt-md-3 {	  .mt-md-3 {
    margin-top: 1rem !important;	    margin-top: 1rem !important;
  }	  }

  .mt-md-4 {	  .mt-md-4 {
    margin-top: 1.5rem !important;	    margin-top: 1.5rem !important;
  }	  }

  .mt-md-5 {	  .mt-md-5 {
    margin-top: 3rem !important;	    margin-top: 3rem !important;
  }	  }

  .mt-md-auto {	  .mt-md-auto {
    margin-top: auto !important;	    margin-top: auto !important;
  }	  }

  .me-md-0 {	  .me-md-0 {
    margin-right: 0 !important;	    margin-right: 0 !important;
  }	  }

  .me-md-1 {	  .me-md-1 {
    margin-right: 0.25rem !important;	    margin-right: 0.25rem !important;
  }	  }

  .me-md-2 {	  .me-md-2 {
    margin-right: 0.5rem !important;	    margin-right: 0.5rem !important;
  }	  }

  .me-md-3 {	  .me-md-3 {
    margin-right: 1rem !important;	    margin-right: 1rem !important;
  }	  }

  .me-md-4 {	  .me-md-4 {
    margin-right: 1.5rem !important;	    margin-right: 1.5rem !important;
  }	  }

  .me-md-5 {	  .me-md-5 {
    margin-right: 3rem !important;	    margin-right: 3rem !important;
  }	  }

  .me-md-auto {	  .me-md-auto {
    margin-right: auto !important;	    margin-right: auto !important;
  }	  }

  .mb-md-0 {	  .mb-md-0 {
    margin-bottom: 0 !important;	    margin-bottom: 0 !important;
  }	  }

  .mb-md-1 {	  .mb-md-1 {
    margin-bottom: 0.25rem !important;	    margin-bottom: 0.25rem !important;
  }	  }

  .mb-md-2 {	  .mb-md-2 {
    margin-bottom: 0.5rem !important;	    margin-bottom: 0.5rem !important;
  }	  }

  .mb-md-3 {	  .mb-md-3 {
    margin-bottom: 1rem !important;	    margin-bottom: 1rem !important;
  }	  }

  .mb-md-4 {	  .mb-md-4 {
    margin-bottom: 1.5rem !important;	    margin-bottom: 1.5rem !important;
  }	  }

  .mb-md-5 {	  .mb-md-5 {
    margin-bottom: 3rem !important;	    margin-bottom: 3rem !important;
  }	  }

  .mb-md-auto {	  .mb-md-auto {
    margin-bottom: auto !important;	    margin-bottom: auto !important;
  }	  }

  .ms-md-0 {	  .ms-md-0 {
    margin-left: 0 !important;	    margin-left: 0 !important;
  }	  }

  .ms-md-1 {	  .ms-md-1 {
    margin-left: 0.25rem !important;	    margin-left: 0.25rem !important;
  }	  }

  .ms-md-2 {	  .ms-md-2 {
    margin-left: 0.5rem !important;	    margin-left: 0.5rem !important;
  }	  }

  .ms-md-3 {	  .ms-md-3 {
    margin-left: 1rem !important;	    margin-left: 1rem !important;
  }	  }

  .ms-md-4 {	  .ms-md-4 {
    margin-left: 1.5rem !important;	    margin-left: 1.5rem !important;
  }	  }

  .ms-md-5 {	  .ms-md-5 {
    margin-left: 3rem !important;	    margin-left: 3rem !important;
  }	  }

  .ms-md-auto {	  .ms-md-auto {
    margin-left: auto !important;	    margin-left: auto !important;
  }	  }

  .p-md-0 {	  .p-md-0 {
    padding: 0 !important;	    padding: 0 !important;
  }	  }

  .p-md-1 {	  .p-md-1 {
    padding: 0.25rem !important;	    padding: 0.25rem !important;
  }	  }

  .p-md-2 {	  .p-md-2 {
    padding: 0.5rem !important;	    padding: 0.5rem !important;
  }	  }

  .p-md-3 {	  .p-md-3 {
    padding: 1rem !important;	    padding: 1rem !important;
  }	  }

  .p-md-4 {	  .p-md-4 {
    padding: 1.5rem !important;	    padding: 1.5rem !important;
  }	  }

  .p-md-5 {	  .p-md-5 {
    padding: 3rem !important;	    padding: 3rem !important;
  }	  }

  .px-md-0 {	  .px-md-0 {
    padding-right: 0 !important;	    padding-right: 0 !important;
    padding-left: 0 !important;	    padding-left: 0 !important;
  }	  }

  .px-md-1 {	  .px-md-1 {
    padding-right: 0.25rem !important;	    padding-right: 0.25rem !important;
    padding-left: 0.25rem !important;	    padding-left: 0.25rem !important;
  }	  }

  .px-md-2 {	  .px-md-2 {
    padding-right: 0.5rem !important;	    padding-right: 0.5rem !important;
    padding-left: 0.5rem !important;	    padding-left: 0.5rem !important;
  }	  }

  .px-md-3 {	  .px-md-3 {
    padding-right: 1rem !important;	    padding-right: 1rem !important;
    padding-left: 1rem !important;	    padding-left: 1rem !important;
  }	  }

  .px-md-4 {	  .px-md-4 {
    padding-right: 1.5rem !important;	    padding-right: 1.5rem !important;
    padding-left: 1.5rem !important;	    padding-left: 1.5rem !important;
  }	  }

  .px-md-5 {	  .px-md-5 {
    padding-right: 3rem !important;	    padding-right: 3rem !important;
    padding-left: 3rem !important;	    padding-left: 3rem !important;
  }	  }

  .py-md-0 {	  .py-md-0 {
    padding-top: 0 !important;	    padding-top: 0 !important;
    padding-bottom: 0 !important;	    padding-bottom: 0 !important;
  }	  }

  .py-md-1 {	  .py-md-1 {
    padding-top: 0.25rem !important;	    padding-top: 0.25rem !important;
    padding-bottom: 0.25rem !important;	    padding-bottom: 0.25rem !important;
  }	  }

  .py-md-2 {	  .py-md-2 {
    padding-top: 0.5rem !important;	    padding-top: 0.5rem !important;
    padding-bottom: 0.5rem !important;	    padding-bottom: 0.5rem !important;
  }	  }

  .py-md-3 {	  .py-md-3 {
    padding-top: 1rem !important;	    padding-top: 1rem !important;
    padding-bottom: 1rem !important;	    padding-bottom: 1rem !important;
  }	  }

  .py-md-4 {	  .py-md-4 {
    padding-top: 1.5rem !important;	    padding-top: 1.5rem !important;
    padding-bottom: 1.5rem !important;	    padding-bottom: 1.5rem !important;
  }	  }

  .py-md-5 {	  .py-md-5 {
    padding-top: 3rem !important;	    padding-top: 3rem !important;
    padding-bottom: 3rem !important;	    padding-bottom: 3rem !important;
  }	  }

  .pt-md-0 {	  .pt-md-0 {
    padding-top: 0 !important;	    padding-top: 0 !important;
  }	  }

  .pt-md-1 {	  .pt-md-1 {
    padding-top: 0.25rem !important;	    padding-top: 0.25rem !important;
  }	  }

  .pt-md-2 {	  .pt-md-2 {
    padding-top: 0.5rem !important;	    padding-top: 0.5rem !important;
  }	  }

  .pt-md-3 {	  .pt-md-3 {
    padding-top: 1rem !important;	    padding-top: 1rem !important;
  }	  }

  .pt-md-4 {	  .pt-md-4 {
    padding-top: 1.5rem !important;	    padding-top: 1.5rem !important;
  }	  }

  .pt-md-5 {	  .pt-md-5 {
    padding-top: 3rem !important;	    padding-top: 3rem !important;
  }	  }

  .pe-md-0 {	  .pe-md-0 {
    padding-right: 0 !important;	    padding-right: 0 !important;
  }	  }

  .pe-md-1 {	  .pe-md-1 {
    padding-right: 0.25rem !important;	    padding-right: 0.25rem !important;
  }	  }

  .pe-md-2 {	  .pe-md-2 {
    padding-right: 0.5rem !important;	    padding-right: 0.5rem !important;
  }	  }

  .pe-md-3 {	  .pe-md-3 {
    padding-right: 1rem !important;	    padding-right: 1rem !important;
  }	  }

  .pe-md-4 {	  .pe-md-4 {
    padding-right: 1.5rem !important;	    padding-right: 1.5rem !important;
  }	  }

  .pe-md-5 {	  .pe-md-5 {
    padding-right: 3rem !important;	    padding-right: 3rem !important;
  }	  }

  .pb-md-0 {	  .pb-md-0 {
    padding-bottom: 0 !important;	    padding-bottom: 0 !important;
  }	  }

  .pb-md-1 {	  .pb-md-1 {
    padding-bottom: 0.25rem !important;	    padding-bottom: 0.25rem !important;
  }	  }

  .pb-md-2 {	  .pb-md-2 {
    padding-bottom: 0.5rem !important;	    padding-bottom: 0.5rem !important;
  }	  }

  .pb-md-3 {	  .pb-md-3 {
    padding-bottom: 1rem !important;	    padding-bottom: 1rem !important;
  }	  }

  .pb-md-4 {	  .pb-md-4 {
    padding-bottom: 1.5rem !important;	    padding-bottom: 1.5rem !important;
  }	  }

  .pb-md-5 {	  .pb-md-5 {
    padding-bottom: 3rem !important;	    padding-bottom: 3rem !important;
  }	  }

  .ps-md-0 {	  .ps-md-0 {
    padding-left: 0 !important;	    padding-left: 0 !important;
  }	  }

  .ps-md-1 {	  .ps-md-1 {
    padding-left: 0.25rem !important;	    padding-left: 0.25rem !important;
  }	  }

  .ps-md-2 {	  .ps-md-2 {
    padding-left: 0.5rem !important;	    padding-left: 0.5rem !important;
  }	  }

  .ps-md-3 {	  .ps-md-3 {
    padding-left: 1rem !important;	    padding-left: 1rem !important;
  }	  }

  .ps-md-4 {	  .ps-md-4 {
    padding-left: 1.5rem !important;	    padding-left: 1.5rem !important;
  }	  }

  .ps-md-5 {	  .ps-md-5 {
    padding-left: 3rem !important;	    padding-left: 3rem !important;
  }	  }

  .gap-md-0 {
    gap: 0 !important;
  }
  .gap-md-1 {
    gap: 0.25rem !important;
  }
  .gap-md-2 {
    gap: 0.5rem !important;
  }
  .gap-md-3 {
    gap: 1rem !important;
  }
  .gap-md-4 {
    gap: 1.5rem !important;
  }
  .gap-md-5 {
    gap: 3rem !important;
  }
  .text-md-start {	  .text-md-start {
    text-align: left !important;	    text-align: left !important;
  }	  }

  .text-md-end {	  .text-md-end {
    text-align: right !important;	    text-align: right !important;
  }	  }

  .text-md-center {	  .text-md-center {
    text-align: center !important;	    text-align: center !important;
  }	  }
@@ -9279,649 +9294,494 @@ textarea.form-control-lg {
  .float-lg-start {	  .float-lg-start {
    float: left !important;	    float: left !important;
  }	  }

  .float-lg-end {	  .float-lg-end {
    float: right !important;	    float: right !important;
  }	  }

  .float-lg-none {	  .float-lg-none {
    float: none !important;	    float: none !important;
  }	  }

  .d-lg-inline {	  .d-lg-inline {
    display: inline !important;	    display: inline !important;
  }	  }

  .d-lg-inline-block {	  .d-lg-inline-block {
    display: inline-block !important;	    display: inline-block !important;
  }	  }

  .d-lg-block {	  .d-lg-block {
    display: block !important;	    display: block !important;
  }	  }

  .d-lg-grid {	  .d-lg-grid {
    display: grid !important;	    display: grid !important;
  }	  }

  .d-lg-table {	  .d-lg-table {
    display: table !important;	    display: table !important;
  }	  }

  .d-lg-table-row {	  .d-lg-table-row {
    display: table-row !important;	    display: table-row !important;
  }	  }

  .d-lg-table-cell {	  .d-lg-table-cell {
    display: table-cell !important;	    display: table-cell !important;
  }	  }

  .d-lg-flex {	  .d-lg-flex {
    display: flex !important;	    display: flex !important;
  }	  }

  .d-lg-inline-flex {	  .d-lg-inline-flex {
    display: inline-flex !important;	    display: inline-flex !important;
  }	  }

  .d-lg-none {	  .d-lg-none {
    display: none !important;	    display: none !important;
  }	  }

  .flex-lg-fill {	  .flex-lg-fill {
    flex: 1 1 auto !important;	    flex: 1 1 auto !important;
  }	  }

  .flex-lg-row {	  .flex-lg-row {
    flex-direction: row !important;	    flex-direction: row !important;
  }	  }

  .flex-lg-column {	  .flex-lg-column {
    flex-direction: column !important;	    flex-direction: column !important;
  }	  }

  .flex-lg-row-reverse {	  .flex-lg-row-reverse {
    flex-direction: row-reverse !important;	    flex-direction: row-reverse !important;
  }	  }

  .flex-lg-column-reverse {	  .flex-lg-column-reverse {
    flex-direction: column-reverse !important;	    flex-direction: column-reverse !important;
  }	  }

  .flex-lg-grow-0 {	  .flex-lg-grow-0 {
    flex-grow: 0 !important;	    flex-grow: 0 !important;
  }	  }

  .flex-lg-grow-1 {	  .flex-lg-grow-1 {
    flex-grow: 1 !important;	    flex-grow: 1 !important;
  }	  }

  .flex-lg-shrink-0 {	  .flex-lg-shrink-0 {
    flex-shrink: 0 !important;	    flex-shrink: 0 !important;
  }	  }

  .flex-lg-shrink-1 {	  .flex-lg-shrink-1 {
    flex-shrink: 1 !important;	    flex-shrink: 1 !important;
  }	  }

  .flex-lg-wrap {	  .flex-lg-wrap {
    flex-wrap: wrap !important;	    flex-wrap: wrap !important;
  }	  }

  .flex-lg-nowrap {	  .flex-lg-nowrap {
    flex-wrap: nowrap !important;	    flex-wrap: nowrap !important;
  }	  }

  .flex-lg-wrap-reverse {	  .flex-lg-wrap-reverse {
    flex-wrap: wrap-reverse !important;	    flex-wrap: wrap-reverse !important;
  }	  }

  .gap-lg-0 {	
    gap: 0 !important;	
  }	

  .gap-lg-1 {	
    gap: 0.25rem !important;	
  }	

  .gap-lg-2 {	
    gap: 0.5rem !important;	
  }	

  .gap-lg-3 {	
    gap: 1rem !important;	
  }	

  .gap-lg-4 {	
    gap: 1.5rem !important;	
  }	

  .gap-lg-5 {	
    gap: 3rem !important;	
  }	

  .justify-content-lg-start {	  .justify-content-lg-start {
    justify-content: flex-start !important;	    justify-content: flex-start !important;
  }	  }

  .justify-content-lg-end {	  .justify-content-lg-end {
    justify-content: flex-end !important;	    justify-content: flex-end !important;
  }	  }

  .justify-content-lg-center {	  .justify-content-lg-center {
    justify-content: center !important;	    justify-content: center !important;
  }	  }

  .justify-content-lg-between {	  .justify-content-lg-between {
    justify-content: space-between !important;	    justify-content: space-between !important;
  }	  }

  .justify-content-lg-around {	  .justify-content-lg-around {
    justify-content: space-around !important;	    justify-content: space-around !important;
  }	  }

  .justify-content-lg-evenly {	  .justify-content-lg-evenly {
    justify-content: space-evenly !important;	    justify-content: space-evenly !important;
  }	  }

  .align-items-lg-start {	  .align-items-lg-start {
    align-items: flex-start !important;	    align-items: flex-start !important;
  }	  }

  .align-items-lg-end {	  .align-items-lg-end {
    align-items: flex-end !important;	    align-items: flex-end !important;
  }	  }

  .align-items-lg-center {	  .align-items-lg-center {
    align-items: center !important;	    align-items: center !important;
  }	  }

  .align-items-lg-baseline {	  .align-items-lg-baseline {
    align-items: baseline !important;	    align-items: baseline !important;
  }	  }

  .align-items-lg-stretch {	  .align-items-lg-stretch {
    align-items: stretch !important;	    align-items: stretch !important;
  }	  }

  .align-content-lg-start {	  .align-content-lg-start {
    align-content: flex-start !important;	    align-content: flex-start !important;
  }	  }

  .align-content-lg-end {	  .align-content-lg-end {
    align-content: flex-end !important;	    align-content: flex-end !important;
  }	  }

  .align-content-lg-center {	  .align-content-lg-center {
    align-content: center !important;	    align-content: center !important;
  }	  }

  .align-content-lg-between {	  .align-content-lg-between {
    align-content: space-between !important;	    align-content: space-between !important;
  }	  }

  .align-content-lg-around {	  .align-content-lg-around {
    align-content: space-around !important;	    align-content: space-around !important;
  }	  }

  .align-content-lg-stretch {	  .align-content-lg-stretch {
    align-content: stretch !important;	    align-content: stretch !important;
  }	  }

  .align-self-lg-auto {	  .align-self-lg-auto {
    align-self: auto !important;	    align-self: auto !important;
  }	  }

  .align-self-lg-start {	  .align-self-lg-start {
    align-self: flex-start !important;	    align-self: flex-start !important;
  }	  }

  .align-self-lg-end {	  .align-self-lg-end {
    align-self: flex-end !important;	    align-self: flex-end !important;
  }	  }

  .align-self-lg-center {	  .align-self-lg-center {
    align-self: center !important;	    align-self: center !important;
  }	  }

  .align-self-lg-baseline {	  .align-self-lg-baseline {
    align-self: baseline !important;	    align-self: baseline !important;
  }	  }

  .align-self-lg-stretch {	  .align-self-lg-stretch {
    align-self: stretch !important;	    align-self: stretch !important;
  }	  }

  .order-lg-first {	  .order-lg-first {
    order: -1 !important;	    order: -1 !important;
  }	  }

  .order-lg-0 {	  .order-lg-0 {
    order: 0 !important;	    order: 0 !important;
  }	  }

  .order-lg-1 {	  .order-lg-1 {
    order: 1 !important;	    order: 1 !important;
  }	  }

  .order-lg-2 {	  .order-lg-2 {
    order: 2 !important;	    order: 2 !important;
  }	  }

  .order-lg-3 {	  .order-lg-3 {
    order: 3 !important;	    order: 3 !important;
  }	  }

  .order-lg-4 {	  .order-lg-4 {
    order: 4 !important;	    order: 4 !important;
  }	  }

  .order-lg-5 {	  .order-lg-5 {
    order: 5 !important;	    order: 5 !important;
  }	  }

  .order-lg-last {	  .order-lg-last {
    order: 6 !important;	    order: 6 !important;
  }	  }

  .m-lg-0 {	  .m-lg-0 {
    margin: 0 !important;	    margin: 0 !important;
  }	  }

  .m-lg-1 {	  .m-lg-1 {
    margin: 0.25rem !important;	    margin: 0.25rem !important;
  }	  }

  .m-lg-2 {	  .m-lg-2 {
    margin: 0.5rem !important;	    margin: 0.5rem !important;
  }	  }

  .m-lg-3 {	  .m-lg-3 {
    margin: 1rem !important;	    margin: 1rem !important;
  }	  }

  .m-lg-4 {	  .m-lg-4 {
    margin: 1.5rem !important;	    margin: 1.5rem !important;
  }	  }

  .m-lg-5 {	  .m-lg-5 {
    margin: 3rem !important;	    margin: 3rem !important;
  }	  }

  .m-lg-auto {	  .m-lg-auto {
    margin: auto !important;	    margin: auto !important;
  }	  }

  .mx-lg-0 {	  .mx-lg-0 {
    margin-right: 0 !important;	    margin-right: 0 !important;
    margin-left: 0 !important;	    margin-left: 0 !important;
  }	  }

  .mx-lg-1 {	  .mx-lg-1 {
    margin-right: 0.25rem !important;	    margin-right: 0.25rem !important;
    margin-left: 0.25rem !important;	    margin-left: 0.25rem !important;
  }	  }

  .mx-lg-2 {	  .mx-lg-2 {
    margin-right: 0.5rem !important;	    margin-right: 0.5rem !important;
    margin-left: 0.5rem !important;	    margin-left: 0.5rem !important;
  }	  }

  .mx-lg-3 {	  .mx-lg-3 {
    margin-right: 1rem !important;	    margin-right: 1rem !important;
    margin-left: 1rem !important;	    margin-left: 1rem !important;
  }	  }

  .mx-lg-4 {	  .mx-lg-4 {
    margin-right: 1.5rem !important;	    margin-right: 1.5rem !important;
    margin-left: 1.5rem !important;	    margin-left: 1.5rem !important;
  }	  }

  .mx-lg-5 {	  .mx-lg-5 {
    margin-right: 3rem !important;	    margin-right: 3rem !important;
    margin-left: 3rem !important;	    margin-left: 3rem !important;
  }	  }

  .mx-lg-auto {	  .mx-lg-auto {
    margin-right: auto !important;	    margin-right: auto !important;
    margin-left: auto !important;	    margin-left: auto !important;
  }	  }

  .my-lg-0 {	  .my-lg-0 {
    margin-top: 0 !important;	    margin-top: 0 !important;
    margin-bottom: 0 !important;	    margin-bottom: 0 !important;
  }	  }

  .my-lg-1 {	  .my-lg-1 {
    margin-top: 0.25rem !important;	    margin-top: 0.25rem !important;
    margin-bottom: 0.25rem !important;	    margin-bottom: 0.25rem !important;
  }	  }

  .my-lg-2 {	  .my-lg-2 {
    margin-top: 0.5rem !important;	    margin-top: 0.5rem !important;
    margin-bottom: 0.5rem !important;	    margin-bottom: 0.5rem !important;
  }	  }

  .my-lg-3 {	  .my-lg-3 {
    margin-top: 1rem !important;	    margin-top: 1rem !important;
    margin-bottom: 1rem !important;	    margin-bottom: 1rem !important;
  }	  }

  .my-lg-4 {	  .my-lg-4 {
    margin-top: 1.5rem !important;	    margin-top: 1.5rem !important;
    margin-bottom: 1.5rem !important;	    margin-bottom: 1.5rem !important;
  }	  }

  .my-lg-5 {	  .my-lg-5 {
    margin-top: 3rem !important;	    margin-top: 3rem !important;
    margin-bottom: 3rem !important;	    margin-bottom: 3rem !important;
  }	  }

  .my-lg-auto {	  .my-lg-auto {
    margin-top: auto !important;	    margin-top: auto !important;
    margin-bottom: auto !important;	    margin-bottom: auto !important;
  }	  }

  .mt-lg-0 {	  .mt-lg-0 {
    margin-top: 0 !important;	    margin-top: 0 !important;
  }	  }

  .mt-lg-1 {	  .mt-lg-1 {
    margin-top: 0.25rem !important;	    margin-top: 0.25rem !important;
  }	  }

  .mt-lg-2 {	  .mt-lg-2 {
    margin-top: 0.5rem !important;	    margin-top: 0.5rem !important;
  }	  }

  .mt-lg-3 {	  .mt-lg-3 {
    margin-top: 1rem !important;	    margin-top: 1rem !important;
  }	  }

  .mt-lg-4 {	  .mt-lg-4 {
    margin-top: 1.5rem !important;	    margin-top: 1.5rem !important;
  }	  }

  .mt-lg-5 {	  .mt-lg-5 {
    margin-top: 3rem !important;	    margin-top: 3rem !important;
  }	  }

  .mt-lg-auto {	  .mt-lg-auto {
    margin-top: auto !important;	    margin-top: auto !important;
  }	  }

  .me-lg-0 {	  .me-lg-0 {
    margin-right: 0 !important;	    margin-right: 0 !important;
  }	  }

  .me-lg-1 {	  .me-lg-1 {
    margin-right: 0.25rem !important;	    margin-right: 0.25rem !important;
  }	  }

  .me-lg-2 {	  .me-lg-2 {
    margin-right: 0.5rem !important;	    margin-right: 0.5rem !important;
  }	  }

  .me-lg-3 {	  .me-lg-3 {
    margin-right: 1rem !important;	    margin-right: 1rem !important;
  }	  }

  .me-lg-4 {	  .me-lg-4 {
    margin-right: 1.5rem !important;	    margin-right: 1.5rem !important;
  }	  }

  .me-lg-5 {	  .me-lg-5 {
    margin-right: 3rem !important;	    margin-right: 3rem !important;
  }	  }

  .me-lg-auto {	  .me-lg-auto {
    margin-right: auto !important;	    margin-right: auto !important;
  }	  }

  .mb-lg-0 {	  .mb-lg-0 {
    margin-bottom: 0 !important;	    margin-bottom: 0 !important;
  }	  }

  .mb-lg-1 {	  .mb-lg-1 {
    margin-bottom: 0.25rem !important;	    margin-bottom: 0.25rem !important;
  }	  }

  .mb-lg-2 {	  .mb-lg-2 {
    margin-bottom: 0.5rem !important;	    margin-bottom: 0.5rem !important;
  }	  }

  .mb-lg-3 {	  .mb-lg-3 {
    margin-bottom: 1rem !important;	    margin-bottom: 1rem !important;
  }	  }

  .mb-lg-4 {	  .mb-lg-4 {
    margin-bottom: 1.5rem !important;	    margin-bottom: 1.5rem !important;
  }	  }

  .mb-lg-5 {	  .mb-lg-5 {
    margin-bottom: 3rem !important;	    margin-bottom: 3rem !important;
  }	  }

  .mb-lg-auto {	  .mb-lg-auto {
    margin-bottom: auto !important;	    margin-bottom: auto !important;
  }	  }

  .ms-lg-0 {	  .ms-lg-0 {
    margin-left: 0 !important;	    margin-left: 0 !important;
  }	  }

  .ms-lg-1 {	  .ms-lg-1 {
    margin-left: 0.25rem !important;	    margin-left: 0.25rem !important;
  }	  }

  .ms-lg-2 {	  .ms-lg-2 {
    margin-left: 0.5rem !important;	    margin-left: 0.5rem !important;
  }	  }

  .ms-lg-3 {	  .ms-lg-3 {
    margin-left: 1rem !important;	    margin-left: 1rem !important;
  }	  }

  .ms-lg-4 {	  .ms-lg-4 {
    margin-left: 1.5rem !important;	    margin-left: 1.5rem !important;
  }	  }

  .ms-lg-5 {	  .ms-lg-5 {
    margin-left: 3rem !important;	    margin-left: 3rem !important;
  }	  }

  .ms-lg-auto {	  .ms-lg-auto {
    margin-left: auto !important;	    margin-left: auto !important;
  }	  }

  .p-lg-0 {	  .p-lg-0 {
    padding: 0 !important;	    padding: 0 !important;
  }	  }

  .p-lg-1 {	  .p-lg-1 {
    padding: 0.25rem !important;	    padding: 0.25rem !important;
  }	  }

  .p-lg-2 {	  .p-lg-2 {
    padding: 0.5rem !important;	    padding: 0.5rem !important;
  }	  }

  .p-lg-3 {	  .p-lg-3 {
    padding: 1rem !important;	    padding: 1rem !important;
  }	  }

  .p-lg-4 {	  .p-lg-4 {
    padding: 1.5rem !important;	    padding: 1.5rem !important;
  }	  }

  .p-lg-5 {	  .p-lg-5 {
    padding: 3rem !important;	    padding: 3rem !important;
  }	  }

  .px-lg-0 {	  .px-lg-0 {
    padding-right: 0 !important;	    padding-right: 0 !important;
    padding-left: 0 !important;	    padding-left: 0 !important;
  }	  }

  .px-lg-1 {	  .px-lg-1 {
    padding-right: 0.25rem !important;	    padding-right: 0.25rem !important;
    padding-left: 0.25rem !important;	    padding-left: 0.25rem !important;
  }	  }

  .px-lg-2 {	  .px-lg-2 {
    padding-right: 0.5rem !important;	    padding-right: 0.5rem !important;
    padding-left: 0.5rem !important;	    padding-left: 0.5rem !important;
  }	  }

  .px-lg-3 {	  .px-lg-3 {
    padding-right: 1rem !important;	    padding-right: 1rem !important;
    padding-left: 1rem !important;	    padding-left: 1rem !important;
  }	  }

  .px-lg-4 {	  .px-lg-4 {
    padding-right: 1.5rem !important;	    padding-right: 1.5rem !important;
    padding-left: 1.5rem !important;	    padding-left: 1.5rem !important;
  }	  }

  .px-lg-5 {	  .px-lg-5 {
    padding-right: 3rem !important;	    padding-right: 3rem !important;
    padding-left: 3rem !important;	    padding-left: 3rem !important;
  }	  }

  .py-lg-0 {	  .py-lg-0 {
    padding-top: 0 !important;	    padding-top: 0 !important;
    padding-bottom: 0 !important;	    padding-bottom: 0 !important;
  }	  }

  .py-lg-1 {	  .py-lg-1 {
    padding-top: 0.25rem !important;	    padding-top: 0.25rem !important;
    padding-bottom: 0.25rem !important;	    padding-bottom: 0.25rem !important;
  }	  }

  .py-lg-2 {	  .py-lg-2 {
    padding-top: 0.5rem !important;	    padding-top: 0.5rem !important;
    padding-bottom: 0.5rem !important;	    padding-bottom: 0.5rem !important;
  }	  }

  .py-lg-3 {	  .py-lg-3 {
    padding-top: 1rem !important;	    padding-top: 1rem !important;
    padding-bottom: 1rem !important;	    padding-bottom: 1rem !important;
  }	  }

  .py-lg-4 {	  .py-lg-4 {
    padding-top: 1.5rem !important;	    padding-top: 1.5rem !important;
    padding-bottom: 1.5rem !important;	    padding-bottom: 1.5rem !important;
  }	  }

  .py-lg-5 {	  .py-lg-5 {
    padding-top: 3rem !important;	    padding-top: 3rem !important;
    padding-bottom: 3rem !important;	    padding-bottom: 3rem !important;
  }	  }

  .pt-lg-0 {	  .pt-lg-0 {
    padding-top: 0 !important;	    padding-top: 0 !important;
  }	  }

  .pt-lg-1 {	  .pt-lg-1 {
    padding-top: 0.25rem !important;	    padding-top: 0.25rem !important;
  }	  }

  .pt-lg-2 {	  .pt-lg-2 {
    padding-top: 0.5rem !important;	    padding-top: 0.5rem !important;
  }	  }

  .pt-lg-3 {	  .pt-lg-3 {
    padding-top: 1rem !important;	    padding-top: 1rem !important;
  }	  }

  .pt-lg-4 {	  .pt-lg-4 {
    padding-top: 1.5rem !important;	    padding-top: 1.5rem !important;
  }	  }

  .pt-lg-5 {	  .pt-lg-5 {
    padding-top: 3rem !important;	    padding-top: 3rem !important;
  }	  }

  .pe-lg-0 {	  .pe-lg-0 {
    padding-right: 0 !important;	    padding-right: 0 !important;
  }	  }

  .pe-lg-1 {	  .pe-lg-1 {
    padding-right: 0.25rem !important;	    padding-right: 0.25rem !important;
  }	  }

  .pe-lg-2 {	  .pe-lg-2 {
    padding-right: 0.5rem !important;	    padding-right: 0.5rem !important;
  }	  }

  .pe-lg-3 {	  .pe-lg-3 {
    padding-right: 1rem !important;	    padding-right: 1rem !important;
  }	  }

  .pe-lg-4 {	  .pe-lg-4 {
    padding-right: 1.5rem !important;	    padding-right: 1.5rem !important;
  }	  }

  .pe-lg-5 {	  .pe-lg-5 {
    padding-right: 3rem !important;	    padding-right: 3rem !important;
  }	  }

  .pb-lg-0 {	  .pb-lg-0 {
    padding-bottom: 0 !important;	    padding-bottom: 0 !important;
  }	  }

  .pb-lg-1 {	  .pb-lg-1 {
    padding-bottom: 0.25rem !important;	    padding-bottom: 0.25rem !important;
  }	  }

  .pb-lg-2 {	  .pb-lg-2 {
    padding-bottom: 0.5rem !important;	    padding-bottom: 0.5rem !important;
  }	  }

  .pb-lg-3 {	  .pb-lg-3 {
    padding-bottom: 1rem !important;	    padding-bottom: 1rem !important;
  }	  }

  .pb-lg-4 {	  .pb-lg-4 {
    padding-bottom: 1.5rem !important;	    padding-bottom: 1.5rem !important;
  }	  }

  .pb-lg-5 {	  .pb-lg-5 {
    padding-bottom: 3rem !important;	    padding-bottom: 3rem !important;
  }	  }

  .ps-lg-0 {	  .ps-lg-0 {
    padding-left: 0 !important;	    padding-left: 0 !important;
  }	  }

  .ps-lg-1 {	  .ps-lg-1 {
    padding-left: 0.25rem !important;	    padding-left: 0.25rem !important;
  }	  }

  .ps-lg-2 {	  .ps-lg-2 {
    padding-left: 0.5rem !important;	    padding-left: 0.5rem !important;
  }	  }

  .ps-lg-3 {	  .ps-lg-3 {
    padding-left: 1rem !important;	    padding-left: 1rem !important;
  }	  }

  .ps-lg-4 {	  .ps-lg-4 {
    padding-left: 1.5rem !important;	    padding-left: 1.5rem !important;
  }	  }

  .ps-lg-5 {	  .ps-lg-5 {
    padding-left: 3rem !important;	    padding-left: 3rem !important;
  }	  }

  .gap-lg-0 {
    gap: 0 !important;
  }
  .gap-lg-1 {
    gap: 0.25rem !important;
  }
  .gap-lg-2 {
    gap: 0.5rem !important;
  }
  .gap-lg-3 {
    gap: 1rem !important;
  }
  .gap-lg-4 {
    gap: 1.5rem !important;
  }
  .gap-lg-5 {
    gap: 3rem !important;
  }
  .text-lg-start {	  .text-lg-start {
    text-align: left !important;	    text-align: left !important;
  }	  }

  .text-lg-end {	  .text-lg-end {
    text-align: right !important;	    text-align: right !important;
  }	  }

  .text-lg-center {	  .text-lg-center {
    text-align: center !important;	    text-align: center !important;
  }	  }
@@ -9930,649 +9790,494 @@ textarea.form-control-lg {
  .float-xl-start {	  .float-xl-start {
    float: left !important;	    float: left !important;
  }	  }

  .float-xl-end {	  .float-xl-end {
    float: right !important;	    float: right !important;
  }	  }

  .float-xl-none {	  .float-xl-none {
    float: none !important;	    float: none !important;
  }	  }

  .d-xl-inline {	  .d-xl-inline {
    display: inline !important;	    display: inline !important;
  }	  }

  .d-xl-inline-block {	  .d-xl-inline-block {
    display: inline-block !important;	    display: inline-block !important;
  }	  }

  .d-xl-block {	  .d-xl-block {
    display: block !important;	    display: block !important;
  }	  }

  .d-xl-grid {	  .d-xl-grid {
    display: grid !important;	    display: grid !important;
  }	  }

  .d-xl-table {	  .d-xl-table {
    display: table !important;	    display: table !important;
  }	  }

  .d-xl-table-row {	  .d-xl-table-row {
    display: table-row !important;	    display: table-row !important;
  }	  }

  .d-xl-table-cell {	  .d-xl-table-cell {
    display: table-cell !important;	    display: table-cell !important;
  }	  }

  .d-xl-flex {	  .d-xl-flex {
    display: flex !important;	    display: flex !important;
  }	  }

  .d-xl-inline-flex {	  .d-xl-inline-flex {
    display: inline-flex !important;	    display: inline-flex !important;
  }	  }

  .d-xl-none {	  .d-xl-none {
    display: none !important;	    display: none !important;
  }	  }

  .flex-xl-fill {	  .flex-xl-fill {
    flex: 1 1 auto !important;	    flex: 1 1 auto !important;
  }	  }

  .flex-xl-row {	  .flex-xl-row {
    flex-direction: row !important;	    flex-direction: row !important;
  }	  }

  .flex-xl-column {	  .flex-xl-column {
    flex-direction: column !important;	    flex-direction: column !important;
  }	  }

  .flex-xl-row-reverse {	  .flex-xl-row-reverse {
    flex-direction: row-reverse !important;	    flex-direction: row-reverse !important;
  }	  }

  .flex-xl-column-reverse {	  .flex-xl-column-reverse {
    flex-direction: column-reverse !important;	    flex-direction: column-reverse !important;
  }	  }

  .flex-xl-grow-0 {	  .flex-xl-grow-0 {
    flex-grow: 0 !important;	    flex-grow: 0 !important;
  }	  }

  .flex-xl-grow-1 {	  .flex-xl-grow-1 {
    flex-grow: 1 !important;	    flex-grow: 1 !important;
  }	  }

  .flex-xl-shrink-0 {	  .flex-xl-shrink-0 {
    flex-shrink: 0 !important;	    flex-shrink: 0 !important;
  }	  }

  .flex-xl-shrink-1 {	  .flex-xl-shrink-1 {
    flex-shrink: 1 !important;	    flex-shrink: 1 !important;
  }	  }

  .flex-xl-wrap {	  .flex-xl-wrap {
    flex-wrap: wrap !important;	    flex-wrap: wrap !important;
  }	  }

  .flex-xl-nowrap {	  .flex-xl-nowrap {
    flex-wrap: nowrap !important;	    flex-wrap: nowrap !important;
  }	  }

  .flex-xl-wrap-reverse {	  .flex-xl-wrap-reverse {
    flex-wrap: wrap-reverse !important;	    flex-wrap: wrap-reverse !important;
  }	  }

  .gap-xl-0 {	
    gap: 0 !important;	
  }	

  .gap-xl-1 {	
    gap: 0.25rem !important;	
  }	

  .gap-xl-2 {	
    gap: 0.5rem !important;	
  }	

  .gap-xl-3 {	
    gap: 1rem !important;	
  }	

  .gap-xl-4 {	
    gap: 1.5rem !important;	
  }	

  .gap-xl-5 {	
    gap: 3rem !important;	
  }	

  .justify-content-xl-start {	  .justify-content-xl-start {
    justify-content: flex-start !important;	    justify-content: flex-start !important;
  }	  }

  .justify-content-xl-end {	  .justify-content-xl-end {
    justify-content: flex-end !important;	    justify-content: flex-end !important;
  }	  }

  .justify-content-xl-center {	  .justify-content-xl-center {
    justify-content: center !important;	    justify-content: center !important;
  }	  }

  .justify-content-xl-between {	  .justify-content-xl-between {
    justify-content: space-between !important;	    justify-content: space-between !important;
  }	  }

  .justify-content-xl-around {	  .justify-content-xl-around {
    justify-content: space-around !important;	    justify-content: space-around !important;
  }	  }

  .justify-content-xl-evenly {	  .justify-content-xl-evenly {
    justify-content: space-evenly !important;	    justify-content: space-evenly !important;
  }	  }

  .align-items-xl-start {	  .align-items-xl-start {
    align-items: flex-start !important;	    align-items: flex-start !important;
  }	  }

  .align-items-xl-end {	  .align-items-xl-end {
    align-items: flex-end !important;	    align-items: flex-end !important;
  }	  }

  .align-items-xl-center {	  .align-items-xl-center {
    align-items: center !important;	    align-items: center !important;
  }	  }

  .align-items-xl-baseline {	  .align-items-xl-baseline {
    align-items: baseline !important;	    align-items: baseline !important;
  }	  }

  .align-items-xl-stretch {	  .align-items-xl-stretch {
    align-items: stretch !important;	    align-items: stretch !important;
  }	  }

  .align-content-xl-start {	  .align-content-xl-start {
    align-content: flex-start !important;	    align-content: flex-start !important;
  }	  }

  .align-content-xl-end {	  .align-content-xl-end {
    align-content: flex-end !important;	    align-content: flex-end !important;
  }	  }

  .align-content-xl-center {	  .align-content-xl-center {
    align-content: center !important;	    align-content: center !important;
  }	  }

  .align-content-xl-between {	  .align-content-xl-between {
    align-content: space-between !important;	    align-content: space-between !important;
  }	  }

  .align-content-xl-around {	  .align-content-xl-around {
    align-content: space-around !important;	    align-content: space-around !important;
  }	  }

  .align-content-xl-stretch {	  .align-content-xl-stretch {
    align-content: stretch !important;	    align-content: stretch !important;
  }	  }

  .align-self-xl-auto {	  .align-self-xl-auto {
    align-self: auto !important;	    align-self: auto !important;
  }	  }

  .align-self-xl-start {	  .align-self-xl-start {
    align-self: flex-start !important;	    align-self: flex-start !important;
  }	  }

  .align-self-xl-end {	  .align-self-xl-end {
    align-self: flex-end !important;	    align-self: flex-end !important;
  }	  }

  .align-self-xl-center {	  .align-self-xl-center {
    align-self: center !important;	    align-self: center !important;
  }	  }

  .align-self-xl-baseline {	  .align-self-xl-baseline {
    align-self: baseline !important;	    align-self: baseline !important;
  }	  }

  .align-self-xl-stretch {	  .align-self-xl-stretch {
    align-self: stretch !important;	    align-self: stretch !important;
  }	  }

  .order-xl-first {	  .order-xl-first {
    order: -1 !important;	    order: -1 !important;
  }	  }

  .order-xl-0 {	  .order-xl-0 {
    order: 0 !important;	    order: 0 !important;
  }	  }

  .order-xl-1 {	  .order-xl-1 {
    order: 1 !important;	    order: 1 !important;
  }	  }

  .order-xl-2 {	  .order-xl-2 {
    order: 2 !important;	    order: 2 !important;
  }	  }

  .order-xl-3 {	  .order-xl-3 {
    order: 3 !important;	    order: 3 !important;
  }	  }

  .order-xl-4 {	  .order-xl-4 {
    order: 4 !important;	    order: 4 !important;
  }	  }

  .order-xl-5 {	  .order-xl-5 {
    order: 5 !important;	    order: 5 !important;
  }	  }

  .order-xl-last {	  .order-xl-last {
    order: 6 !important;	    order: 6 !important;
  }	  }

  .m-xl-0 {	  .m-xl-0 {
    margin: 0 !important;	    margin: 0 !important;
  }	  }

  .m-xl-1 {	  .m-xl-1 {
    margin: 0.25rem !important;	    margin: 0.25rem !important;
  }	  }

  .m-xl-2 {	  .m-xl-2 {
    margin: 0.5rem !important;	    margin: 0.5rem !important;
  }	  }

  .m-xl-3 {	  .m-xl-3 {
    margin: 1rem !important;	    margin: 1rem !important;
  }	  }

  .m-xl-4 {	  .m-xl-4 {
    margin: 1.5rem !important;	    margin: 1.5rem !important;
  }	  }

  .m-xl-5 {	  .m-xl-5 {
    margin: 3rem !important;	    margin: 3rem !important;
  }	  }

  .m-xl-auto {	  .m-xl-auto {
    margin: auto !important;	    margin: auto !important;
  }	  }

  .mx-xl-0 {	  .mx-xl-0 {
    margin-right: 0 !important;	    margin-right: 0 !important;
    margin-left: 0 !important;	    margin-left: 0 !important;
  }	  }

  .mx-xl-1 {	  .mx-xl-1 {
    margin-right: 0.25rem !important;	    margin-right: 0.25rem !important;
    margin-left: 0.25rem !important;	    margin-left: 0.25rem !important;
  }	  }

  .mx-xl-2 {	  .mx-xl-2 {
    margin-right: 0.5rem !important;	    margin-right: 0.5rem !important;
    margin-left: 0.5rem !important;	    margin-left: 0.5rem !important;
  }	  }

  .mx-xl-3 {	  .mx-xl-3 {
    margin-right: 1rem !important;	    margin-right: 1rem !important;
    margin-left: 1rem !important;	    margin-left: 1rem !important;
  }	  }

  .mx-xl-4 {	  .mx-xl-4 {
    margin-right: 1.5rem !important;	    margin-right: 1.5rem !important;
    margin-left: 1.5rem !important;	    margin-left: 1.5rem !important;
  }	  }

  .mx-xl-5 {	  .mx-xl-5 {
    margin-right: 3rem !important;	    margin-right: 3rem !important;
    margin-left: 3rem !important;	    margin-left: 3rem !important;
  }	  }

  .mx-xl-auto {	  .mx-xl-auto {
    margin-right: auto !important;	    margin-right: auto !important;
    margin-left: auto !important;	    margin-left: auto !important;
  }	  }

  .my-xl-0 {	  .my-xl-0 {
    margin-top: 0 !important;	    margin-top: 0 !important;
    margin-bottom: 0 !important;	    margin-bottom: 0 !important;
  }	  }

  .my-xl-1 {	  .my-xl-1 {
    margin-top: 0.25rem !important;	    margin-top: 0.25rem !important;
    margin-bottom: 0.25rem !important;	    margin-bottom: 0.25rem !important;
  }	  }

  .my-xl-2 {	  .my-xl-2 {
    margin-top: 0.5rem !important;	    margin-top: 0.5rem !important;
    margin-bottom: 0.5rem !important;	    margin-bottom: 0.5rem !important;
  }	  }

  .my-xl-3 {	  .my-xl-3 {
    margin-top: 1rem !important;	    margin-top: 1rem !important;
    margin-bottom: 1rem !important;	    margin-bottom: 1rem !important;
  }	  }

  .my-xl-4 {	  .my-xl-4 {
    margin-top: 1.5rem !important;	    margin-top: 1.5rem !important;
    margin-bottom: 1.5rem !important;	    margin-bottom: 1.5rem !important;
  }	  }

  .my-xl-5 {	  .my-xl-5 {
    margin-top: 3rem !important;	    margin-top: 3rem !important;
    margin-bottom: 3rem !important;	    margin-bottom: 3rem !important;
  }	  }

  .my-xl-auto {	  .my-xl-auto {
    margin-top: auto !important;	    margin-top: auto !important;
    margin-bottom: auto !important;	    margin-bottom: auto !important;
  }	  }

  .mt-xl-0 {	  .mt-xl-0 {
    margin-top: 0 !important;	    margin-top: 0 !important;
  }	  }

  .mt-xl-1 {	  .mt-xl-1 {
    margin-top: 0.25rem !important;	    margin-top: 0.25rem !important;
  }	  }

  .mt-xl-2 {	  .mt-xl-2 {
    margin-top: 0.5rem !important;	    margin-top: 0.5rem !important;
  }	  }

  .mt-xl-3 {	  .mt-xl-3 {
    margin-top: 1rem !important;	    margin-top: 1rem !important;
  }	  }

  .mt-xl-4 {	  .mt-xl-4 {
    margin-top: 1.5rem !important;	    margin-top: 1.5rem !important;
  }	  }

  .mt-xl-5 {	  .mt-xl-5 {
    margin-top: 3rem !important;	    margin-top: 3rem !important;
  }	  }

  .mt-xl-auto {	  .mt-xl-auto {
    margin-top: auto !important;	    margin-top: auto !important;
  }	  }

  .me-xl-0 {	  .me-xl-0 {
    margin-right: 0 !important;	    margin-right: 0 !important;
  }	  }

  .me-xl-1 {	  .me-xl-1 {
    margin-right: 0.25rem !important;	    margin-right: 0.25rem !important;
  }	  }

  .me-xl-2 {	  .me-xl-2 {
    margin-right: 0.5rem !important;	    margin-right: 0.5rem !important;
  }	  }

  .me-xl-3 {	  .me-xl-3 {
    margin-right: 1rem !important;	    margin-right: 1rem !important;
  }	  }

  .me-xl-4 {	  .me-xl-4 {
    margin-right: 1.5rem !important;	    margin-right: 1.5rem !important;
  }	  }

  .me-xl-5 {	  .me-xl-5 {
    margin-right: 3rem !important;	    margin-right: 3rem !important;
  }	  }

  .me-xl-auto {	  .me-xl-auto {
    margin-right: auto !important;	    margin-right: auto !important;
  }	  }

  .mb-xl-0 {	  .mb-xl-0 {
    margin-bottom: 0 !important;	    margin-bottom: 0 !important;
  }	  }

  .mb-xl-1 {	  .mb-xl-1 {
    margin-bottom: 0.25rem !important;	    margin-bottom: 0.25rem !important;
  }	  }

  .mb-xl-2 {	  .mb-xl-2 {
    margin-bottom: 0.5rem !important;	    margin-bottom: 0.5rem !important;
  }	  }

  .mb-xl-3 {	  .mb-xl-3 {
    margin-bottom: 1rem !important;	    margin-bottom: 1rem !important;
  }	  }

  .mb-xl-4 {	  .mb-xl-4 {
    margin-bottom: 1.5rem !important;	    margin-bottom: 1.5rem !important;
  }	  }

  .mb-xl-5 {	  .mb-xl-5 {
    margin-bottom: 3rem !important;	    margin-bottom: 3rem !important;
  }	  }

  .mb-xl-auto {	  .mb-xl-auto {
    margin-bottom: auto !important;	    margin-bottom: auto !important;
  }	  }

  .ms-xl-0 {	  .ms-xl-0 {
    margin-left: 0 !important;	    margin-left: 0 !important;
  }	  }

  .ms-xl-1 {	  .ms-xl-1 {
    margin-left: 0.25rem !important;	    margin-left: 0.25rem !important;
  }	  }

  .ms-xl-2 {	  .ms-xl-2 {
    margin-left: 0.5rem !important;	    margin-left: 0.5rem !important;
  }	  }

  .ms-xl-3 {	  .ms-xl-3 {
    margin-left: 1rem !important;	    margin-left: 1rem !important;
  }	  }

  .ms-xl-4 {	  .ms-xl-4 {
    margin-left: 1.5rem !important;	    margin-left: 1.5rem !important;
  }	  }

  .ms-xl-5 {	  .ms-xl-5 {
    margin-left: 3rem !important;	    margin-left: 3rem !important;
  }	  }

  .ms-xl-auto {	  .ms-xl-auto {
    margin-left: auto !important;	    margin-left: auto !important;
  }	  }

  .p-xl-0 {	  .p-xl-0 {
    padding: 0 !important;	    padding: 0 !important;
  }	  }

  .p-xl-1 {	  .p-xl-1 {
    padding: 0.25rem !important;	    padding: 0.25rem !important;
  }	  }

  .p-xl-2 {	  .p-xl-2 {
    padding: 0.5rem !important;	    padding: 0.5rem !important;
  }	  }

  .p-xl-3 {	  .p-xl-3 {
    padding: 1rem !important;	    padding: 1rem !important;
  }	  }

  .p-xl-4 {	  .p-xl-4 {
    padding: 1.5rem !important;	    padding: 1.5rem !important;
  }	  }

  .p-xl-5 {	  .p-xl-5 {
    padding: 3rem !important;	    padding: 3rem !important;
  }	  }

  .px-xl-0 {	  .px-xl-0 {
    padding-right: 0 !important;	    padding-right: 0 !important;
    padding-left: 0 !important;	    padding-left: 0 !important;
  }	  }

  .px-xl-1 {	  .px-xl-1 {
    padding-right: 0.25rem !important;	    padding-right: 0.25rem !important;
    padding-left: 0.25rem !important;	    padding-left: 0.25rem !important;
  }	  }

  .px-xl-2 {	  .px-xl-2 {
    padding-right: 0.5rem !important;	    padding-right: 0.5rem !important;
    padding-left: 0.5rem !important;	    padding-left: 0.5rem !important;
  }	  }

  .px-xl-3 {	  .px-xl-3 {
    padding-right: 1rem !important;	    padding-right: 1rem !important;
    padding-left: 1rem !important;	    padding-left: 1rem !important;
  }	  }

  .px-xl-4 {	  .px-xl-4 {
    padding-right: 1.5rem !important;	    padding-right: 1.5rem !important;
    padding-left: 1.5rem !important;	    padding-left: 1.5rem !important;
  }	  }

  .px-xl-5 {	  .px-xl-5 {
    padding-right: 3rem !important;	    padding-right: 3rem !important;
    padding-left: 3rem !important;	    padding-left: 3rem !important;
  }	  }

  .py-xl-0 {	  .py-xl-0 {
    padding-top: 0 !important;	    padding-top: 0 !important;
    padding-bottom: 0 !important;	    padding-bottom: 0 !important;
  }	  }

  .py-xl-1 {	  .py-xl-1 {
    padding-top: 0.25rem !important;	    padding-top: 0.25rem !important;
    padding-bottom: 0.25rem !important;	    padding-bottom: 0.25rem !important;
  }	  }

  .py-xl-2 {	  .py-xl-2 {
    padding-top: 0.5rem !important;	    padding-top: 0.5rem !important;
    padding-bottom: 0.5rem !important;	    padding-bottom: 0.5rem !important;
  }	  }

  .py-xl-3 {	  .py-xl-3 {
    padding-top: 1rem !important;	    padding-top: 1rem !important;
    padding-bottom: 1rem !important;	    padding-bottom: 1rem !important;
  }	  }

  .py-xl-4 {	  .py-xl-4 {
    padding-top: 1.5rem !important;	    padding-top: 1.5rem !important;
    padding-bottom: 1.5rem !important;	    padding-bottom: 1.5rem !important;
  }	  }

  .py-xl-5 {	  .py-xl-5 {
    padding-top: 3rem !important;	    padding-top: 3rem !important;
    padding-bottom: 3rem !important;	    padding-bottom: 3rem !important;
  }	  }

  .pt-xl-0 {	  .pt-xl-0 {
    padding-top: 0 !important;	    padding-top: 0 !important;
  }	  }

  .pt-xl-1 {	  .pt-xl-1 {
    padding-top: 0.25rem !important;	    padding-top: 0.25rem !important;
  }	  }

  .pt-xl-2 {	  .pt-xl-2 {
    padding-top: 0.5rem !important;	    padding-top: 0.5rem !important;
  }	  }

  .pt-xl-3 {	  .pt-xl-3 {
    padding-top: 1rem !important;	    padding-top: 1rem !important;
  }	  }

  .pt-xl-4 {	  .pt-xl-4 {
    padding-top: 1.5rem !important;	    padding-top: 1.5rem !important;
  }	  }

  .pt-xl-5 {	  .pt-xl-5 {
    padding-top: 3rem !important;	    padding-top: 3rem !important;
  }	  }

  .pe-xl-0 {	  .pe-xl-0 {
    padding-right: 0 !important;	    padding-right: 0 !important;
  }	  }

  .pe-xl-1 {	  .pe-xl-1 {
    padding-right: 0.25rem !important;	    padding-right: 0.25rem !important;
  }	  }

  .pe-xl-2 {	  .pe-xl-2 {
    padding-right: 0.5rem !important;	    padding-right: 0.5rem !important;
  }	  }

  .pe-xl-3 {	  .pe-xl-3 {
    padding-right: 1rem !important;	    padding-right: 1rem !important;
  }	  }

  .pe-xl-4 {	  .pe-xl-4 {
    padding-right: 1.5rem !important;	    padding-right: 1.5rem !important;
  }	  }

  .pe-xl-5 {	  .pe-xl-5 {
    padding-right: 3rem !important;	    padding-right: 3rem !important;
  }	  }

  .pb-xl-0 {	  .pb-xl-0 {
    padding-bottom: 0 !important;	    padding-bottom: 0 !important;
  }	  }

  .pb-xl-1 {	  .pb-xl-1 {
    padding-bottom: 0.25rem !important;	    padding-bottom: 0.25rem !important;
  }	  }

  .pb-xl-2 {	  .pb-xl-2 {
    padding-bottom: 0.5rem !important;	    padding-bottom: 0.5rem !important;
  }	  }

  .pb-xl-3 {	  .pb-xl-3 {
    padding-bottom: 1rem !important;	    padding-bottom: 1rem !important;
  }	  }

  .pb-xl-4 {	  .pb-xl-4 {
    padding-bottom: 1.5rem !important;	    padding-bottom: 1.5rem !important;
  }	  }

  .pb-xl-5 {	  .pb-xl-5 {
    padding-bottom: 3rem !important;	    padding-bottom: 3rem !important;
  }	  }

  .ps-xl-0 {	  .ps-xl-0 {
    padding-left: 0 !important;	    padding-left: 0 !important;
  }	  }

  .ps-xl-1 {	  .ps-xl-1 {
    padding-left: 0.25rem !important;	    padding-left: 0.25rem !important;
  }	  }

  .ps-xl-2 {	  .ps-xl-2 {
    padding-left: 0.5rem !important;	    padding-left: 0.5rem !important;
  }	  }

  .ps-xl-3 {	  .ps-xl-3 {
    padding-left: 1rem !important;	    padding-left: 1rem !important;
  }	  }

  .ps-xl-4 {	  .ps-xl-4 {
    padding-left: 1.5rem !important;	    padding-left: 1.5rem !important;
  }	  }

  .ps-xl-5 {	  .ps-xl-5 {
    padding-left: 3rem !important;	    padding-left: 3rem !important;
  }	  }

  .gap-xl-0 {
    gap: 0 !important;
  }
  .gap-xl-1 {
    gap: 0.25rem !important;
  }
  .gap-xl-2 {
    gap: 0.5rem !important;
  }
  .gap-xl-3 {
    gap: 1rem !important;
  }
  .gap-xl-4 {
    gap: 1.5rem !important;
  }
  .gap-xl-5 {
    gap: 3rem !important;
  }
  .text-xl-start {	  .text-xl-start {
    text-align: left !important;	    text-align: left !important;
  }	  }

  .text-xl-end {	  .text-xl-end {
    text-align: right !important;	    text-align: right !important;
  }	  }

  .text-xl-center {	  .text-xl-center {
    text-align: center !important;	    text-align: center !important;
  }	  }
@@ -10581,649 +10286,494 @@ textarea.form-control-lg {
  .float-xxl-start {	  .float-xxl-start {
    float: left !important;	    float: left !important;
  }	  }

  .float-xxl-end {	  .float-xxl-end {
    float: right !important;	    float: right !important;
  }	  }

  .float-xxl-none {	  .float-xxl-none {
    float: none !important;	    float: none !important;
  }	  }

  .d-xxl-inline {	  .d-xxl-inline {
    display: inline !important;	    display: inline !important;
  }	  }

  .d-xxl-inline-block {	  .d-xxl-inline-block {
    display: inline-block !important;	    display: inline-block !important;
  }	  }

  .d-xxl-block {	  .d-xxl-block {
    display: block !important;	    display: block !important;
  }	  }

  .d-xxl-grid {	  .d-xxl-grid {
    display: grid !important;	    display: grid !important;
  }	  }

  .d-xxl-table {	  .d-xxl-table {
    display: table !important;	    display: table !important;
  }	  }

  .d-xxl-table-row {	  .d-xxl-table-row {
    display: table-row !important;	    display: table-row !important;
  }	  }

  .d-xxl-table-cell {	  .d-xxl-table-cell {
    display: table-cell !important;	    display: table-cell !important;
  }	  }

  .d-xxl-flex {	  .d-xxl-flex {
    display: flex !important;	    display: flex !important;
  }	  }

  .d-xxl-inline-flex {	  .d-xxl-inline-flex {
    display: inline-flex !important;	    display: inline-flex !important;
  }	  }

  .d-xxl-none {	  .d-xxl-none {
    display: none !important;	    display: none !important;
  }	  }

  .flex-xxl-fill {	  .flex-xxl-fill {
    flex: 1 1 auto !important;	    flex: 1 1 auto !important;
  }	  }

  .flex-xxl-row {	  .flex-xxl-row {
    flex-direction: row !important;	    flex-direction: row !important;
  }	  }

  .flex-xxl-column {	  .flex-xxl-column {
    flex-direction: column !important;	    flex-direction: column !important;
  }	  }

  .flex-xxl-row-reverse {	  .flex-xxl-row-reverse {
    flex-direction: row-reverse !important;	    flex-direction: row-reverse !important;
  }	  }

  .flex-xxl-column-reverse {	  .flex-xxl-column-reverse {
    flex-direction: column-reverse !important;	    flex-direction: column-reverse !important;
  }	  }

  .flex-xxl-grow-0 {	  .flex-xxl-grow-0 {
    flex-grow: 0 !important;	    flex-grow: 0 !important;
  }	  }

  .flex-xxl-grow-1 {	  .flex-xxl-grow-1 {
    flex-grow: 1 !important;	    flex-grow: 1 !important;
  }	  }

  .flex-xxl-shrink-0 {	  .flex-xxl-shrink-0 {
    flex-shrink: 0 !important;	    flex-shrink: 0 !important;
  }	  }

  .flex-xxl-shrink-1 {	  .flex-xxl-shrink-1 {
    flex-shrink: 1 !important;	    flex-shrink: 1 !important;
  }	  }

  .flex-xxl-wrap {	  .flex-xxl-wrap {
    flex-wrap: wrap !important;	    flex-wrap: wrap !important;
  }	  }

  .flex-xxl-nowrap {	  .flex-xxl-nowrap {
    flex-wrap: nowrap !important;	    flex-wrap: nowrap !important;
  }	  }

  .flex-xxl-wrap-reverse {	  .flex-xxl-wrap-reverse {
    flex-wrap: wrap-reverse !important;	    flex-wrap: wrap-reverse !important;
  }	  }

  .gap-xxl-0 {	
    gap: 0 !important;	
  }	

  .gap-xxl-1 {	
    gap: 0.25rem !important;	
  }	

  .gap-xxl-2 {	
    gap: 0.5rem !important;	
  }	

  .gap-xxl-3 {	
    gap: 1rem !important;	
  }	

  .gap-xxl-4 {	
    gap: 1.5rem !important;	
  }	

  .gap-xxl-5 {	
    gap: 3rem !important;	
  }	

  .justify-content-xxl-start {	  .justify-content-xxl-start {
    justify-content: flex-start !important;	    justify-content: flex-start !important;
  }	  }

  .justify-content-xxl-end {	  .justify-content-xxl-end {
    justify-content: flex-end !important;	    justify-content: flex-end !important;
  }	  }

  .justify-content-xxl-center {	  .justify-content-xxl-center {
    justify-content: center !important;	    justify-content: center !important;
  }	  }

  .justify-content-xxl-between {	  .justify-content-xxl-between {
    justify-content: space-between !important;	    justify-content: space-between !important;
  }	  }

  .justify-content-xxl-around {	  .justify-content-xxl-around {
    justify-content: space-around !important;	    justify-content: space-around !important;
  }	  }

  .justify-content-xxl-evenly {	  .justify-content-xxl-evenly {
    justify-content: space-evenly !important;	    justify-content: space-evenly !important;
  }	  }

  .align-items-xxl-start {	  .align-items-xxl-start {
    align-items: flex-start !important;	    align-items: flex-start !important;
  }	  }

  .align-items-xxl-end {	  .align-items-xxl-end {
    align-items: flex-end !important;	    align-items: flex-end !important;
  }	  }

  .align-items-xxl-center {	  .align-items-xxl-center {
    align-items: center !important;	    align-items: center !important;
  }	  }

  .align-items-xxl-baseline {	  .align-items-xxl-baseline {
    align-items: baseline !important;	    align-items: baseline !important;
  }	  }

  .align-items-xxl-stretch {	  .align-items-xxl-stretch {
    align-items: stretch !important;	    align-items: stretch !important;
  }	  }

  .align-content-xxl-start {	  .align-content-xxl-start {
    align-content: flex-start !important;	    align-content: flex-start !important;
  }	  }

  .align-content-xxl-end {	  .align-content-xxl-end {
    align-content: flex-end !important;	    align-content: flex-end !important;
  }	  }

  .align-content-xxl-center {	  .align-content-xxl-center {
    align-content: center !important;	    align-content: center !important;
  }	  }

  .align-content-xxl-between {	  .align-content-xxl-between {
    align-content: space-between !important;	    align-content: space-between !important;
  }	  }

  .align-content-xxl-around {	  .align-content-xxl-around {
    align-content: space-around !important;	    align-content: space-around !important;
  }	  }

  .align-content-xxl-stretch {	  .align-content-xxl-stretch {
    align-content: stretch !important;	    align-content: stretch !important;
  }	  }

  .align-self-xxl-auto {	  .align-self-xxl-auto {
    align-self: auto !important;	    align-self: auto !important;
  }	  }

  .align-self-xxl-start {	  .align-self-xxl-start {
    align-self: flex-start !important;	    align-self: flex-start !important;
  }	  }

  .align-self-xxl-end {	  .align-self-xxl-end {
    align-self: flex-end !important;	    align-self: flex-end !important;
  }	  }

  .align-self-xxl-center {	  .align-self-xxl-center {
    align-self: center !important;	    align-self: center !important;
  }	  }

  .align-self-xxl-baseline {	  .align-self-xxl-baseline {
    align-self: baseline !important;	    align-self: baseline !important;
  }	  }

  .align-self-xxl-stretch {	  .align-self-xxl-stretch {
    align-self: stretch !important;	    align-self: stretch !important;
  }	  }

  .order-xxl-first {	  .order-xxl-first {
    order: -1 !important;	    order: -1 !important;
  }	  }

  .order-xxl-0 {	  .order-xxl-0 {
    order: 0 !important;	    order: 0 !important;
  }	  }

  .order-xxl-1 {	  .order-xxl-1 {
    order: 1 !important;	    order: 1 !important;
  }	  }

  .order-xxl-2 {	  .order-xxl-2 {
    order: 2 !important;	    order: 2 !important;
  }	  }

  .order-xxl-3 {	  .order-xxl-3 {
    order: 3 !important;	    order: 3 !important;
  }	  }

  .order-xxl-4 {	  .order-xxl-4 {
    order: 4 !important;	    order: 4 !important;
  }	  }

  .order-xxl-5 {	  .order-xxl-5 {
    order: 5 !important;	    order: 5 !important;
  }	  }

  .order-xxl-last {	  .order-xxl-last {
    order: 6 !important;	    order: 6 !important;
  }	  }

  .m-xxl-0 {	  .m-xxl-0 {
    margin: 0 !important;	    margin: 0 !important;
  }	  }

  .m-xxl-1 {	  .m-xxl-1 {
    margin: 0.25rem !important;	    margin: 0.25rem !important;
  }	  }

  .m-xxl-2 {	  .m-xxl-2 {
    margin: 0.5rem !important;	    margin: 0.5rem !important;
  }	  }

  .m-xxl-3 {	  .m-xxl-3 {
    margin: 1rem !important;	    margin: 1rem !important;
  }	  }

  .m-xxl-4 {	  .m-xxl-4 {
    margin: 1.5rem !important;	    margin: 1.5rem !important;
  }	  }

  .m-xxl-5 {	  .m-xxl-5 {
    margin: 3rem !important;	    margin: 3rem !important;
  }	  }

  .m-xxl-auto {	  .m-xxl-auto {
    margin: auto !important;	    margin: auto !important;
  }	  }

  .mx-xxl-0 {	  .mx-xxl-0 {
    margin-right: 0 !important;	    margin-right: 0 !important;
    margin-left: 0 !important;	    margin-left: 0 !important;
  }	  }

  .mx-xxl-1 {	  .mx-xxl-1 {
    margin-right: 0.25rem !important;	    margin-right: 0.25rem !important;
    margin-left: 0.25rem !important;	    margin-left: 0.25rem !important;
  }	  }

  .mx-xxl-2 {	  .mx-xxl-2 {
    margin-right: 0.5rem !important;	    margin-right: 0.5rem !important;
    margin-left: 0.5rem !important;	    margin-left: 0.5rem !important;
  }	  }

  .mx-xxl-3 {	  .mx-xxl-3 {
    margin-right: 1rem !important;	    margin-right: 1rem !important;
    margin-left: 1rem !important;	    margin-left: 1rem !important;
  }	  }

  .mx-xxl-4 {	  .mx-xxl-4 {
    margin-right: 1.5rem !important;	    margin-right: 1.5rem !important;
    margin-left: 1.5rem !important;	    margin-left: 1.5rem !important;
  }	  }

  .mx-xxl-5 {	  .mx-xxl-5 {
    margin-right: 3rem !important;	    margin-right: 3rem !important;
    margin-left: 3rem !important;	    margin-left: 3rem !important;
  }	  }

  .mx-xxl-auto {	  .mx-xxl-auto {
    margin-right: auto !important;	    margin-right: auto !important;
    margin-left: auto !important;	    margin-left: auto !important;
  }	  }

  .my-xxl-0 {	  .my-xxl-0 {
    margin-top: 0 !important;	    margin-top: 0 !important;
    margin-bottom: 0 !important;	    margin-bottom: 0 !important;
  }	  }

  .my-xxl-1 {	  .my-xxl-1 {
    margin-top: 0.25rem !important;	    margin-top: 0.25rem !important;
    margin-bottom: 0.25rem !important;	    margin-bottom: 0.25rem !important;
  }	  }

  .my-xxl-2 {	  .my-xxl-2 {
    margin-top: 0.5rem !important;	    margin-top: 0.5rem !important;
    margin-bottom: 0.5rem !important;	    margin-bottom: 0.5rem !important;
  }	  }

  .my-xxl-3 {	  .my-xxl-3 {
    margin-top: 1rem !important;	    margin-top: 1rem !important;
    margin-bottom: 1rem !important;	    margin-bottom: 1rem !important;
  }	  }

  .my-xxl-4 {	  .my-xxl-4 {
    margin-top: 1.5rem !important;	    margin-top: 1.5rem !important;
    margin-bottom: 1.5rem !important;	    margin-bottom: 1.5rem !important;
  }	  }

  .my-xxl-5 {	  .my-xxl-5 {
    margin-top: 3rem !important;	    margin-top: 3rem !important;
    margin-bottom: 3rem !important;	    margin-bottom: 3rem !important;
  }	  }

  .my-xxl-auto {	  .my-xxl-auto {
    margin-top: auto !important;	    margin-top: auto !important;
    margin-bottom: auto !important;	    margin-bottom: auto !important;
  }	  }

  .mt-xxl-0 {	  .mt-xxl-0 {
    margin-top: 0 !important;	    margin-top: 0 !important;
  }	  }

  .mt-xxl-1 {	  .mt-xxl-1 {
    margin-top: 0.25rem !important;	    margin-top: 0.25rem !important;
  }	  }

  .mt-xxl-2 {	  .mt-xxl-2 {
    margin-top: 0.5rem !important;	    margin-top: 0.5rem !important;
  }	  }

  .mt-xxl-3 {	  .mt-xxl-3 {
    margin-top: 1rem !important;	    margin-top: 1rem !important;
  }	  }

  .mt-xxl-4 {	  .mt-xxl-4 {
    margin-top: 1.5rem !important;	    margin-top: 1.5rem !important;
  }	  }

  .mt-xxl-5 {	  .mt-xxl-5 {
    margin-top: 3rem !important;	    margin-top: 3rem !important;
  }	  }

  .mt-xxl-auto {	  .mt-xxl-auto {
    margin-top: auto !important;	    margin-top: auto !important;
  }	  }

  .me-xxl-0 {	  .me-xxl-0 {
    margin-right: 0 !important;	    margin-right: 0 !important;
  }	  }

  .me-xxl-1 {	  .me-xxl-1 {
    margin-right: 0.25rem !important;	    margin-right: 0.25rem !important;
  }	  }

  .me-xxl-2 {	  .me-xxl-2 {
    margin-right: 0.5rem !important;	    margin-right: 0.5rem !important;
  }	  }

  .me-xxl-3 {	  .me-xxl-3 {
    margin-right: 1rem !important;	    margin-right: 1rem !important;
  }	  }

  .me-xxl-4 {	  .me-xxl-4 {
    margin-right: 1.5rem !important;	    margin-right: 1.5rem !important;
  }	  }

  .me-xxl-5 {	  .me-xxl-5 {
    margin-right: 3rem !important;	    margin-right: 3rem !important;
  }	  }

  .me-xxl-auto {	  .me-xxl-auto {
    margin-right: auto !important;	    margin-right: auto !important;
  }	  }

  .mb-xxl-0 {	  .mb-xxl-0 {
    margin-bottom: 0 !important;	    margin-bottom: 0 !important;
  }	  }

  .mb-xxl-1 {	  .mb-xxl-1 {
    margin-bottom: 0.25rem !important;	    margin-bottom: 0.25rem !important;
  }	  }

  .mb-xxl-2 {	  .mb-xxl-2 {
    margin-bottom: 0.5rem !important;	    margin-bottom: 0.5rem !important;
  }	  }

  .mb-xxl-3 {	  .mb-xxl-3 {
    margin-bottom: 1rem !important;	    margin-bottom: 1rem !important;
  }	  }

  .mb-xxl-4 {	  .mb-xxl-4 {
    margin-bottom: 1.5rem !important;	    margin-bottom: 1.5rem !important;
  }	  }

  .mb-xxl-5 {	  .mb-xxl-5 {
    margin-bottom: 3rem !important;	    margin-bottom: 3rem !important;
  }	  }

  .mb-xxl-auto {	  .mb-xxl-auto {
    margin-bottom: auto !important;	    margin-bottom: auto !important;
  }	  }

  .ms-xxl-0 {	  .ms-xxl-0 {
    margin-left: 0 !important;	    margin-left: 0 !important;
  }	  }

  .ms-xxl-1 {	  .ms-xxl-1 {
    margin-left: 0.25rem !important;	    margin-left: 0.25rem !important;
  }	  }

  .ms-xxl-2 {	  .ms-xxl-2 {
    margin-left: 0.5rem !important;	    margin-left: 0.5rem !important;
  }	  }

  .ms-xxl-3 {	  .ms-xxl-3 {
    margin-left: 1rem !important;	    margin-left: 1rem !important;
  }	  }

  .ms-xxl-4 {	  .ms-xxl-4 {
    margin-left: 1.5rem !important;	    margin-left: 1.5rem !important;
  }	  }

  .ms-xxl-5 {	  .ms-xxl-5 {
    margin-left: 3rem !important;	    margin-left: 3rem !important;
  }	  }

  .ms-xxl-auto {	  .ms-xxl-auto {
    margin-left: auto !important;	    margin-left: auto !important;
  }	  }

  .p-xxl-0 {	  .p-xxl-0 {
    padding: 0 !important;	    padding: 0 !important;
  }	  }

  .p-xxl-1 {	  .p-xxl-1 {
    padding: 0.25rem !important;	    padding: 0.25rem !important;
  }	  }

  .p-xxl-2 {	  .p-xxl-2 {
    padding: 0.5rem !important;	    padding: 0.5rem !important;
  }	  }

  .p-xxl-3 {	  .p-xxl-3 {
    padding: 1rem !important;	    padding: 1rem !important;
  }	  }

  .p-xxl-4 {	  .p-xxl-4 {
    padding: 1.5rem !important;	    padding: 1.5rem !important;
  }	  }

  .p-xxl-5 {	  .p-xxl-5 {
    padding: 3rem !important;	    padding: 3rem !important;
  }	  }

  .px-xxl-0 {	  .px-xxl-0 {
    padding-right: 0 !important;	    padding-right: 0 !important;
    padding-left: 0 !important;	    padding-left: 0 !important;
  }	  }

  .px-xxl-1 {	  .px-xxl-1 {
    padding-right: 0.25rem !important;	    padding-right: 0.25rem !important;
    padding-left: 0.25rem !important;	    padding-left: 0.25rem !important;
  }	  }

  .px-xxl-2 {	  .px-xxl-2 {
    padding-right: 0.5rem !important;	    padding-right: 0.5rem !important;
    padding-left: 0.5rem !important;	    padding-left: 0.5rem !important;
  }	  }

  .px-xxl-3 {	  .px-xxl-3 {
    padding-right: 1rem !important;	    padding-right: 1rem !important;
    padding-left: 1rem !important;	    padding-left: 1rem !important;
  }	  }

  .px-xxl-4 {	  .px-xxl-4 {
    padding-right: 1.5rem !important;	    padding-right: 1.5rem !important;
    padding-left: 1.5rem !important;	    padding-left: 1.5rem !important;
  }	  }

  .px-xxl-5 {	  .px-xxl-5 {
    padding-right: 3rem !important;	    padding-right: 3rem !important;
    padding-left: 3rem !important;	    padding-left: 3rem !important;
  }	  }

  .py-xxl-0 {	  .py-xxl-0 {
    padding-top: 0 !important;	    padding-top: 0 !important;
    padding-bottom: 0 !important;	    padding-bottom: 0 !important;
  }	  }

  .py-xxl-1 {	  .py-xxl-1 {
    padding-top: 0.25rem !important;	    padding-top: 0.25rem !important;
    padding-bottom: 0.25rem !important;	    padding-bottom: 0.25rem !important;
  }	  }

  .py-xxl-2 {	  .py-xxl-2 {
    padding-top: 0.5rem !important;	    padding-top: 0.5rem !important;
    padding-bottom: 0.5rem !important;	    padding-bottom: 0.5rem !important;
  }	  }

  .py-xxl-3 {	  .py-xxl-3 {
    padding-top: 1rem !important;	    padding-top: 1rem !important;
    padding-bottom: 1rem !important;	    padding-bottom: 1rem !important;
  }	  }

  .py-xxl-4 {	  .py-xxl-4 {
    padding-top: 1.5rem !important;	    padding-top: 1.5rem !important;
    padding-bottom: 1.5rem !important;	    padding-bottom: 1.5rem !important;
  }	  }

  .py-xxl-5 {	  .py-xxl-5 {
    padding-top: 3rem !important;	    padding-top: 3rem !important;
    padding-bottom: 3rem !important;	    padding-bottom: 3rem !important;
  }	  }

  .pt-xxl-0 {	  .pt-xxl-0 {
    padding-top: 0 !important;	    padding-top: 0 !important;
  }	  }

  .pt-xxl-1 {	  .pt-xxl-1 {
    padding-top: 0.25rem !important;	    padding-top: 0.25rem !important;
  }	  }

  .pt-xxl-2 {	  .pt-xxl-2 {
    padding-top: 0.5rem !important;	    padding-top: 0.5rem !important;
  }	  }

  .pt-xxl-3 {	  .pt-xxl-3 {
    padding-top: 1rem !important;	    padding-top: 1rem !important;
  }	  }

  .pt-xxl-4 {	  .pt-xxl-4 {
    padding-top: 1.5rem !important;	    padding-top: 1.5rem !important;
  }	  }

  .pt-xxl-5 {	  .pt-xxl-5 {
    padding-top: 3rem !important;	    padding-top: 3rem !important;
  }	  }

  .pe-xxl-0 {	  .pe-xxl-0 {
    padding-right: 0 !important;	    padding-right: 0 !important;
  }	  }

  .pe-xxl-1 {	  .pe-xxl-1 {
    padding-right: 0.25rem !important;	    padding-right: 0.25rem !important;
  }	  }

  .pe-xxl-2 {	  .pe-xxl-2 {
    padding-right: 0.5rem !important;	    padding-right: 0.5rem !important;
  }	  }

  .pe-xxl-3 {	  .pe-xxl-3 {
    padding-right: 1rem !important;	    padding-right: 1rem !important;
  }	  }

  .pe-xxl-4 {	  .pe-xxl-4 {
    padding-right: 1.5rem !important;	    padding-right: 1.5rem !important;
  }	  }

  .pe-xxl-5 {	  .pe-xxl-5 {
    padding-right: 3rem !important;	    padding-right: 3rem !important;
  }	  }

  .pb-xxl-0 {	  .pb-xxl-0 {
    padding-bottom: 0 !important;	    padding-bottom: 0 !important;
  }	  }

  .pb-xxl-1 {	  .pb-xxl-1 {
    padding-bottom: 0.25rem !important;	    padding-bottom: 0.25rem !important;
  }	  }

  .pb-xxl-2 {	  .pb-xxl-2 {
    padding-bottom: 0.5rem !important;	    padding-bottom: 0.5rem !important;
  }	  }

  .pb-xxl-3 {	  .pb-xxl-3 {
    padding-bottom: 1rem !important;	    padding-bottom: 1rem !important;
  }	  }

  .pb-xxl-4 {	  .pb-xxl-4 {
    padding-bottom: 1.5rem !important;	    padding-bottom: 1.5rem !important;
  }	  }

  .pb-xxl-5 {	  .pb-xxl-5 {
    padding-bottom: 3rem !important;	    padding-bottom: 3rem !important;
  }	  }

  .ps-xxl-0 {	  .ps-xxl-0 {
    padding-left: 0 !important;	    padding-left: 0 !important;
  }	  }

  .ps-xxl-1 {	  .ps-xxl-1 {
    padding-left: 0.25rem !important;	    padding-left: 0.25rem !important;
  }	  }

  .ps-xxl-2 {	  .ps-xxl-2 {
    padding-left: 0.5rem !important;	    padding-left: 0.5rem !important;
  }	  }

  .ps-xxl-3 {	  .ps-xxl-3 {
    padding-left: 1rem !important;	    padding-left: 1rem !important;
  }	  }

  .ps-xxl-4 {	  .ps-xxl-4 {
    padding-left: 1.5rem !important;	    padding-left: 1.5rem !important;
  }	  }

  .ps-xxl-5 {	  .ps-xxl-5 {
    padding-left: 3rem !important;	    padding-left: 3rem !important;
  }	  }

  .gap-xxl-0 {
    gap: 0 !important;
  }
  .gap-xxl-1 {
    gap: 0.25rem !important;
  }
  .gap-xxl-2 {
    gap: 0.5rem !important;
  }
  .gap-xxl-3 {
    gap: 1rem !important;
  }
  .gap-xxl-4 {
    gap: 1.5rem !important;
  }
  .gap-xxl-5 {
    gap: 3rem !important;
  }
  .text-xxl-start {	  .text-xxl-start {
    text-align: left !important;	    text-align: left !important;
  }	  }

  .text-xxl-end {	  .text-xxl-end {
    text-align: right !important;	    text-align: right !important;
  }	  }

  .text-xxl-center {	  .text-xxl-center {
    text-align: center !important;	    text-align: center !important;
  }	  }
@@ -11232,15 +10782,12 @@ textarea.form-control-lg {
  .fs-1 {	  .fs-1 {
    font-size: 2.5rem !important;	    font-size: 2.5rem !important;
  }	  }

  .fs-2 {	  .fs-2 {
    font-size: 2rem !important;	    font-size: 2rem !important;
  }	  }

  .fs-3 {	  .fs-3 {
    font-size: 1.75rem !important;	    font-size: 1.75rem !important;
  }	  }

  .fs-4 {	  .fs-4 {
    font-size: 1.5rem !important;	    font-size: 1.5rem !important;
  }	  }
@@ -11249,39 +10796,30 @@ textarea.form-control-lg {
  .d-print-inline {	  .d-print-inline {
    display: inline !important;	    display: inline !important;
  }	  }

  .d-print-inline-block {	  .d-print-inline-block {
    display: inline-block !important;	    display: inline-block !important;
  }	  }

  .d-print-block {	  .d-print-block {
    display: block !important;	    display: block !important;
  }	  }

  .d-print-grid {	  .d-print-grid {
    display: grid !important;	    display: grid !important;
  }	  }

  .d-print-table {	  .d-print-table {
    display: table !important;	    display: table !important;
  }	  }

  .d-print-table-row {	  .d-print-table-row {
    display: table-row !important;	    display: table-row !important;
  }	  }

  .d-print-table-cell {	  .d-print-table-cell {
    display: table-cell !important;	    display: table-cell !important;
  }	  }

  .d-print-flex {	  .d-print-flex {
    display: flex !important;	    display: flex !important;
  }	  }

  .d-print-inline-flex {	  .d-print-inline-flex {
    display: inline-flex !important;	    display: inline-flex !important;
  }	  }

  .d-print-none {	  .d-print-none {
    display: none !important;	    display: none !important;
  }	  }
  4 changes: 2 additions & 2 deletions4  
dist/index.html
@@ -257,10 +257,10 @@ <h5 class="fw-bolder">Popular Item</h5>
        </section>	        </section>
        <!-- Footer-->	        <!-- Footer-->
        <footer class="py-5 bg-dark">	        <footer class="py-5 bg-dark">
            <div class="container"><p class="m-0 text-center text-white">Copyright &copy; Your Website 2022</p></div>	            <div class="container"><p class="m-0 text-center text-white">Copyright &copy; Your Website 2023</p></div>
        </footer>	        </footer>
        <!-- Bootstrap core JS-->	        <!-- Bootstrap core JS-->
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js"></script>	        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js"></script>
        <!-- Core theme JS-->	        <!-- Core theme JS-->
        <script src="js/scripts.js"></script>	        <script src="js/scripts.js"></script>
    </body>	    </body>
 4 changes: 2 additions & 2 deletions4  
dist/js/scripts.js
@@ -1,6 +1,6 @@
/*!	/*!
* Start Bootstrap - Shop Homepage v5.0.5 (https://startbootstrap.com/template/shop-homepage)	* Start Bootstrap - Shop Homepage v5.0.6 (https://startbootstrap.com/template/shop-homepage)
* Copyright 2013-2022 Start Bootstrap	* Copyright 2013-2023 Start Bootstrap
* Licensed under MIT (https://github.com/StartBootstrap/startbootstrap-shop-homepage/blob/master/LICENSE)	* Licensed under MIT (https://github.com/StartBootstrap/startbootstrap-shop-homepage/blob/master/LICENSE)
*/	*/
// This file is intentionally blank	// This file is intentionally blank
 3,138 changes: 2,837 additions & 301 deletions3,138  
package-lock.json
Large diffs are not rendered by default.

  16 changes: 8 additions & 8 deletions16  
package.json
@@ -1,7 +1,7 @@
{	{
    "title": "Shop Homepage",	    "title": "Shop Homepage",
    "name": "startbootstrap-shop-homepage",	    "name": "startbootstrap-shop-homepage",
    "version": "5.0.5",	    "version": "5.0.6",
    "scripts": {	    "scripts": {
        "build": "npm run clean && npm run build:pug && npm run build:scss && npm run build:scripts && npm run build:assets",	        "build": "npm run clean && npm run build:pug && npm run build:scss && npm run build:scripts && npm run build:assets",
        "build:assets": "node scripts/build-assets.js",	        "build:assets": "node scripts/build-assets.js",
@@ -36,18 +36,18 @@
        "url": "https://github.com/StartBootstrap/startbootstrap-shop-homepage.git"	        "url": "https://github.com/StartBootstrap/startbootstrap-shop-homepage.git"
    },	    },
    "dependencies": {	    "dependencies": {
        "bootstrap": "5.1.3"	        "bootstrap": "5.2.3"
    },	    },
    "devDependencies": {	    "devDependencies": {
        "autoprefixer": "10.4.4",	        "autoprefixer": "10.4.14",
        "browser-sync": "2.27.9",	        "browser-sync": "2.29.1",
        "chokidar": "3.5.3",	        "chokidar": "3.5.3",
        "concurrently": "6.3.0",	        "concurrently": "6.3.0",
        "postcss": "8.4.12",	        "postcss": "8.4.21",
        "prettier": "2.6.0",	        "prettier": "2.8.6",
        "pug": "3.0.2",	        "pug": "3.0.2",
        "sass": "1.49.9",	        "sass": "1.60.0",
        "shelljs": "0.8.5",	        "shelljs": "0.8.5",
        "upath": "2.0.1"	        "upath": "2.0.1"
    }	    }
}	}
  4 changes: 2 additions & 2 deletions4  
src/pug/index.pug
@@ -226,10 +226,10 @@ html(lang='en')
        // Footer	        // Footer
        footer.py-5.bg-dark	        footer.py-5.bg-dark
            .container	            .container
                p.m-0.text-center.text-white Copyright &copy; Your Website 2022	                p.m-0.text-center.text-white Copyright &copy; Your Website 2023


        // Bootstrap core JS	        // Bootstrap core JS
        script(src='https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js')	        script(src='https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js')


        // Core theme JS	        // Core theme JS
        script(src='js/scripts.js')	





