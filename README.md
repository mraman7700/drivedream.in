<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <!-- 
    - primary meta tags
  -->
  <title>Drive Dream</title>
  <style>



/*-----------------------------------*\
  #style.css
\*-----------------------------------*/

/**
 * copyright 2022 codewithsadee
 */





/*-----------------------------------*\
  #CUSTOM PROPERTY
\*-----------------------------------*/

:root {

/**
 * colors
 */

--smokey-black: hsl(0, 0%, 7%);
--eerie-black: hsl(0, 0%, 9%);
--radical-red: hsl(346, 100%, 58%);
--white_a9: hsla(0, 0%, 100%, 0.09);
--white_a15: hsla(0, 0%, 100%, 0.15);
--white_a25: hsla(0, 0%, 100%, 0.25);
--white_a50: hsla(0, 0%, 100%, 0.5);
--white_a70: hsla(0, 0%, 100%, 0.7);
--white_a75: hsla(0, 0%, 100%, 0.75);
--white_a80: hsla(0, 0%, 100%, 0.8);
--jet-1: hsl(0, 0%, 20%);
--jet-2: hsl(0, 0%, 16%);
--white: hsl(0, 0%, 100%);
--black: hsl(0, 0%, 0%);

/**
 * gradient color
 */

--gradient-1: linear-gradient(180deg, transparent, var(--black));
--gradient-2: linear-gradient(180deg,var(--black) 25%,hsla(0, 0%, 0%, 0.6) 80%);

/**
 * typography
 */

--ff-recoleta: "Recoleta", serif;
--ff-gordita: "Gordita", sans-serif;

--fs-1: 6rem;
--fs-2: 5rem;
--fs-3: 3.8rem;
--fs-4: 2.8rem;
--fs-5: 2.6rem;
--fs-6: 2.2rem;
--fs-7: 2rem;
--fs-8: 1.8rem;
--fs-9: 1.5rem;
--fs-10: 1.4rem;
--fs-11: 1.2rem;

--fw-300: 300;
--fw-400: 400;
--fw-500: 500;

/**
 * spacing
 */

--section-padding: 60px;

/**
 * shadow
 */

--shadow: 0 12px 30px -10px hsla(0, 0%, 14%, 0.1);

/**
 * border radius
 */

--radius-circle: 50%;
--radius-5: 5px;
--radius-25: 25px;

/**
 * transition
 */

--transition-1: 0.25s ease;
--transition-2: 0.5s ease;
--transition-3: 1s ease;
--cubic-in: cubic-bezier(0.51, 0.03, 0.64, 0.28);
--cubic-out: cubic-bezier(0.33, 0.85, 0.4, 0.96);

}





/*-----------------------------------*\
#RESET
\*-----------------------------------*/

*,
*::before,
*::after {
margin: 0;
padding: 0;
box-sizing: border-box;
}

li { list-style: none; }

a,
img,
span,
button,
ion-icon { display: block; }

a {
color: inherit;
text-decoration: none;
}

img { height: auto; }

button {
background: none;
border: none;
font: inherit;
cursor: pointer;
}

ion-icon { pointer-events: none; }

address { font-style: normal; }

html {
font-family: var(--ff-gordita);
font-size: 10px;
scroll-behavior: smooth;
}

body {
background-color: black;
color: var(--white);
font-size: 1.6rem;
font-weight: var(--fw-400);
line-height: 2.15;
overflow-x: hidden;
}

body.active { overflow: hidden; }

:focus-visible { outline-offset: 4px; }

::-webkit-scrollbar { width: 5px; }

::-webkit-scrollbar-track { background-color: var(--white); }

::-webkit-scrollbar-thumb { background-color: var(--jet-2); }





/*-----------------------------------*\
#REUSED STYLE
\*-----------------------------------*/

.container { padding-inline: 15px; }

.shape { display: none; }

.section { padding-block: var(--section-padding); }

.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
font-family: var(--ff-recoleta);
line-height: 1.2;
}

.h1 {
font-size: var(--fs-1);
font-weight: var(--fw-400);
}

.h2,
.h3,
.h4,
.h5,
.h6 { font-weight: var(--fw-300); }

.h2 { font-size: var(--fs-2); }

.h3 { font-size: var(--fs-3); }

.h4 { font-size: var(--fs-4); }

.h5 { font-size: var(--fs-5); }

.h6 { font-size: var(--fs-6); }

.img-holder {
aspect-ratio: var(--width) / var(--height);
background-color: var(--jet-1);
overflow: hidden;
}

.has-before {
position: relative;
z-index: 1;
}

.has-before::before {
content: "";
position: absolute;
}

.img-holder.has-before::before {
bottom: 0;
left: 0;
width: 100%;
height: 50%;
background-image: var(--gradient-1);
}

.img-cover {
width: 100%;
height: 100%;
object-fit: cover;
}

.btn-icon {
background-color: var(--bg-color, var(--white));
border-radius: var(--border-radius, var(--radius-circle));
display: grid;
place-content: center;
transition: var(--transition-2);
}

.btn-icon path { transition: var(--transition-2); }

.btn-icon:is(:hover, :focus-visible) {
background-color: var(--hover-bg-color, var(--white));
}

.btn-icon:is(:hover, :focus-visible) path {
stroke: var(--hover-text-color, var(--black));
}

.section-subtitle {
color: var(--white_a25);
font-size: var(--fs-7);
text-transform: uppercase;
letter-spacing: 3.5px;
}

[data-reveal] {
transform: translateY(50px);
opacity: 0;
transition: var(--transition-3);
}

[data-reveal="left"] { transform: translate(-50px, 0); }

[data-reveal="right"] { transform: translate(50px, 0); }

[data-reveal].revealed {
transform: translate(0, 0);
opacity: 1;
}





/*-----------------------------------*\
#LOADING
\*-----------------------------------*/

.loading {
position: fixed;
top: 0;
left: 0;
width: 100vw;
height: 100vh;
background-color: var(--white);
z-index: 5;
transform-origin: bottom;
transition: 0.5s var(--cubic-in);
transition-delay: 0.5s;
}

.loading.loaded {
transform: scaleY(0);
pointer-events: none;
}

.loading > * {
position: absolute;
top: 50%;
left: 50%;

transform: translate(-50%, -50%);
transition: var(--transition-2);
}

.loading.loaded > * { opacity: 0; }

.loading .circle { animation: rotate360 10.5s linear infinite; }

@keyframes rotate360 {
0% { transform: translate(-50%, -50%) rotate(0); }
100% { transform: translate(-50%, -50%) rotate(1turn); }
}





/*-----------------------------------*\
#HEADER
\*-----------------------------------*/

.header {
position: fixed;
top: 0;
left: 0;
width: 100%;
padding-block: 18px;
transition: var(--transition-2);
z-index: 4;
}

.header.active {
background-color: transparent;
padding-block: 12px;
box-shadow: var(--shadow);
}

.header .container,
.navbar-top {
display: flex;
justify-content: space-between;
align-items: center;
}

.navbar {
position: fixed;
top: 0;
right: -280px;
height: 100vh;
max-width: 280px;
width: 100%;
padding: 25px;
overflow-y: auto;
z-index: 2;
transition: 0.25s var(--cubic-out);
visibility: hidden;
}

.navbar.active {
visibility: visible;
transform: translateX(-280px);
transition-duration: 0.5s;
}

.navbar-top .logo .img { width: 130px; }

.nav-close-btn {
width: 50px;
height: 50px;
margin-top: 5px;
margin-right: 5px;
}

.nav-close-btn .span {
background-color: var(--white_a80);
width: 40px;
height: 4px;
border-radius: 5px;
transition: var(--transition-1);
}

.nav-close-btn .one { transform: rotate(45deg) translate(2px, 2px); }

.nav-close-btn .two { transform: rotate(-45deg); }

.nav-close-btn:is(:hover, :focus-visible) .span { background-color: var(--radical-red); }

.navbar-list {
text-align: center;
padding-block: 40px;
}

.navbar-link {
font-size: var(--fs-7);
font-weight: var(--fw-400);
padding-block: 2px;
text-transform: capitalize;
transition: var(--transition-1);
}

.navbar-link:is(:hover, :focus-visible) { color: var(--radical-red); }

.login-btn {
display: flex;
justify-content: center;
align-items: center;
gap: 15px;
width: 100%;
background-color: var(--radical-red);
color: var(--white);
padding: 8px 30px;
border-radius: var(--radius-5);
margin-block-end: 50px;
}

.login-btn .span { font-weight: var(--fw-500); }

.navbar-title {
font-size: var(--fs-8);
font-weight: var(--fw-500);
line-height: 1;
margin-block-end: 15px;
}

.navbar-text {
color: var(--white_a75);
font-weight: var(--fw-300);
line-height: 1.6;
margin-block-end: 15px;
}

.navbar .contact-link {
color: var(--radical-red);
font-size: var(--fs-6);
font-weight: var(--fw-400);
}

.navbar .contact-link:is(:hover, :focus-visible) { text-decoration: underline; }

.overlay {
position: fixed;
inset: 0;
background-color: var(--black);
z-index: 1;
transition: var(--transition-1);
opacity: 0;
pointer-events: none;
}

.overlay.active {
opacity: 0.75;
pointer-events: all;
}





/*-----------------------------------*\
#HERO
\*-----------------------------------*/

.hero {
padding-block-start: 120px;
text-align: center;
}

.hero-banner {
max-width: 150px;
margin-inline: auto;
margin-block-end: 20px;
margin-top: 40px;
margin-right: 70px;
}

.hero .wrapper {
position: relative;
text-align: left;
height: 1.2em;
}

.hero .wrapper .strong {
position: absolute;
top: 0;
left: 50%;
transform: translateX(-50%);
width: 300px;
font-weight: inherit;
display: flex;
}

.hero-text {
font-size: var(--fs-10);
font-weight: var(--fw-300);
text-transform: uppercase;
letter-spacing: 5px;
margin-bottom: 6rem;
}

.hero .wrapper .space { padding: 0.1em; }

.hero .wrapper :is(.in, .out) {
opacity: 0;
transform: scaleY(0);
}

.hero .strong.active .out {
opacity: 1;
transform: scaleY(1);
animation: textWave 0.2s ease reverse forwards;
}

.hero .wrapper .in { animation: textWave 0.2s ease forwards; }

@keyframes textWave {
0% {
  opacity: 0;
  transform: scaleY(0);
}
100% {
  opacity: 1;
  transform: scaleY(1);
}
}

.hero-title{
  margin-top: 100px;
}



/*-----------------------------------*\
#GALLERY
\*-----------------------------------*/

.gallery-list {
display: grid;
gap: 30px;
}

.gallery-item,
.gallery-card { position: relative; }

.gallery-card :is(.card-content, .btn-icon) {
position: absolute;
z-index: 1;
}

.gallery-card .card-content {
bottom: 0;
left: 0;
width: 100%;
padding: 30px 12px;
}

.gallery-card .card-tag {
color: var(--white_a70);
font-size: var(--fs-9);
font-weight: var(--fw-300);
}

.gallery-card .card-title {
font-weight: var(--fw-400);
max-width: max-content;
margin-block-end: 2px;
}

.gallery-card .card-title:is(:hover, :focus-visible) { text-decoration: underline; }

.gallery-card .btn-icon {
top: 0;
right: 0;
width: 50px;
height: 50px;
--border-radius: 0 0 0 var(--radius-25);
}

.gallery-card .btn-icon img {
width: 25px;
transform: rotate(-45deg);
}

.gallery-card .btn-icon:is(:hover, :focus-visible) {
border-bottom-left-radius: var(--radius-5);
}

.gallery-card { animation: changeCard 10s linear infinite; }

.gallery-item .gallery-card:last-child {
position: absolute;
top: 0;
left: 0;
width: 100%;
opacity: 0;
visibility: hidden;
animation-delay: 5s;
}

@keyframes changeCard {
0%,
55%,
100% {
  opacity: 0;
  visibility: hidden;
}

5%,
50% {
  opacity: 1;
  visibility: visible;
}
}

.gallery-item:is(:hover, :focus-within) .gallery-card { animation-play-state: paused; }

.gallery .scroll-down {
width: 60px;
height: 60px;
display: grid;
place-content: center;
margin-inline: auto;
margin-block-start: 55px;
border: 1px solid var(--white_a15);
border-radius: var(--radius-circle);
transition: var(--transition-2);
animation: scrollDown 2.5s linear infinite alternate;
}

.gallery .scroll-down img { width: 22px; }

.gallery .scroll-down:is(:hover, :focus-visible) {
background-color: var(--radical-red);
border-color: var(--radical-red);
}

@keyframes scrollDown {
0% { transform: translateY(-12px); }
100% { transform: translateY(12px); }
}





/*-----------------------------------*\
#CATEGORY
\*-----------------------------------*/

.category {
--section-padding: 40px;
border-block: 1px solid var(--white_a9);
}

.category-list {
display: flex;
justify-content: center;
align-items: center;
flex-wrap: wrap;
gap: 35px 10px;
}

.category-item { max-width: calc(50% - 5px); }

.category-card .card-title {
color: var(--white_a25);
margin-block-end: 10px;
text-align: center;
transition: var(--transition-2);
}

.category-card:is(:hover, :focus-visible) .card-title { color: var(--white); }





/*-----------------------------------*\
#ABOUT
\*-----------------------------------*/

.about .container {
display: grid;
gap: 45px;
}

.about .wrapper,
.about-banner { padding-inline-start: 45px; }

.about .section-title { margin-block-end: 35px; }

.about .section-text {
font-size: var(--fs-6);
color: var(--white_a70);
font-weight: var(--fw-300);
line-height: 1.7;
margin-block-end: 35px;
}

.about .wrapper::before {
top: 10px;
left: 0;
background-image: url("../images/about-quote.svg");
background-repeat: no-repeat;
background-size: contain;
width: 20px;
height: 20px;
}

.about .section-text .em {
color: var(--white);
font-weight: var(--fw-400);
text-decoration: underline;
}

.about-banner { position: relative; }

.about .shape-1 {
display: block;
position: absolute;
bottom: 10%;
left: 0;
z-index: 1;
width: 100px;
}





/*-----------------------------------*\
#SERVICES
\*-----------------------------------*/

.service { padding-inline: 15px; }

.service .section-subtitle {
padding-inline: 10px;
margin-block-end: 55px;
}

.service-card .img { display: none; }

.service-list > li:not(:last-child) { border-block-start: 1px solid var(--white_a9); }

.service-list > li:last-child { border-block: 1px solid var(--white_a9); }

.service-card { padding: 30px 10px; }

.service-card .card-subtitle {
color: var(--white_a50);
font-size: var(--fs-7);
font-weight: var(--fw-300);
line-height: 1.5;
margin-block: 10px 25px;
}

.service-card .btn-icon {
width: 55px;
height: 55px;
border: 1px solid var(--white);
--bg-color: transparent;
--hover-bg-color: var(--white);
--hover-text-color: var(--black);
}

.service-card .btn-icon svg { width: 25px; }





/*-----------------------------------*\
#PORTFOLIO
\*-----------------------------------*/

.portfolio { padding-block-end: 100px; }

.portfolio .section-title { margin-block-end: 60px; }

.portfolio-card {
position: relative;
margin-block-end: 50px;
}

.portfolio-card :is(.card-content, .btn-icon) {
position: absolute;
z-index: 1;
}

.portfolio-card .card-content {
bottom: 0;
left: 0;
width: 100%;
padding: 20px 15px;
}

.portfolio-card .card-tag {
color: var(--white_a70);
font-weight: var(--fw-300);
}

.portfolio-card .btn-icon {
top: 20px;
right: 20px;
width: 45px;
height: 45px;

--hover-bg-color: var(--radical-red);
--hover-text-color: var(--white);
}

.portfolio-card .btn-icon svg { width: 20px; }

.portfolio-card .card-title:is(:hover, :focus) { text-decoration: underline; }





/*-----------------------------------*\
#FOOTER
\*-----------------------------------*/

.footer { position: relative; }

.footer .abs-img { display: none; }

.footer-top {
padding-block: 100px 140px;
border-block-start: 1px solid var(--white_a9);
text-align: center;
z-index: 1;
}

.footer-top .section-title {
margin-block: 20px 90px;
line-height: normal;
}

.footer .btn-icon {
width: 60px;
height: 60px;
margin-inline: auto;
--hover-bg-color: var(--radical-red);
}

.footer .btn-icon img { width: 30px; }

.footer-bg {
position: absolute;
bottom: 0;
left: 0;
width: 100%;
height: 60%;
z-index: -1;
}

.footer-bg::before {
inset: 0;
background-image: var(--gradient-2);
}

.footer-bg .img-cover { object-position: top; }

.footer-bottom .logo {
margin-inline: auto;
max-width: max-content;
margin-block-end: 20px;
}

.social-list {
display: flex;
justify-content: center;
gap: 10px;
}

.social-link { font-weight: var(--fw-500); }

.social-link:is(:hover, :focus-visible) { text-decoration: underline; }

.copyright,
.social-list { padding-block-end: 15px; }

.copyright {
font-weight: var(--fw-300);
letter-spacing: 0.5px;
text-align: center;
}





/*-----------------------------------*\
#BACK TO TOP
\*-----------------------------------*/

.back-top-btn {
position: fixed;
bottom: 30px;
right: -70px;
width: 70px;
height: 70px;
border: 1px dashed currentColor;
color: var(--radical-red);
font-size: var(--fs-11);
border-radius: var(--radius-circle);
display: grid;
place-items: center;
visibility: hidden;
transition: var(--transition-2);
z-index: 3;
}

.back-top-btn.show {
transform: translateX(-100px);
visibility: visible;
}

.back-top-btn:hover { color: var(--white); }





/*-----------------------------------*\
#CUSTOM CURSOR
\*-----------------------------------*/

.cursor { display: none; }





/*-----------------------------------*\
#MEDIA QUERIES
\*-----------------------------------*/

/**
* responsive for large than 575px screen
*/

@media (min-width: 575px) {

/**
 * CUSTOM PROPERTY
 */

:root {

  /**
   * spacing
   */

  --section-padding: 80px;

}



/**
 * REUSED STYLE
 */

.container {
  max-width: 540px;
  width: 100%;
  margin-inline: auto;
}

:is(.header, .gallery, .category, .portfolio) .container { max-width: unset; }



/**
 * HEADER
 */

.navbar {
  max-width: 500px;
  right: -500px;
}

.navbar.active { transform: translateX(-500px); }



/**
 * GALLERY
 */

.gallery-list {
  grid-template-columns: 1fr 1fr;
  column-gap: 25px;
}

.gallery-card .btn-icon {
  transform-origin: top right;
  transform: scale(0);
}

.gallery-card:is(:hover, :focus-within) .btn-icon { transform: scale(1); }

.gallery-card :is(.card-title, .card-tag) {
  transform: translateY(10px);
  opacity: 0;
  transition: var(--transition-2);
}

.gallery-card .card-tag { transition-delay: 0.1s; }

.gallery-card:is(:hover, :focus-within) :is(.card-title, .card-tag) {
  transform: translateY(0);
  opacity: 1;
}

.gallery [data-reveal] {
  transform: translateY(0);
  opacity: 1;
}



/**
 * CATEGORY
 */

.category-item { max-width: 235px; }



/**
 * PORTFOLIO
 */

.portfolio-list {
  display: flex;
  column-gap: 30px;
}



/**
 * FOOTER
 */

.footer-bottom { padding-block-end: 40px; }

.footer-bottom .container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  align-items: center;
}

.footer-bottom .logo { margin: 0; }

.copyright,
.social-list { padding-block-end: 0; }

.social-list {
  order: 1;
  justify-content: flex-end;
}

}





/**
* responsive for large than 768px screen
*/

@media (min-width: 768px) {

/**
 * CUSTOM PROPERTY
 */

:root {

  /**
   * typography
   */

  --fs-3: 4.5rem;

}



/**
 * REUSED STYLE
 */

.container { max-width: 720px; }



/**
 * ABOUT
 */

.about-banner {
  max-width: 500px;
  margin-inline: auto;
}



/**
 * SERVICE
 */

.service-card {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.service-card .card-subtitle { margin-block-end: 15px; }

}





/**
* responsive for large than 992px screen
*/

@media (min-width: 992px) {

/**
 * CUSTOM PROPERTY
 */

:root {

  /**
   * typography
   */

  --fs-1: 8rem;

}



/**
 * REUSED STYLE
 */

.section { position: relative; }

.container { max-width: 960px; }

.shape {
  display: block;
  position: absolute;
}



/**
 * HEADER
 */

.header { padding-block: 30px; }

.navbar {
  padding: 40px;
  padding-block-end: 10px;
}

.navbar-link { --fs-7: 2.4rem; }

.navbar-title { --fs-8: 2.2rem; }

.navbar-text {
  font-size: 1.9rem;
  margin-block-end: 30px;
}



/**
 * HERO
 */

.hero { padding-block-start: 150px; }

.hero .container {
  position: relative;
  z-index: 1;
}

.hero-title { text-align: left; }

.hero .wrapper {
  --fs-2: 8rem;
  margin-block: -5px 10px;
}

.hero-banner {
  position: absolute;
  top: 50%;
  right: 0;
  transform: translateY(-50%);
  max-width: 200px;
  z-index: -1;
}

.hero .shape { display: none; }



/**
 * GALLERY
 */

.gallery { padding-block-end: 140px; }

.gallery-list { grid-template-columns: repeat(4, 1fr); }

.gallery-item:nth-child(even) { margin-block-start: 100px; }

.gallery .scroll-down {
  width: 85px;
  height: 85px;
  margin-block-start: 100px;
}

.gallery .scroll-down img { width: 26px; }

.gallery .shape {
  left: 5%;
  bottom: 15%;
}



/**
 * CATEGORY
 */

.category { --section-padding: 60px; }

.category-card { position: relative; }

.category-card .card-banner {
  position: absolute;
  bottom: 100%;
  left: 50%;
  transform: translate(-50%, -20px);
  width: 200px;
  opacity: 0;
  visibility: hidden;
  transition: var(--transition-2);
}

.category-card:is(:hover, :focus-visible) .card-banner {
  transform: translate(-50%, 0);
  visibility: visible;
  opacity: 1;
}

.category-card .card-title { --fs-4: 5.5rem; }

.category-item { min-width: max-content; }

.category-list {
  row-gap: 0;
  justify-content: flex-start;
}



/**
 * ABOUT
 */

.about .container {
  grid-template-columns: 0.9fr 1fr;
  align-items: flex-start;
  gap: 80px;
}

.about-content { order: 1; }

.about-banner .shape-2 {
  width: 100%;
  bottom: -20px;
  left: 0;
  animation: moving 8s linear infinite;
}

@keyframes moving {
  0%,
  100% { transform: translateY(0); }

  50% { transform: translateY(30px); }
}

.about .shape-3 {
  bottom: 0;
  right: 0;
}



/**
 * SERVICE
 */

.service-card { position: relative; }

.service-card .img {
  display: block;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 200px;
  height: 400px;
  opacity: 0;
  visibility: hidden;
  transition: var(--transition-1);
  z-index: -1;
}

.service-card:is(:hover, :focus-within) .img {
  opacity: 1;
  visibility: visible;
}



/**
 * PORTFOLIO
 */

.portfolio {
  padding-block-end: 150px;
  margin-block-end: 60px;
}

.portfolio .shape {
  bottom: 0;
  right: 0;
}



/**
 * FOOTER
 */

.footer .shape {
  top: 25%;
  left: 0;
}

.footer .abs-img {
  display: block;
  position: absolute;
  max-width: max-content;
  z-index: -1;
}

.footer .abs-img-1 {
  width: 9%;
  top: 12%;
  left: 10%;
}

.footer .abs-img-2 {
  width: 14%;
  top: 15%;
  right: 0;
}

.footer .abs-img-3 {
  width: 16%;
  left: 0;
  bottom: 10%;
}

.footer .abs-img-4 {
  width: 9%;
  right: 15%;
  bottom: 10%;
}



/**
 * CUSTOM CURSOR
 */

.cursor {
  display: block;
  position: fixed;
  top: 0;
  left: 0;
  width: 75px;
  height: 75px;
  background-color: var(--white);
  mix-blend-mode: exclusion;
  border-radius: var(--radius-circle);
  transform: translate(-50%, -50%) scale(0.35);
  transition: transform 0.35s;
  pointer-events: none;
  z-index: 6;
}

.cursor.hovered { transform: translate(-50%, -50%) scale(1.2); }

.cursor.disabled { transform: translate(-50%, -50%) scale(0); }

}





/**
* responsive for large than 1200px screen
*/

@media (min-width: 1200px) {

/**
 * CUSTOM PROPERTY
 */

:root {

  /**
   * typography
   */

  --fs-1: 10rem;
  --fs-2: 9rem;
  --fs-3: 6.8rem;
  --fs-4: 3.6rem;
  --fs-6: 2.8rem;

}



/**
 * REUSED STYLE
 */

.container { max-width: 1140px; }



/**
 * HEADER
 */

.header .container { padding-inline: 35px; }



/**
 * HERO
 */

.hero { padding-block: 170px 150px; }

.hero .container { max-width: 1250px; }

.hero .wrapper {
  --fs-2: 10rem;
  margin-block: -10px 15px;
}

.hero .wrapper .strong { left: 40%; }

.hero-text {
  --fs-10: 2rem;
  font-weight: var(--fw-400);
  letter-spacing: 8px;
}

.hero-banner { max-width: 290px; }

.hero .shape {
  display: block;
  top: 60%;
  left: 0;
}



/**
 * GALLERY
 */

.gallery-list { gap: 50px; }

.gallery-card .card-title { font-weight: var(--fw-300); }



/**
 * CATEGORY
 */

.category-list { column-gap: 15px; }

.category-card .card-title { --fs-4: 7rem; }



/**
 * ABOUT
 */

.about .container { gap: 120px; }

.about .shape-1 { width: max-content; }

.about .section-title { margin-block-end: 70px; }

.about .wrapper { padding-inline-start: 80px; }

.about .wrapper::before {
  width: 35px;
  height: 30px;
}

.about .section-text {
  --fs-6: 3.2rem;
  margin-block-end: 50px;
}



/**
 * SERVICE
 */

.service-card { padding-block: 50px; }

.service-card .card-subtitle { --fs-7: 2.4rem; }

.service-card .img { width: max-content; }

.service-card .btn-icon {
  width: 95px;
  height: 95px;
}

.service-card .btn-icon svg { width: 40px; }



/**
 * PORTFOLIO
 */

.portfolio-list { column-gap: 90px; }

.portfolio-card { margin-block-end: 100px; }

.portfolio-card .card-content { padding-inline: 50px; }

.portfolio-card .btn-icon {
  width: 60px;
  height: 60px;
  top: auto;
  bottom: 45px;
  right: 50px;
  opacity: 0;
  transition: var(--transition-2);
}

.portfolio-card .btn-icon svg { width: 25px; }

.portfolio-card:is(:hover, :focus-within) .btn-icon { opacity: 1; }



/**
 * FOOTER
 */

.footer-top { padding-block: 300px; }

.footer-top .section-title {
  --fs-2: 8rem;
  margin-block-start: 50px;
}

.footer .btn-icon {
  width: 90px;
  height: 90px;
}

.footer .btn-icon img { width: 45px; }

}





/**
* responsive for large than 1400px screen
*/

@media (min-width: 1400px) {

/**
 * CUSTOM PROPERTY
 */

:root {

  /**
   * typography
   */

  --fs-1: 13rem;
  --fs-2: 10rem;
  --fs-3: 8rem;

}



/**
 * REUSED STYLE
 */

.container { max-width: 1320px; }

:is(.header, .gallery, .category, .portfolio) .container { max-width: 1580px; }



/**
 * HEADER
 */

.header .container { padding-inline: 60px; }



/**
 * HERO
 */

.hero .container { max-width: 1500px; }

.hero-content { margin-inline-end: 400px; }

.hero .wrapper { --fs-2: 13rem; }

.hero-text { --fs-10: 2.4rem; }

.hero-banner { max-width: max-content; }



/**
 * CATEGORY
 */

.category .container { padding-inline: 40px; }

.category-card .card-title { --fs-4: 8rem; }



/**
 * ABOUT
 */

.about { padding-block: 180px 120px; }



/**
 * SERVICE
 */

.service { padding-inline: 70px; }

.service-card { padding-block: 65px; }



/**
 * PORTFOLIO
 */

.portfolio .container { padding-inline: 45px; }



/**
 * FOOTER
 */

.footer-top .container { max-width: 1200px; }

}



.back-video{
        position: absolute;
        right: 0;
        bottom: 0;
        z-index: -1;
       }
       @media (min-aspect-ratio: 16/9){
        .back-video{
            width: 100%;
            height: auto;
        }
       }
       @media (max-aspect-ratio: 16/9){
        .back-video{
            width: auto;
            height: 100%;
        }
      }

.logo{
  margin-bottom: 1rem;
}







body{
	line-height: 1.5;
	font-family: 'Poppins', sans-serif;
}
*{
	margin:0;
	padding:0;
	box-sizing: border-box;
}
.containe{
	max-width: 1170px;
	margin-left: 200px;
  margin-bottom: -3.3rem;
}
.row{
	display: flex;
	flex-wrap: wrap;
}
ul{
	list-style: none;
}
.foote{
	background-color: transparent;
    padding: 70px 0;
    margin-top: -20px;
}
.footer-col{
   width: 25%;
   padding: 0 15px;
}
.footer-col h4{
	font-size: 18px;
	color: white;
	text-transform: capitalize;
	margin-bottom: 35px;
	font-weight: 500;
	position: relative;
}
.footer-col h4::before{
	content: '';
	position: absolute;
	left:0;
	bottom: -10px;
	background-color: #e91e63;
	height: 2px;
	box-sizing: border-box;
	width: 50px;
}
.footer-col ul li:not(:last-child){
	margin-bottom: 10px;
}
.footer-col ul li a{
	font-size: 16px;
	text-transform: capitalize;
	color: #ffffff;
	text-decoration: none;
	font-weight: 300;
	color: #bbbbbb;
	display: block;
	transition: all 0.3s ease;
}
.footer-col ul li a:hover{
	color: #ffffff;
	padding-left: 8px;
}
.footer-col .social-links a{
	display: inline-block;
	height: 40px;
	width: 40px;
	background-color: rgba(255,255,255,0.2);
	margin:0 10px 10px 0;
	text-align: center;
	line-height: 40px;
	border-radius: 50%;
	color: #ffffff;
	transition: all 0.5s ease;
}
.footer-col .social-links a:hover{
	color: #24262b;
	background-color: #ffffff;
}

/*responsive*/
@media(max-width: 767px){
  .footer-col{
    width: 50%;
    margin-bottom: 30px;
}
}
@media(max-width: 574px){
  .footer-col{
    width: 100%;
}
}


.footer{
  margin-top: 46px;
}




.tooltip-container {
  position: relative;
  cursor: pointer;
  transition: all 0.2s;
  font-size: 17px;
  border-radius: 10px;
}

.tooltip {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  padding: 10px;
  opacity: 0;
  pointer-events: none;
  transition: all 0.3s;
  
}

.profile {
  border-radius: 10px 15px;
  padding: 10px;
}

.tooltip-container:hover .tooltip {
  top: -150px;
  opacity: 1;
  visibility: visible;
  pointer-events: auto;
}

.icon {
  text-decoration: none;
  color: #fff;
  display: block;
  position: relative;
}
.layer {
  width: 55px;
  height: 55px;
  transition: transform 0.3s;
}
.icon:hover .layer {
  transform: rotate(-35deg) skew(20deg);
}
.layer span {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  border: 1px solid #fff;
  border-radius: 15px;
  transition: all 0.3s;
}

.layer span,
.text {
  color: #e6683c;
  border-color: #e6683c;
}

.icon:hover.layer span {
  box-shadow: -1px 1px 3px #e6683c;
}
.icon .text {
  position: absolute;
  left: 50%;
  bottom: -5px;
  opacity: 0;
  font-weight: 500;
  transform: translateX(-50%);
  transition: bottom 0.3s ease, opacity 0.3s ease;
}
.icon:hover .text {
  bottom: -35px;
  opacity: 1;
}

.icon:hover .layer span:nth-child(1) {
  opacity: 0.2;
}
.icon:hover .layer span:nth-child(2) {
  opacity: 0.4;
  transform: translate(5px, -5px);
}
.icon:hover .layer span:nth-child(3) {
  opacity: 0.6;
  transform: translate(10px, -10px);
}
.icon:hover .layer span:nth-child(4) {
  opacity: 0.8;
  transform: translate(15px, -15px);
}
.icon:hover .layer span:nth-child(5) {
  opacity: 1;
  transform: translate(20px, -20px);
}

.instagramSVG {
  font-size: 25px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: -webkit-linear-gradient(
    45deg,
    #f09433 0%,
    #e6683c 25%,
    #dc2743 50%,
    #cc2366 75%,
    #bc1888 100%
  );
  background: linear-gradient(
    45deg,
    #f09433 0%,
    #e6683c 25%,
    #dc2743 50%,
    #cc2366 75%,
    #bc1888 100%
  );
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#f09433', endColorstr='#bc1888',GradientType=1 );
}
.user {
  display: flex;
  gap: 10px;
}
.img {
  width: 50px;
  height: 50px;
  font-size: 25px;
  font-weight: 700;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.name {
  font-size: 17px;
  font-weight: 700;
  color: #e6683c;
}
.details {
  display: flex;
  flex-direction: column;
  gap: 0;
}
.about {
  padding-top: 5px;
}






.tool-container {
  position: relative;
  cursor: pointer;
  transition: all 0.2s;
  font-size: 17px;
  border-radius: 10px;
  margin-left: 70px;
  margin-top: -56px;
}

.tool {
  position: absolute;
  top: 0;
  transform: translateX(-50%);
  padding: 10px;
  opacity: 0;
  pointer-events: none;
  transition: all 0.3s;
 
}



.tool-container:hover .tool {
  top: -150px;
  opacity: 1;
  visibility: visible;
  pointer-events: auto;
}

.ico {
  text-decoration: none;
  display: block;
  position: relative;
}
.ico .laye {
  width: 55px;
  height: 55px;
  border-radius: 50%;
  transition: transform 0.3s, border 0.3s ease, box-shadow 0.3s ease;
}

.ico:hover .laye {
  transform: rotate(-35deg) skew(20deg);
}

.laye span {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  border-radius: 50%;
  transition: all 0.3s;
}

.laye span,


.ico:hover .laye span {
  box-shadow: -1px 1px 3px #1877f2;
}

.ico .tex {
  position: absolute;
  left: 50%;
  bottom: -5px;
  opacity: 0;
  font-weight: 500;
  transform: translateX(-50%);
  transition: bottom 0.3s ease, opacity 0.3s ease;
}

.ico:hover .tex {
  bottom: -35px;
  opacity: 1;
}

.ico:hover .laye span:nth-child(1) {
  opacity: 0.2;
}

.ico:hover .laye span:nth-child(2) {
  opacity: 0.4;
  transform: translate(5px, -5px);
}

.ico:hover .laye span:nth-child(3) {
  opacity: 0.6;
  transform: translate(10px, -10px);
}

.ico:hover .laye span:nth-child(4) {
  opacity: 0.8;
  transform: translate(15px, -15px);
}

.ico:hover .laye span:nth-child(5) {
  opacity: 1;
  transform: translate(20px, -20px);
}

.facebookSVG {
  font-size: 25px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #1877f2;
  border-radius: 50%;
  background: linear-gradient(
    45deg,
    #1877f2 0%,
    #3b5998 25%,
    #1877f2 50%,
    #3b5998 75%,
    #1877f2 100%
  );
}

.us {
  display: flex;
  gap: 10px;
}

.im {
  width: 50px;
  height: 50px;
  font-size: 25px;
  font-weight: 700;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.nam {
  font-size: 17px;
  font-weight: 700;
  color: #1877f2;
}

.deta {
  display: flex;
  flex-direction: column;
  gap: 0;
  color: #fff;
}

.abou {
  color: #ccc;
  padding-top: 5px;
}


.img{
  width: 10%;
}




*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}


.counter-up{
  min-height: 50vh;
  background-size: cover;
  background-attachment: fixed;
  padding:  1px 50px;
  position: relative;
  display: flex;
  align-items: center;
  margin-top: -90px;
  margin-bottom: -90px;
}
.counter-up::before{
  position: absolute;
  content: "";
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background: transparent;
}
.counter-up .content{
  z-index: 1;
  position: relative;
  display: flex;
  width: 100%;
  height: 100%;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
}
.counter-up .content .box{
  width: calc(25% - 30px);
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  flex-direction: column;
  padding: 30px;
}
.content .box .icon{
  font-size: 48px;
  color: white;
  transition: all .2s ease;
}

.content .box .icon:hover{
  transform: scale(1.4);
}


.content .box .counter{
  font-size: 50px;
  font-weight: 500;
  color: white;
  font-family: sans-serif;
  transition: all .2s ease;

}
.content .box .counter:hover{
  transform: scale(1.4);
}

.content .box .text{
  font-weight: 300;
  font-size: 20px;
  color: white;
  transition: all .2s ease;
}
.content .box .text:hover{
  transform: scale(1.1);
}


@media screen and (max-width: 1036px) {
  .counter-up{
    padding: 50px 50px 0 50px;
  }
  .counter-up .content .box{
    width: calc(50% - 30px);
    margin-bottom: 10px;
  }
}
@media screen and (max-width: 580px) {
  .counter-up .content .box{
    width: 100%;
  }
}
@media screen and (max-width: 500px) {
  .wrapper{
    padding: 5px;
  }
  .counter-up{
    padding: 10px 10px 0 10px;
  }
}

.img .sd{
  margin-right: -261px;
  margin-bottom: 40px;
}










  </style>
  <meta name="title" content="Drive Dream">
  <meta name="description" content="This is a Car website made my aman.">

  <!-- 
    - favicon
  -->
  <link rel="shortcut icon" href="./favicon.svg" type="image/svg+xml">

  <!-- 
    - custom css link
  -->
  <link rel="stylesheet" href="./assets/css/style.css">

  <!-- 
    - custom font link
  -->
  <link rel="stylesheet" href="./assets/font/font.css">

  <!-- 
    - preload images
  -->
  <link rel="preload" as="image" href="./assets/images/loading.svg">
  <link rel="preload" as="image" href="./assets/images/loading-circle.svg">

</head>

<body class="active" id="top">

  <!-- 
    -#PRELOADING
  -->

  <div class="loading" data-loading>
    <img src="img1/logo7.png" width="500" height="500" alt="loading" class="img">
    <img src="img1/loading-circle.svg" width="70" height="70" alt="" class="circle">
  </div>





  <!-- 
    - #HEADER
  -->

  <header class="header" data-header>
    <div class="container">

      <a href="#" class="logo">
        <img src="img1/logo7.png" width="240" height="140" alt="Richard home">
      </a>

      <button class="nav-open-btn" aria-label="open menu" data-nav-toggler>
        <img src="img1/menu.svg" width="30" height="30" alt="menu icon">
      </button>

      <nav class="navbar" data-navbar>

        <div class="navbar-top">
          <a href="#" class="logo">
            <img src="img1/logo7.png " width="30" height="40" alt="Richard home" class="img">
          </a>

          <button class="nav-close-btn" aria-label="close menu" data-nav-toggler>
            <span class="span one"></span>
            <span class="span two"></span>
          </button>
        </div>

        <ul class="navbar-list">

          <li class="navbar-item">
            <a href="#home" class="navbar-link" data-nav-link>Home</a>
          </li>

          <li class="navbar-item">
            <a href="#gallery" class="navbar-link" data-nav-link>Gallery</a>
          </li>

          <li class="navbar-item">
            <a href="#about" class="navbar-link" data-nav-link>About</a>
          </li>

          <li class="navbar-item">
            <a href="#services" class="navbar-link" data-nav-link>Services</a>
          </li>

          <li class="navbar-item">
            <a href="#portfolio" class="navbar-link" data-nav-link>Portfolio</a>
          </li>

          <li class="navbar-item">
            <a href="#contact" class="navbar-link" data-nav-link>Contact us</a>
          </li>

        </ul>

        <button class="login-btn">
          <img src="img1/user.svg" width="21" height="21" alt="user icon">

          <span class="span">Login</span>
        </button>

        <p class="navbar-title">My Address</p>

        <address class="navbar-text">
          Bangalore Nagarghavi
        </address>

        <p class="navbar-text">
          Urgent issue? call us at
          <a href="tel:8085613846" class="contact-link">6366678694</a>
        </p>

      </nav>

      <div class="overlay" data-nav-toggler data-overlay></div>

    </div>
  </header>





  <main>
    <article>

      <!-- 
        - #HERO
      -->

      <section class="section hero" id="home" aria-label="home">
        <div class="container">


          <div class="hero-content">

            <h1 class="h1 hero-title">Drive Dream</h1>

            <div class="wrapper h2">
              <strong class="strong" data-letter-effect>Sport Car</strong>
              <strong class="strong" data-letter-effect>Luxury Car</strong>
              <strong class="strong" data-letter-effect>Car Service</strong>
            </div>

            <p class="hero-text">2+ months Of Experience</p>

          </div>

        </div>


      </section>





      <!-- 
        - #GALLERY
      -->

      <section class="section gallery" id="gallery">
        <div class="container">

          <ul class="gallery-list">

            <li class="gallery-item" data-reveal>

              <div class="gallery-card">

                <figure class="card-banner img-holder has-before" style="--width: 450; --height: 625;">
                  <img src="img1/carima1.webp" width="450" height="625" loading="lazy" alt="The Drunken"
                    class="img-cover">
                </figure>

                <div class="card-content">
                  <h3 class="h6">
                    <a href="#" class="card-title">Super Cars</a>
                  </h3>

                  <span class="card-tag">Drive Dream Collection</span>
                </div>

                <a href="#" class="btn-icon">
                  <img src="img1/arrow-forward.svg" width="43" height="20" loading="lazy"
                    alt="arrow-forward icon">
                </a>

              </div>

              <div class="gallery-card">

                <figure class="card-banner img-holder has-before" style="--width: 450; --height: 625;">
                  <img src="img1/carima11.jpg" width="450" height="625" loading="lazy"
                    alt="Lettuce Entertain" class="img-cover">
                </figure>

                <div class="card-content">
                  <h3 class="h6">
                    <a href="#" class="card-title">Expence Cars</a>
                  </h3>

                  <span class="card-tag">Drive Dream Collection</span>
                </div>

                <a href="#" class="btn-icon">
                  <img src="img1/arrow-forward.svg" width="43" height="20" loading="lazy"
                    alt="arrow-forward icon">
                </a>

              </div>

            </li>

            <li class="gallery-item" data-reveal>

              <div class="gallery-card">
A
                <figure class="card-banner img-holder has-before" style="--width: 450; --height: 625;">
                  <img src="img1/carima12.jpg" width="450" height="625" loading="lazy" alt="Leaping Lizard"
                    class="img-cover">
                </figure>

                <div class="card-content">
                  <h3 class="h6">
                    <a href="#" class="card-title">super Cars</a>
                  </h3>

                  <span class="card-tag">Drive Dream Collection</span>
                </div>

                <a href="#" class="btn-icon">
                  <img src="img1/arrow-forward.svg" width="43" height="20" loading="lazy"
                    alt="arrow-forward icon">
                </a>

              </div>

              <div class="gallery-card">

                <figure class="card-banner img-holder has-before" style="--width: 450; --height: 625;">
                  <img src="img1/carima13.jpg" width="450" height="625" loading="lazy" alt="Juan More Taco"
                    class="img-cover">
                </figure>

                <div class="card-content">
                  <h3 class="h6">
                    <a href="#" class="card-title">Luxury Cars</a>
                  </h3>

                  <span class="card-tag">Drive Dream Collection</span>
                </div>

                <a href="#" class="btn-icon">
                  <img src="img1/arrow-forward.svg" width="43" height="20" loading="lazy"
                    alt="arrow-forward icon">
                </a>

              </div>

            </li>

            <li class="gallery-item" data-reveal>

              <div class="gallery-card">

                <figure class="card-banner img-holder has-before" style="--width: 450; --height: 625;">
                  <img src="img1/b6.jpeg" width="450" height="625" loading="lazy" alt="Goldilox Bagels"
                    class="img-cover">
                </figure>

                <div class="card-content">
                  <h3 class="h6">
                    <a href="#" class="card-title">Mussale Cars</a>
                  </h3>

                  <span class="card-tag">Drive Dream Collection</span>
                </div>

                <a href="#" class="btn-icon">
                  <img src="img1/arrow-forward.svg" width="43" height="20" loading="lazy"
                    alt="arrow-forward icon">
                </a>

              </div>

              <div class="gallery-card">

                <figure class="card-banner img-holder has-before" style="--width: 450; --height: 625;">
                  <img src="img1/carima3.jpg" width="450" height="625" loading="lazy" alt="Cookie Monstah"
                    class="img-cover">
                </figure>

                <div class="card-content">
                  <h3 class="h6">
                    <a href="#" class="card-title">Limited Edition</a>
                  </h3>

                  <span class="card-tag">Drive Dream Collection</span>
                </div>

                <a href="#" class="btn-icon">
                  <img src="img1/arrow-forward.svg" width="43" height="20" loading="lazy"
                    alt="arrow-forward icon">
                </a>

              </div>

            </li>

            <li class="gallery-item" data-reveal>

              <div class="gallery-card">

                <figure class="card-banner img-holder has-before" style="--width: 450; --height: 625;">
                  <img src="img1/cat3.png" width="450" height="625" loading="lazy"
                    alt="Divine Pastabilities" class="img-cover">
                </figure>

                <div class="card-content">
                  <h3 class="h6">
                    <a href="#" class="card-title">Divine Pastabilities</a>
                  </h3>

                  <span class="card-tag">Drive Dream Collection</span>
                </div>

                <a href="#" class="btn-icon">
                  <img src="img1/arrow-forward.svg" width="43" height="20" loading="lazy"
                    alt="arrow-forward icon">
                </a>

              </div>

              <div class="gallery-card">

                <figure class="card-banner img-holder has-before" style="--width: 450; --height: 625;">
                  <img src="img1/lux2.jpg" width="450" height="625" loading="lazy"
                    alt="The Lockhart Bar" class="img-cover">
                </figure>

                <div class="card-content">
                  <h3 class="h6">
                    <a href="#" class="card-title">Hyper Cars</a>
                  </h3>

                  <span class="card-tag">Drive Dream Collection</span>
                </div>

                <a href="#" class="btn-icon">
                  <img src="img1/arrow-forward.svg" width="43" height="20" loading="lazy"
                    alt="arrow-forward icon">
                </a>

              </div>

            </li>

          </ul>

          <a href="#service" class="scroll-down">
            <img src="img1/scroll-down.svg" width="40" height="66" loading="lazy" alt="mouse scroll">
          </a>

          <img src="img1/gallery-shape.svg" width="220" height="78" loading="lazy" alt="" class="shape">

        </div>
      </section>





      <!-- 
        - #CATEGORY
      -->

      <section class="section category" aria-label="photography category">
        <div class="container">

          <ul class="category-list">

            <li class="category-item" data-reveal>
              <a href="#" class="category-card">

                <h3 class="h4 card-title">Driving your</h3>

                <figure class="card-banner img-holder" style="--width: 600; --height: 690;">
                  <img src="img1/c1.jpg" width="600" height="690" loading="lazy" alt="Landscape"
                    class="img-cover">
                </figure>

              </a>
            </li>

            <li class="category-item" data-reveal>
              <a href="#" class="category-card">

                <h3 class="h4 card-title">dream car</h3>

                <figure class="card-banner img-holder" style="--width: 600; --height: 690;">
                  <img src="img1/c2.jpg" width="600" height="690" loading="lazy" alt="Model"
                    class="img-cover">
                </figure>

              </a>
            </li>

            <li class="category-item" data-reveal>
              <a href="#" class="category-card">

                <h3 class="h4 card-title">can profoundly</h3>

                <figure class="card-banner img-holder" style="--width: 600; --height: 690;">
                  <img src="img1/c3.jpg" width="600" height="690" loading="lazy" alt="Street"
                    class="img-cover">
                </figure>

              </a>
            </li>

            <li class="category-item" data-reveal>
              <a href="#" class="category-card">

                <h3 class="h4 card-title">impact your</h3>

                <figure class="card-banner img-holder" style="--width: 600; --height: 690;">
                  <img src="img1/carima1.webp" width="600" height="690" loading="lazy" alt="Product"
                    class="img-cover">
                </figure>

              </a>
            </li>

            <li class="category-item" data-reveal>
              <a href="#" class="category-card">

                <h3 class="h4 card-title">experience </h3>

                <figure class="card-banner img-holder" style="--width: 600; --height: 690;">
                  <img src="img1/c5.jpg" width="600" height="690" loading="lazy" alt="Fashion"
                    class="img-cover">
                </figure>

              </a>
            </li>

            <li class="category-item" data-reveal>
              <a href="#" class="category-card">

                <h3 class="h4 card-title">with a company's</h3>

                <figure class="card-banner img-holder" style="--width: 600; --height: 690;">
                  <img src="img1/c6.jpg" width="600" height="690" loading="lazy" alt="Film"
                    class="img-cover">
                </figure>

              </a>
            </li>

            <li class="category-item" data-reveal>
              <a href="#" class="category-card">

                <h3 class="h4 card-title">service</h3>

                <figure class="card-banner img-holder" style="--width: 600; --height: 690;">
                  <img src="img1/c7.jpg" width="600" height="690" loading="lazy" alt="Architecture"
                    class="img-cover">
                </figure>

              </a>
            </li>

            <li class="category-item" data-reveal>
              <a href="#" class="category-card">

                <h3 class="h4 card-title">at Drive Dream</h3>

                <figure class="card-banner img-holder" style="--width: 600; --height: 690;">
                  <img src="img1/c8.jpg" width="600" height="690" loading="lazy" alt="Event"
                    class="img-cover">
                </figure>

              </a>
            </li>

            <li class="category-item" data-reveal>
              <a href="#" class="category-card">

                <h3 class="h4 card-title">Specialized Expertise</h3>

                <figure class="card-banner img-holder" style="--width: 600; --height: 690;">
                  <img src="img1/c9.jpg" width="600" height="690" loading="lazy" alt="Wedding"
                    class="img-cover">
                </figure>

              </a>
            </li>

            <li class="category-item" data-reveal>
              <a href="#" class="category-card">

                <h3 class="h4 card-title">Warranty and Support:</h3>

                <figure class="card-banner img-holder" style="--width: 600; --height: 690;">
                  <img src="img1/c10.jpg" width="600" height="690" loading="lazy" alt="People"
                    class="img-cover">
                </figure>

              </a>
            </li>

            <li class="category-item" data-reveal>
              <a href="#" class="category-card">

                <h3 class="h4 card-title">Overall Satisfaction</h3>

                <figure class="card-banner img-holder" style="--width: 600; --height: 690;">
                  <img src="img1/c11.jpg" width="600" height="690" loading="lazy" alt="Event"
                    class="img-cover">
                </figure>

              </a>
            </li>


          </ul>

        </div>
      </section>






<!--
    - #video      
-->
<video class="back-video" autoplay muted loop play-inline>
  <source src="img1/bmw6 - COMPRESS.mp4">
</video>








      <!-- 
        - #ABOUT
      -->

      <section class="section about" id="about" aria-label="about me">
        <div class="container">

          <div class="about-content">

            <h2 class="h2 section-title" data-reveal="right">
              Hi. I’m <br>
              Aman
            </h2>

            <div class="wrapper has-before" data-reveal="right">

              <p class="section-text">
                A passionate
                <em class="em">engreeniar</em>
                who are  working in this field for
                <em class="em">last 2 years.</em>
                I’m ready to give you my best.
              </p>

              

            </div>

          </div>

          <figure class="about-banner" data-reveal="left">

            <div class="img-holder has-before" style="--width: 512; --height: 684;">
              <img src="img1/lulumall.jpg" width="512" height="684" loading="lazy" alt="Riachard Ryan"
                class="img-cover">
            </div>



            <img src="img1/about-shape-2.svg" width="659" height="653" loading="lazy" alt=""
              class="shape shape-2">

          </figure>

          <img src="img1/about-shape-3.svg" width="239" height="232" loading="lazy" alt=""
            class="shape shape-3">

        </div>
      </section>





      <!-- 
        - #SERVICE
      -->

      <section class="section service" id="service" aria-labelledby="service-lable">

        <p class="section-subtitle container" id="service-lable">My Services</p>

        <ul class="service-list">

          <li data-reveal>
            <div class="service-card container">

              <img src="img1/super3.jpg" width="340" height="380" loading="lazy" alt="Wedding Photography"
                class="img">

              <div>
                <h3 class="h3 card-title">Super Cars</h3>

                <p class="card-subtitle">
                  Aut temporibus qui vero.
                </p>
              </div>

              <a href="#" class="btn-icon" aria-label="See more">
                <svg xmlns="http://www.w3.org/2000/svg" width="43" height="20" viewBox="0 0 43 20" fill="none">
                  <path d="M0 10H41" stroke="white" stroke-width="2" />
                  <path d="M33 1L41.9 10.2727L33 19" stroke="white" stroke-width="2" />
                </svg>
              </a>

            </div>
          </li>

          <li data-reveal>
            <div class="service-card container">

              <img src="img1/lux2.jpg" width="340" height="380" loading="lazy" alt="Event Organiser"
                class="img">

              <div>
                <h3 class="h3 card-title">Luxury Cars</h3>

                <p class="card-subtitle">
                  Nobis, magni modi ipsa culpa.
                </p>
              </div>

              <a href="#" class="btn-icon" aria-label="See more">
                <svg xmlns="http://www.w3.org/2000/svg" width="43" height="20" viewBox="0 0 43 20" fill="none">
                  <path d="M0 10H41" stroke="white" stroke-width="2" />
                  <path d="M33 1L41.9 10.2727L33 19" stroke="white" stroke-width="2" />
                </svg>
              </a>

            </div>
          </li>

          <li data-reveal>
            <div class="service-card container">

              <img src="img1/produc1.jpg" width="340" height="380" loading="lazy" alt="Product Marketing"
                class="img">

              <div>
                <h3 class="h3 card-title">Product Marketing</h3>

                <p class="card-subtitle">
                  Tenetur porro repellendus!
                </p>
              </div>

              <a href="#" class="btn-icon" aria-label="See more">
                <svg xmlns="http://www.w3.org/2000/svg" width="43" height="20" viewBox="0 0 43 20" fill="none">
                  <path d="M0 10H41" stroke="white" stroke-width="2" />
                  <path d="M33 1L41.9 10.2727L33 19" stroke="white" stroke-width="2" />
                </svg>
              </a>

            </div>
          </li>

          <li data-reveal>
            <div class="service-card container">

              <img src="img1/limit3.jpg" width="340" height="380" loading="lazy" alt="Videography"
                class="img">

              <div>
                <h3 class="h3 card-title">Limited Edition Cars</h3>

                <p class="card-subtitle">
                  Amet consectetur adipisicing elit
                </p>
              </div>

              <a href="#" class="btn-icon" aria-label="See more">
                <svg xmlns="http://www.w3.org/2000/svg" width="43" height="20" viewBox="0 0 43 20" fill="none">
                  <path d="M0 10H41" stroke="white" stroke-width="2" />
                  <path d="M33 1L41.9 10.2727L33 19" stroke="white" stroke-width="2" />
                </svg>
              </a>

            </div>
          </li>

        </ul>

      </section>





      <!-- 
        - #PORTFOLIO
      -->




      <link rel="stylesheet" href="style.css">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css"/>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/waypoints/4.0.1/jquery.waypoints.min.js"></script>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/Counter-Up/1.0.0/jquery.counterup.min.js"></script>
  
   
    <div class="counter-up">
      <div class="content">
        <div class="box">
          <div class="icon"><i class="fas fa-history"></i></div>
          <div class="counter">24</div>
          <div class="text">Working Hours</div>
        </div>
        <div class="box">
          <div class="icon"><i class="fas fa-gift"></i></div>
          <div class="counter">508</div>
          <div class="text">Completed Projects</div>
        </div>
        <div class="box">
          <div class="icon"><i class="fas fa-users"></i></div>
          <div class="counter">436</div>
          <div class="text">Happy Clients</div>
        </div>
        <div class="box">
          <div class="icon"><i class="fas fa-award"></i></div>
          <div class="counter">120</div>
          <div class="text">Awards Received</div>
        </div>
      </div>
    </div>
  





      <section class="section portfolio" id="portfolio" aria-labelledby="portfolio-label">
        <div class="container">

          <div class="portfolio-list">

            <div class="wrapper">

              <h2 class="h2 section-title" id="portfolio-label" data-reveal>My Recent Work.</h2>

              <div class="portfolio-card" data-reveal>

                <figure class="card-banner img-holder has-before" style="--width: 700; --height: 605;">
                  <img src="img1/lux.jpg" width="700" height="605" loading="lazy" alt="Shoe Promo"
                    class="img-cover">
                </figure>

                <div class="card-content">
                  <h3 class="h4">
                    <a href="#" class="card-title">Cars</a>
                  </h3>

                  <p class="card-tag">Product</p>
                </div>

                <a href="#" class="btn-icon" aria-label="See more">
                  <svg xmlns="http://www.w3.org/2000/svg" width="43" height="20" viewBox="0 0 43 20" fill="none">
                    <path d="M0 10H41" stroke="black" stroke-width="2" />
                    <path d="M33 1L41.9 10.2727L33 19" stroke="black" stroke-width="2" />
                  </svg>
                </a>

              </div>

              <div class="portfolio-card" data-reveal>

                <figure class="card-banner img-holder has-before" style="--width: 700; --height: 1091;">
                  <img src="img1/limit.jpg" width="700" height="1091" loading="lazy" alt="Wedding Shot"
                    class="img-cover">
                </figure>

                <div class="card-content">
                  <h3 class="h4">
                    <a href="#" class="card-title">Latash</a>
                  </h3>

                  <p class="card-tag">Cars</p>
                </div>

                <a href="#" class="btn-icon" aria-label="See more">
                  <svg xmlns="http://www.w3.org/2000/svg" width="43" height="20" viewBox="0 0 43 20" fill="none">
                    <path d="M0 10H41" stroke="black" stroke-width="2" />
                    <path d="M33 1L41.9 10.2727L33 19" stroke="black" stroke-width="2" />
                  </svg>
                </a>

              </div>

            </div>

            <div class="wrapper">

              <div class="portfolio-card" data-reveal>

                <figure class="card-banner img-holder has-before" style="--width: 700; --height: 1000;">
                  <img src="img1/super.jpg" width="700" height="1000" loading="lazy" alt="Fashion Show"
                    class="img-cover">
                </figure>

                <div class="card-content">
                  <h3 class="h4">
                    <a href="#" class="card-title">Hyper</a>
                  </h3>

                  <p class="card-tag">Cars</p>
                </div>

                <a href="#" class="btn-icon" aria-label="See more">
                  <svg xmlns="http://www.w3.org/2000/svg" width="43" height="20" viewBox="0 0 43 20" fill="none">
                    <path d="M0 10H41" stroke="black" stroke-width="2" />
                    <path d="M33 1L41.9 10.2727L33 19" stroke="black" stroke-width="2" />
                  </svg>
                </a>

              </div>

              <div class="portfolio-card" data-reveal>

                <figure class="card-banner img-holder has-before" style="--width: 700; --height: 850;">
                  <img src="img1/produc.jpg" width="700" height="850" loading="lazy" alt="Jumbo Barger"
                    class="img-cover">
                </figure>

                <div class="card-content">
                  <h3 class="h4">
                    <a href="#" class="card-title">Carban Fiber</a>
                  </h3>

                  <p class="card-tag">Cars</p>
                </div>

                <a href="#" class="btn-icon" aria-label="See more">
                  <svg xmlns="http://www.w3.org/2000/svg" width="43" height="20" viewBox="0 0 43 20" fill="none">
                    <path d="M0 10H41" stroke="black" stroke-width="2" />
                    <path d="M33 1L41.9 10.2727L33 19" stroke="black" stroke-width="2" />
                  </svg>
                </a>

              </div>

            </div>

          </div>

          <img src="img1/about-shape-3.svg" width="286" height="232" loading="lazy" alt="" class="shape">

        </div>
      </section>

    </article>
  </main>





  <!-- 
    - #FOOTER
  -->

  <footer class="footer">

    <div class="footer-top section" id="contact">
      <div class="container">

        <p class="section-subtitle" data-reveal>Contact Us</p>

        <h2 class="h2 section-title" data-reveal>
          Work inquiry, Job oportunities? Send Message.
        </h2>

        <a href="#" class="btn-icon" data-reveal>
          <img src="img1/arrow-forward.svg" width="43" height="20" loading="lazy" alt="arrow-forward icon">
        </a>

        <img src="img1/BMW_Logo.png" width="300" height="300" loading="lazy" alt="photography"
          class="abs-img abs-img-1" data-reveal>

        <img src="img1/lambo.png" width="265" height="275" loading="lazy" alt="photography"
          class="abs-img abs-img-2" data-reveal>


        <img src="img1/Porsche_Logo.png" width="175" height="175" loading="lazy" alt="photography"
          class="abs-img abs-img-4" data-reveal>

        <img src="img1/footer-shape.svg" width="185" height="134" loading="lazy" alt="" class="shape">

      </div>
    </div>

    <div class="footer-bottom">
      <div class="container">

        <a href="#" class="logo">
        </a>

       

        <p class="copyright" style="margin-right: 160px;">Creat By Aman</p>

      </div>
      <footer class="foote">
        <div class="containe">
          <div class="row">
            <div class="footer-col">
              <h4>company</h4>
              <ul>
                <li><a href="#">about us</a></li>
                <li><a href="#">Models</a></li>
                <li><a href="#">our services</a></li>
                <li><a href="#">privacy policy</a></li>
                <li><a href="#">Blogs</a></li>
   
              </ul>
            </div>
            <div class="footer-col">
              <h4>get help</h4>
              <ul>
                <li><a href="#">FAQ</a></li>
                <li><a href="#">shipping</a></li>
                <li><a href="#">returns</a></li>
                <li><a href="#">order status</a></li>
                <li><a href="#">payment options</a></li>
              </ul>
            </div>
            <div class="footer-col">
              <h4>Types Of Cars</h4>
              <ul>
                <li><a href="dv.html">Luxury Cars</a></li>
                <li><a href="dv.html">Super Cars</a></li>
                <li><a href="dv.html">SUV</a></li>
                <li><a href="dv.html">sedan</a></li>
                <li><a href="dv.html">Sport Cars</a></li>
   
              </ul>
            </div>
            <div class="footer-col">
              <h4>follow us</h4>
              <div class="social-links">

                <div class="tooltip-container">
                  <div class="tooltip">
                    <div class="profile">
                      <div class="user">
                        <div class="img"><img class="sd" src="img1/insta1.jpg" style="margin-left: 130px;" width="200" height="200"  alt=""></div>
                        <div class="details">
                          <div class="name"></div>
                          <div class="username"></div>
                        </div>
                      </div>
                      <div class="about"></div>
                    </div>
                  </div>
                  <div class="text">
                    <a class="icon" href="https://www.instagram.com/its.me_aman.77/">
                      <div class="layer">
                        <span></span>
                        <span></span>
                        <span></span>
                        <span></span>
                        <span class="instagramSVG">
                          <svg
                            fill="white"
                            class="svgIcon"
                            viewBox="0 0 448 512"
                            height="1.5em"
                            xmlns="http://www.w3.org/2000/svg"
                          >
                            <path
                              d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"
                            ></path>
                          </svg>
                        </span>
                      </div>
                      <div class="text">Instagram</div>
                    </a>
                  </div>
                </div>
                


                <div class="tool-container">
                  <div class="tool">
                    <div class="pro">
                      <div class="us">
                        <div class="im"><img class="sp" src="img1/facebook.jpg" width="200" height="200" style="margin-left: 450px; margin-top: 10px;" alt=""></div>
                        <div class="deta">
                          <div class="nam"></div>
                          <div class="usern"></div>
                        </div>
                      </div>
                      <div class="abou"></div>
                    </div>
                  </div>
                  <div class="tex">
                    <a class="ico" href="https://www.facebook.com/profile.php?id=61560468907805">
                      <div class="laye">
                        <span></span>
                        <span></span>
                        <span></span>
                        <span></span>
                        <span class="facebookSVG">
                          <svg
                            viewBox="0 0 40 40"
                            xml:space="preserve"
                            xmlns="http://www.w3.org/2000/svg"
                          >
                            <linearGradient
                              gradientUnits="userSpaceOnUse"
                              gradientTransform="matrix(40 0 0 -39.7778 11115.001 16212.334)"
                              y2="407.5726"
                              y1="406.6018"
                              x2="-277.375"
                              x1="-277.375"
                              id="a"
                            >
                              <stop stop-color="#0062e0" offset="0"></stop>
                              <stop stop-color="#19afff" offset="1"></stop>
                            </linearGradient>
                            <path
                              d="M16.7 39.8C7.2 38.1 0 29.9 0 20 0 9 9 0 20 0s20 9 20 20c0 9.9-7.2 18.1-16.7 19.8l-1.1-.9h-4.4l-1.1.9z"
                              fill="url(#a)"
                            ></path>
                            <path
                              d="m27.8 25.6.9-5.6h-5.3v-3.9c0-1.6.6-2.8 3-2.8H29V8.2c-1.4-.2-3-.4-4.4-.4-4.6 0-7.8 2.8-7.8 7.8V20h-5v5.6h5v14.1c1.1.2 2.2.3 3.3.3 1.1 0 2.2-.1 3.3-.3V25.6h4.4z"
                              fill="#fff"
                            ></path>
                          </svg>
                        </span>
                      </div>
                      <div class="tex">Facebook</div>
                    </a>
                  </div>
                </div>



                


              </div>
            </div>
          </div>
        </div>
     </footer>
   
    </div>

    <div class="footer-bg has-before">
      <img src="img1/footer-bg.jpg" width="1920" height="1135" loading="lazy" alt="photography"
        class="img-cover">
    </div>

  </footer>





  <!-- 
    - #BACK TO TOP
  -->

  <a href="#top" class="back-top-btn" aria-label="back to top" data-back-top-btn>0%</a>





  <!-- 
    - #CUSTOM CURSOR
  -->

  <div class="cursor" data-cursor></div>





  <!-- 
    - custom js link
  -->
  <script src="./assets/js/script.js"></script>
<script>

    'use strict';



// add Event on multiple elment

const addEventOnElements = function (elements, eventType, callback) {
  for (let i = 0; i < elements.length; i++) {
    elements[i].addEventListener(eventType, callback);
  }
}



// PRELOADING

const loadingElement = document.querySelector("[data-loading]");

window.addEventListener("load", function () {
  loadingElement.classList.add("loaded");
  document.body.classList.remove("active");
});



// MOBILE NAV TOGGLE

const [navTogglers, navLinks, navbar, overlay] = [
  document.querySelectorAll("[data-nav-toggler]"),
  document.querySelectorAll("[data-nav-link]"),
  document.querySelector("[data-navbar]"),
  document.querySelector("[data-overlay]")
];

const toggleNav = function () {
  navbar.classList.toggle("active");
  overlay.classList.toggle("active");
  document.body.classList.toggle("active");
}

addEventOnElements(navTogglers, "click", toggleNav);

const closeNav = function () {
  navbar.classList.remove("active");
  overlay.classList.remove("active");
  document.body.classList.remove("active");
}

addEventOnElements(navLinks, "click", closeNav);



// HEADER

const header = document.querySelector("[data-header]");

const activeElementOnScroll = function () {
  if (window.scrollY > 50) {
    header.classList.add("active");
  } else {
    header.classList.remove("active");
  }
}

window.addEventListener("scroll", activeElementOnScroll);



/**
 * TEXT ANIMATION EFFECT FOR HERO SECTION
 */

const letterBoxes = document.querySelectorAll("[data-letter-effect]");

let activeLetterBoxIndex = 0;
let lastActiveLetterBoxIndex = 0;
let totalLetterBoxDelay = 0;

const setLetterEffect = function () {

  // loop through all letter boxes
  for (let i = 0; i < letterBoxes.length; i++) {
    // set initial animation delay
    let letterAnimationDelay = 0;

    // get all character from the current letter box
    const letters = letterBoxes[i].textContent.trim();
    // remove all character from the current letter box
    letterBoxes[i].textContent = "";

    // loop through all letters
    for (let j = 0; j < letters.length; j++) {

      // create a span
      const span = document.createElement("span");

      // set animation delay on span
      span.style.animationDelay = `${letterAnimationDelay}s`;

      // set the "in" class on the span, if current letter box is active
      // otherwise class is "out"
      if (i === activeLetterBoxIndex) {
        span.classList.add("in");
      } else {
        span.classList.add("out");
      }

      // pass current letter into span
      span.textContent = letters[j];

      // add space class on span, when current letter contain space
      if (letters[j] === " ") span.classList.add("space");

      // pass the span on current letter box
      letterBoxes[i].appendChild(span);

      // skip letterAnimationDelay when loop is in the last index
      if (j >= letters.length - 1) break;
      // otherwise update
      letterAnimationDelay += 0.05;

    }

    // get total delay of active letter box
    if (i === activeLetterBoxIndex) {
      totalLetterBoxDelay = Number(letterAnimationDelay.toFixed(2));
    }

    // add active class on last active letter box
    if (i === lastActiveLetterBoxIndex) {
      letterBoxes[i].classList.add("active");
    } else {
      letterBoxes[i].classList.remove("active");
    }

  }

  setTimeout(function () {
    lastActiveLetterBoxIndex = activeLetterBoxIndex;

    // update activeLetterBoxIndex based on total letter boxes
    activeLetterBoxIndex >= letterBoxes.length - 1 ? activeLetterBoxIndex = 0 : activeLetterBoxIndex++;

    setLetterEffect();
  }, (totalLetterBoxDelay * 1000) + 3000);

}

// call the letter effect function after window loaded
window.addEventListener("load", setLetterEffect);



/**
 * BACK TO TOP BUTTON
 */

const backTopBtn = document.querySelector("[data-back-top-btn]");

window.addEventListener("scroll", function () {
  const bodyHeight = document.body.scrollHeight;
  const windowHeight = window.innerHeight;
  const scrollEndPos = bodyHeight - windowHeight;
  const totalScrollPercent = (window.scrollY / scrollEndPos) * 100;

  backTopBtn.textContent = `${totalScrollPercent.toFixed(0)}%`;

  // visible back top btn when scrolled 5% of the page
  if (totalScrollPercent > 5) {
    backTopBtn.classList.add("show");
  } else {
    backTopBtn.classList.remove("show");
  }
});



/**
 * SCROLL REVEAL
 */

const revealElements = document.querySelectorAll("[data-reveal]");

const scrollReveal = function () {
  for (let i = 0; i < revealElements.length; i++) {
    const elementIsInScreen = revealElements[i].getBoundingClientRect().top < window.innerHeight / 1.15;

    if (elementIsInScreen) {
      revealElements[i].classList.add("revealed");
    } else {
      revealElements[i].classList.remove("revealed");
    }
  }
}

window.addEventListener("scroll", scrollReveal);

scrollReveal();



/**
 * CUSTOM CURSOR
 */

const cursor = document.querySelector("[data-cursor]");
const anchorElements = document.querySelectorAll("a");
const buttons = document.querySelectorAll("button");

// change cursorElement position based on cursor move
document.body.addEventListener("mousemove", function (event) {
  setTimeout(function () {
    cursor.style.top = `${event.clientY}px`;
    cursor.style.left = `${event.clientX}px`;
  }, 100);
});

// add cursor hoverd class
const hoverActive = function () { cursor.classList.add("hovered"); }

// remove cursor hovered class
const hoverDeactive = function () { cursor.classList.remove("hovered"); }

// add hover effect on cursor, when hover on any button or hyperlink
addEventOnElements(anchorElements, "mouseover", hoverActive);
addEventOnElements(anchorElements, "mouseout", hoverDeactive);
addEventOnElements(buttons, "mouseover", hoverActive);
addEventOnElements(buttons, "mouseout", hoverDeactive);

// add disabled class on cursorElement, when mouse out of body
document.body.addEventListener("mouseout", function () {
  cursor.classList.add("disabled");
});

// remove diabled class on cursorElement, when mouse in the body
document.body.addEventListener("mouseover", function () {
  cursor.classList.remove("disabled");
});




         $(document).ready(function(){
    $('.counter').counterUp({
      delay: 10,
      time: 1200
    });
  });
</script>
</body>

</html>
