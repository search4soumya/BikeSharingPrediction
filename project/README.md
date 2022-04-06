<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />

<title>bike_sharing_prediction</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>



<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.7.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.7.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.fa-pull-left {
  float: left;
}
.fa-pull-right {
  float: right;
}
.fa.fa-pull-left {
  margin-right: .3em;
}
.fa.fa-pull-right {
  margin-left: .3em;
}
/* Deprecated as of 4.4.0 */
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
.fa-pulse {
  -webkit-animation: fa-spin 1s infinite steps(8);
  animation: fa-spin 1s infinite steps(8);
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=1)";
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2)";
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=3)";
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1)";
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1)";
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook-f:before,
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-feed:before,
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before,
.fa-gratipay:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper-pp:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-resistance:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-y-combinator-square:before,
.fa-yc-square:before,
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
.fa-buysellads:before {
  content: "\f20d";
}
.fa-connectdevelop:before {
  content: "\f20e";
}
.fa-dashcube:before {
  content: "\f210";
}
.fa-forumbee:before {
  content: "\f211";
}
.fa-leanpub:before {
  content: "\f212";
}
.fa-sellsy:before {
  content: "\f213";
}
.fa-shirtsinbulk:before {
  content: "\f214";
}
.fa-simplybuilt:before {
  content: "\f215";
}
.fa-skyatlas:before {
  content: "\f216";
}
.fa-cart-plus:before {
  content: "\f217";
}
.fa-cart-arrow-down:before {
  content: "\f218";
}
.fa-diamond:before {
  content: "\f219";
}
.fa-ship:before {
  content: "\f21a";
}
.fa-user-secret:before {
  content: "\f21b";
}
.fa-motorcycle:before {
  content: "\f21c";
}
.fa-street-view:before {
  content: "\f21d";
}
.fa-heartbeat:before {
  content: "\f21e";
}
.fa-venus:before {
  content: "\f221";
}
.fa-mars:before {
  content: "\f222";
}
.fa-mercury:before {
  content: "\f223";
}
.fa-intersex:before,
.fa-transgender:before {
  content: "\f224";
}
.fa-transgender-alt:before {
  content: "\f225";
}
.fa-venus-double:before {
  content: "\f226";
}
.fa-mars-double:before {
  content: "\f227";
}
.fa-venus-mars:before {
  content: "\f228";
}
.fa-mars-stroke:before {
  content: "\f229";
}
.fa-mars-stroke-v:before {
  content: "\f22a";
}
.fa-mars-stroke-h:before {
  content: "\f22b";
}
.fa-neuter:before {
  content: "\f22c";
}
.fa-genderless:before {
  content: "\f22d";
}
.fa-facebook-official:before {
  content: "\f230";
}
.fa-pinterest-p:before {
  content: "\f231";
}
.fa-whatsapp:before {
  content: "\f232";
}
.fa-server:before {
  content: "\f233";
}
.fa-user-plus:before {
  content: "\f234";
}
.fa-user-times:before {
  content: "\f235";
}
.fa-hotel:before,
.fa-bed:before {
  content: "\f236";
}
.fa-viacoin:before {
  content: "\f237";
}
.fa-train:before {
  content: "\f238";
}
.fa-subway:before {
  content: "\f239";
}
.fa-medium:before {
  content: "\f23a";
}
.fa-yc:before,
.fa-y-combinator:before {
  content: "\f23b";
}
.fa-optin-monster:before {
  content: "\f23c";
}
.fa-opencart:before {
  content: "\f23d";
}
.fa-expeditedssl:before {
  content: "\f23e";
}
.fa-battery-4:before,
.fa-battery:before,
.fa-battery-full:before {
  content: "\f240";
}
.fa-battery-3:before,
.fa-battery-three-quarters:before {
  content: "\f241";
}
.fa-battery-2:before,
.fa-battery-half:before {
  content: "\f242";
}
.fa-battery-1:before,
.fa-battery-quarter:before {
  content: "\f243";
}
.fa-battery-0:before,
.fa-battery-empty:before {
  content: "\f244";
}
.fa-mouse-pointer:before {
  content: "\f245";
}
.fa-i-cursor:before {
  content: "\f246";
}
.fa-object-group:before {
  content: "\f247";
}
.fa-object-ungroup:before {
  content: "\f248";
}
.fa-sticky-note:before {
  content: "\f249";
}
.fa-sticky-note-o:before {
  content: "\f24a";
}
.fa-cc-jcb:before {
  content: "\f24b";
}
.fa-cc-diners-club:before {
  content: "\f24c";
}
.fa-clone:before {
  content: "\f24d";
}
.fa-balance-scale:before {
  content: "\f24e";
}
.fa-hourglass-o:before {
  content: "\f250";
}
.fa-hourglass-1:before,
.fa-hourglass-start:before {
  content: "\f251";
}
.fa-hourglass-2:before,
.fa-hourglass-half:before {
  content: "\f252";
}
.fa-hourglass-3:before,
.fa-hourglass-end:before {
  content: "\f253";
}
.fa-hourglass:before {
  content: "\f254";
}
.fa-hand-grab-o:before,
.fa-hand-rock-o:before {
  content: "\f255";
}
.fa-hand-stop-o:before,
.fa-hand-paper-o:before {
  content: "\f256";
}
.fa-hand-scissors-o:before {
  content: "\f257";
}
.fa-hand-lizard-o:before {
  content: "\f258";
}
.fa-hand-spock-o:before {
  content: "\f259";
}
.fa-hand-pointer-o:before {
  content: "\f25a";
}
.fa-hand-peace-o:before {
  content: "\f25b";
}
.fa-trademark:before {
  content: "\f25c";
}
.fa-registered:before {
  content: "\f25d";
}
.fa-creative-commons:before {
  content: "\f25e";
}
.fa-gg:before {
  content: "\f260";
}
.fa-gg-circle:before {
  content: "\f261";
}
.fa-tripadvisor:before {
  content: "\f262";
}
.fa-odnoklassniki:before {
  content: "\f263";
}
.fa-odnoklassniki-square:before {
  content: "\f264";
}
.fa-get-pocket:before {
  content: "\f265";
}
.fa-wikipedia-w:before {
  content: "\f266";
}
.fa-safari:before {
  content: "\f267";
}
.fa-chrome:before {
  content: "\f268";
}
.fa-firefox:before {
  content: "\f269";
}
.fa-opera:before {
  content: "\f26a";
}
.fa-internet-explorer:before {
  content: "\f26b";
}
.fa-tv:before,
.fa-television:before {
  content: "\f26c";
}
.fa-contao:before {
  content: "\f26d";
}
.fa-500px:before {
  content: "\f26e";
}
.fa-amazon:before {
  content: "\f270";
}
.fa-calendar-plus-o:before {
  content: "\f271";
}
.fa-calendar-minus-o:before {
  content: "\f272";
}
.fa-calendar-times-o:before {
  content: "\f273";
}
.fa-calendar-check-o:before {
  content: "\f274";
}
.fa-industry:before {
  content: "\f275";
}
.fa-map-pin:before {
  content: "\f276";
}
.fa-map-signs:before {
  content: "\f277";
}
.fa-map-o:before {
  content: "\f278";
}
.fa-map:before {
  content: "\f279";
}
.fa-commenting:before {
  content: "\f27a";
}
.fa-commenting-o:before {
  content: "\f27b";
}
.fa-houzz:before {
  content: "\f27c";
}
.fa-vimeo:before {
  content: "\f27d";
}
.fa-black-tie:before {
  content: "\f27e";
}
.fa-fonticons:before {
  content: "\f280";
}
.fa-reddit-alien:before {
  content: "\f281";
}
.fa-edge:before {
  content: "\f282";
}
.fa-credit-card-alt:before {
  content: "\f283";
}
.fa-codiepie:before {
  content: "\f284";
}
.fa-modx:before {
  content: "\f285";
}
.fa-fort-awesome:before {
  content: "\f286";
}
.fa-usb:before {
  content: "\f287";
}
.fa-product-hunt:before {
  content: "\f288";
}
.fa-mixcloud:before {
  content: "\f289";
}
.fa-scribd:before {
  content: "\f28a";
}
.fa-pause-circle:before {
  content: "\f28b";
}
.fa-pause-circle-o:before {
  content: "\f28c";
}
.fa-stop-circle:before {
  content: "\f28d";
}
.fa-stop-circle-o:before {
  content: "\f28e";
}
.fa-shopping-bag:before {
  content: "\f290";
}
.fa-shopping-basket:before {
  content: "\f291";
}
.fa-hashtag:before {
  content: "\f292";
}
.fa-bluetooth:before {
  content: "\f293";
}
.fa-bluetooth-b:before {
  content: "\f294";
}
.fa-percent:before {
  content: "\f295";
}
.fa-gitlab:before {
  content: "\f296";
}
.fa-wpbeginner:before {
  content: "\f297";
}
.fa-wpforms:before {
  content: "\f298";
}
.fa-envira:before {
  content: "\f299";
}
.fa-universal-access:before {
  content: "\f29a";
}
.fa-wheelchair-alt:before {
  content: "\f29b";
}
.fa-question-circle-o:before {
  content: "\f29c";
}
.fa-blind:before {
  content: "\f29d";
}
.fa-audio-description:before {
  content: "\f29e";
}
.fa-volume-control-phone:before {
  content: "\f2a0";
}
.fa-braille:before {
  content: "\f2a1";
}
.fa-assistive-listening-systems:before {
  content: "\f2a2";
}
.fa-asl-interpreting:before,
.fa-american-sign-language-interpreting:before {
  content: "\f2a3";
}
.fa-deafness:before,
.fa-hard-of-hearing:before,
.fa-deaf:before {
  content: "\f2a4";
}
.fa-glide:before {
  content: "\f2a5";
}
.fa-glide-g:before {
  content: "\f2a6";
}
.fa-signing:before,
.fa-sign-language:before {
  content: "\f2a7";
}
.fa-low-vision:before {
  content: "\f2a8";
}
.fa-viadeo:before {
  content: "\f2a9";
}
.fa-viadeo-square:before {
  content: "\f2aa";
}
.fa-snapchat:before {
  content: "\f2ab";
}
.fa-snapchat-ghost:before {
  content: "\f2ac";
}
.fa-snapchat-square:before {
  content: "\f2ad";
}
.fa-pied-piper:before {
  content: "\f2ae";
}
.fa-first-order:before {
  content: "\f2b0";
}
.fa-yoast:before {
  content: "\f2b1";
}
.fa-themeisle:before {
  content: "\f2b2";
}
.fa-google-plus-circle:before,
.fa-google-plus-official:before {
  content: "\f2b3";
}
.fa-fa:before,
.fa-font-awesome:before {
  content: "\f2b4";
}
.fa-handshake-o:before {
  content: "\f2b5";
}
.fa-envelope-open:before {
  content: "\f2b6";
}
.fa-envelope-open-o:before {
  content: "\f2b7";
}
.fa-linode:before {
  content: "\f2b8";
}
.fa-address-book:before {
  content: "\f2b9";
}
.fa-address-book-o:before {
  content: "\f2ba";
}
.fa-vcard:before,
.fa-address-card:before {
  content: "\f2bb";
}
.fa-vcard-o:before,
.fa-address-card-o:before {
  content: "\f2bc";
}
.fa-user-circle:before {
  content: "\f2bd";
}
.fa-user-circle-o:before {
  content: "\f2be";
}
.fa-user-o:before {
  content: "\f2c0";
}
.fa-id-badge:before {
  content: "\f2c1";
}
.fa-drivers-license:before,
.fa-id-card:before {
  content: "\f2c2";
}
.fa-drivers-license-o:before,
.fa-id-card-o:before {
  content: "\f2c3";
}
.fa-quora:before {
  content: "\f2c4";
}
.fa-free-code-camp:before {
  content: "\f2c5";
}
.fa-telegram:before {
  content: "\f2c6";
}
.fa-thermometer-4:before,
.fa-thermometer:before,
.fa-thermometer-full:before {
  content: "\f2c7";
}
.fa-thermometer-3:before,
.fa-thermometer-three-quarters:before {
  content: "\f2c8";
}
.fa-thermometer-2:before,
.fa-thermometer-half:before {
  content: "\f2c9";
}
.fa-thermometer-1:before,
.fa-thermometer-quarter:before {
  content: "\f2ca";
}
.fa-thermometer-0:before,
.fa-thermometer-empty:before {
  content: "\f2cb";
}
.fa-shower:before {
  content: "\f2cc";
}
.fa-bathtub:before,
.fa-s15:before,
.fa-bath:before {
  content: "\f2cd";
}
.fa-podcast:before {
  content: "\f2ce";
}
.fa-window-maximize:before {
  content: "\f2d0";
}
.fa-window-minimize:before {
  content: "\f2d1";
}
.fa-window-restore:before {
  content: "\f2d2";
}
.fa-times-rectangle:before,
.fa-window-close:before {
  content: "\f2d3";
}
.fa-times-rectangle-o:before,
.fa-window-close-o:before {
  content: "\f2d4";
}
.fa-bandcamp:before {
  content: "\f2d5";
}
.fa-grav:before {
  content: "\f2d6";
}
.fa-etsy:before {
  content: "\f2d7";
}
.fa-imdb:before {
  content: "\f2d8";
}
.fa-ravelry:before {
  content: "\f2d9";
}
.fa-eercast:before {
  content: "\f2da";
}
.fa-microchip:before {
  content: "\f2db";
}
.fa-snowflake-o:before {
  content: "\f2dc";
}
.fa-superpowers:before {
  content: "\f2dd";
}
.fa-wpexplorer:before {
  content: "\f2de";
}
.fa-meetup:before {
  content: "\f2e0";
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
div.traceback-wrapper pre.traceback {
  max-height: 600px;
  overflow: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5px;
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
[dir="rtl"] #ipython_notebook {
  margin-right: 10px;
  margin-left: 0;
}
[dir="rtl"] #ipython_notebook.pull-left {
  float: right !important;
  float: right;
}
.flex-spacer {
  flex: 1;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#kernel_logo_widget {
  margin: 0 10px;
}
span#login_widget {
  float: right;
}
[dir="rtl"] span#login_widget {
  float: left;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
.modal-header {
  cursor: move;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
[dir="rtl"] .center-nav form.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] .center-nav .navbar-text {
  float: right;
}
[dir="rtl"] .navbar-inner {
  text-align: right;
}
[dir="rtl"] div.text-left {
  text-align: right;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}
.alternate_upload .btn-xs > input.fileinput {
  margin: -1px -5px;
}
.alternate_upload .btn-upload {
  position: relative;
  height: 22px;
}
::-webkit-file-upload-button {
  cursor: pointer;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
ul#tabs {
  margin-bottom: 4px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
[dir="rtl"] ul#tabs.nav-tabs > li {
  float: right;
}
[dir="rtl"] ul#tabs.nav.nav-tabs {
  padding-right: 0;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons .pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .list_toolbar .col-sm-4,
[dir="rtl"] .list_toolbar .col-sm-8 {
  float: right;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: text-bottom;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
[dir="rtl"] .list_item > div input {
  margin-right: 0;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_modified {
  margin-right: 7px;
  margin-left: 7px;
}
[dir="rtl"] .item_modified.pull-right {
  float: left !important;
  float: left;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
[dir="rtl"] .item_buttons.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .item_buttons .kernel-name {
  margin-left: 7px;
  float: right;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
.sort_button {
  display: inline-block;
  padding-left: 7px;
}
[dir="rtl"] .sort_button.pull-right {
  float: left !important;
  float: left;
}
#tree-selector {
  padding-right: 0px;
}
#button-select-all {
  min-width: 50px;
}
[dir="rtl"] #button-select-all.btn {
  float: right ;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
  margin-top: 2px;
  height: 16px;
}
[dir="rtl"] #select-all.pull-left {
  float: right !important;
  float: right;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.fa-pull-left {
  margin-right: .3em;
}
.folder_icon:before.fa-pull-right {
  margin-left: .3em;
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.fa-pull-left {
  margin-right: .3em;
}
.file_icon:before.fa-pull-right {
  margin-left: .3em;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
#new-menu .dropdown-header {
  font-size: 10px;
  border-bottom: 1px solid #e5e5e5;
  padding: 0 0 3px;
  margin: -3px 20px 0;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.move-button {
  display: none;
}
.download-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
.CodeMirror-dialog {
  background-color: #fff;
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI escape sequences */
/* The color values are a mix of
   http://www.xcolors.net/dl/baskerville-ivorylight and
   http://www.xcolors.net/dl/euphrasia */
.ansi-black-fg {
  color: #3E424D;
}
.ansi-black-bg {
  background-color: #3E424D;
}
.ansi-black-intense-fg {
  color: #282C36;
}
.ansi-black-intense-bg {
  background-color: #282C36;
}
.ansi-red-fg {
  color: #E75C58;
}
.ansi-red-bg {
  background-color: #E75C58;
}
.ansi-red-intense-fg {
  color: #B22B31;
}
.ansi-red-intense-bg {
  background-color: #B22B31;
}
.ansi-green-fg {
  color: #00A250;
}
.ansi-green-bg {
  background-color: #00A250;
}
.ansi-green-intense-fg {
  color: #007427;
}
.ansi-green-intense-bg {
  background-color: #007427;
}
.ansi-yellow-fg {
  color: #DDB62B;
}
.ansi-yellow-bg {
  background-color: #DDB62B;
}
.ansi-yellow-intense-fg {
  color: #B27D12;
}
.ansi-yellow-intense-bg {
  background-color: #B27D12;
}
.ansi-blue-fg {
  color: #208FFB;
}
.ansi-blue-bg {
  background-color: #208FFB;
}
.ansi-blue-intense-fg {
  color: #0065CA;
}
.ansi-blue-intense-bg {
  background-color: #0065CA;
}
.ansi-magenta-fg {
  color: #D160C4;
}
.ansi-magenta-bg {
  background-color: #D160C4;
}
.ansi-magenta-intense-fg {
  color: #A03196;
}
.ansi-magenta-intense-bg {
  background-color: #A03196;
}
.ansi-cyan-fg {
  color: #60C6C8;
}
.ansi-cyan-bg {
  background-color: #60C6C8;
}
.ansi-cyan-intense-fg {
  color: #258F8F;
}
.ansi-cyan-intense-bg {
  background-color: #258F8F;
}
.ansi-white-fg {
  color: #C5C1B4;
}
.ansi-white-bg {
  background-color: #C5C1B4;
}
.ansi-white-intense-fg {
  color: #A1A6B2;
}
.ansi-white-intense-bg {
  background-color: #A1A6B2;
}
.ansi-default-inverse-fg {
  color: #FFFFFF;
}
.ansi-default-inverse-bg {
  background-color: #000000;
}
.ansi-bold {
  font-weight: bold;
}
.ansi-underline {
  text-decoration: underline;
}
/* The following styles are deprecated an will be removed in a future version */
.ansibold {
  font-weight: bold;
}
.ansi-inverse {
  outline: 0.5px dotted;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  position: relative;
  overflow: visible;
}
div.cell:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: transparent;
}
div.cell.jupyter-soft-selected {
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected,
div.cell.selected.jupyter-soft-selected {
  border-color: #ababab;
}
div.cell.selected:before,
div.cell.selected.jupyter-soft-selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #42A5F5;
}
@media print {
  div.cell.selected,
  div.cell.selected.jupyter-soft-selected {
    border-color: transparent;
  }
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
}
.edit_mode div.cell.selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #66BB6A;
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  /* Note that this should set vertical padding only, since CodeMirror assumes
       that horizontal padding will be set on CodeMirror pre */
  padding: 0.4em 0;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. This sets horizontal padding only,
    use .CodeMirror-lines for vertical */
  padding: 0 0.4em;
  border: 0;
  border-radius: 0;
}
.CodeMirror-cursor {
  border-left: 1.4px solid black;
}
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .CodeMirror-cursor {
    border-left: 2px solid black;
  }
}
@media screen and (min-width: 4320px) {
  .CodeMirror-cursor {
    border-left: 4px solid black;
  }
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
div.output_area .mglyph > img {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 1px 0 1px 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul:not(.list-inline),
.rendered_html ol:not(.list-inline) {
  padding-left: 2em;
}
.rendered_html ul {
  list-style: disc;
}
.rendered_html ul ul {
  list-style: square;
  margin-top: 0;
}
.rendered_html ul ul ul {
  list-style: circle;
}
.rendered_html ol {
  list-style: decimal;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin-top: 0;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
  padding: 0px;
  background-color: #fff;
}
.rendered_html code {
  background-color: #eff0f1;
}
.rendered_html p code {
  padding: 1px 5px;
}
.rendered_html pre code {
  background-color: #fff;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  color: #000;
  font-size: 100%;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: none;
  border-collapse: collapse;
  border-spacing: 0;
  color: black;
  font-size: 12px;
  table-layout: fixed;
}
.rendered_html thead {
  border-bottom: 1px solid black;
  vertical-align: bottom;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  text-align: right;
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html tbody tr:nth-child(odd) {
  background: #f5f5f5;
}
.rendered_html tbody tr:hover {
  background: rgba(66, 165, 245, 0.2);
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
.rendered_html .alert {
  margin-bottom: initial;
}
.rendered_html * + .alert {
  margin-top: 1em;
}
[dir="rtl"] .rendered_html p {
  text-align: right;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.rendered .rendered_html tr,
.text_cell.rendered .rendered_html th,
.text_cell.rendered .rendered_html td {
  max-width: none;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.text_cell .dropzone .input_area {
  border: 2px dashed #bababa;
  margin: -1px;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
.jupyter-keybindings {
  padding: 1px;
  line-height: 24px;
  border-bottom: 1px solid gray;
}
.jupyter-keybindings input {
  margin: 0;
  padding: 0;
  border: none;
}
.jupyter-keybindings i {
  padding: 6px;
}
.well code {
  background-color: #ffffff;
  border-color: #ababab;
  border-width: 1px;
  border-style: solid;
  padding: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.tags_button_container {
  width: 100%;
  display: flex;
}
.tag-container {
  display: flex;
  flex-direction: row;
  flex-grow: 1;
  overflow: hidden;
  position: relative;
}
.tag-container > * {
  margin: 0 4px;
}
.remove-tag-btn {
  margin-left: 4px;
}
.tags-input {
  display: flex;
}
.cell-tag:last-child:after {
  content: "";
  position: absolute;
  right: 0;
  width: 40px;
  height: 100%;
  /* Fade to background color of cell toolbar */
  background: linear-gradient(to right, rgba(0, 0, 0, 0), #EEE);
}
.tags-input > * {
  margin-left: 4px;
}
.cell-tag,
.tags-input input,
.tags-input button {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  box-shadow: none;
  width: inherit;
  font-size: inherit;
  height: 22px;
  line-height: 22px;
  padding: 0px 4px;
  display: inline-block;
}
.cell-tag:focus,
.tags-input input:focus,
.tags-input button:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.cell-tag::-moz-placeholder,
.tags-input input::-moz-placeholder,
.tags-input button::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.cell-tag:-ms-input-placeholder,
.tags-input input:-ms-input-placeholder,
.tags-input button:-ms-input-placeholder {
  color: #999;
}
.cell-tag::-webkit-input-placeholder,
.tags-input input::-webkit-input-placeholder,
.tags-input button::-webkit-input-placeholder {
  color: #999;
}
.cell-tag::-ms-expand,
.tags-input input::-ms-expand,
.tags-input button::-ms-expand {
  border: 0;
  background-color: transparent;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
.cell-tag[readonly],
.tags-input input[readonly],
.tags-input button[readonly],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  background-color: #eeeeee;
  opacity: 1;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  cursor: not-allowed;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button {
  height: auto;
}
select.cell-tag,
select.tags-input input,
select.tags-input button {
  height: 30px;
  line-height: 30px;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button,
select[multiple].cell-tag,
select[multiple].tags-input input,
select[multiple].tags-input button {
  height: auto;
}
.cell-tag,
.tags-input button {
  padding: 0px 4px;
}
.cell-tag {
  background-color: #fff;
  white-space: nowrap;
}
.tags-input input[type=text]:focus {
  outline: none;
  box-shadow: none;
  border-color: #ccc;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
[dir="rtl"] #kernel_logo_widget {
  float: left !important;
  float: left;
}
.modal .modal-body .move-path {
  display: flex;
  flex-direction: row;
  justify-content: space;
  align-items: center;
}
.modal .modal-body .move-path .server-root {
  padding-right: 20px;
}
.modal .modal-body .move-path .path-input {
  flex: 1;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
[dir="rtl"] #menubar .navbar-toggle {
  float: right;
}
[dir="rtl"] #menubar .navbar-collapse {
  clear: right;
}
[dir="rtl"] #menubar .navbar-nav {
  float: right;
}
[dir="rtl"] #menubar .nav {
  padding-right: 0px;
}
[dir="rtl"] #menubar .navbar-nav > li {
  float: right;
}
[dir="rtl"] #menubar .navbar-right {
  float: left !important;
}
[dir="rtl"] ul.dropdown-menu {
  text-align: right;
  left: auto;
}
[dir="rtl"] ul#new-menu.dropdown-menu {
  right: auto;
  left: 0;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
[dir="rtl"] i.menu-icon.pull-right {
  float: left !important;
  float: left;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
[dir="rtl"] ul#help_menu li a {
  padding-left: 2.2em;
}
[dir="rtl"] ul#help_menu li a i {
  margin-right: 0;
  margin-left: -1.2em;
}
[dir="rtl"] ul#help_menu li a i.pull-right {
  float: left !important;
  float: left;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
[dir="rtl"] .dropdown-submenu > .dropdown-menu {
  right: 100%;
  margin-right: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.fa-pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.fa-pull-right {
  margin-left: .3em;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
[dir="rtl"] .dropdown-submenu > a:after {
  float: left;
  content: "\f0d9";
  margin-right: 0;
  margin-left: -10px;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
[dir="rtl"] #notification_area {
  float: left !important;
  float: left;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] .indicator_area {
  float: left !important;
  float: left;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
[dir="rtl"] #kernel_indicator {
  float: left !important;
  float: left;
  border-left: 0;
  border-right: 1px solid;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] #modal_indicator {
  float: left !important;
  float: left;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  height: 30px;
  margin-top: 4px;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  width: 50%;
  flex: 1;
}
span.save_widget span.filename {
  height: 100%;
  line-height: 1em;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
[dir="rtl"] span.save_widget.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] span.save_widget span.filename {
  margin-left: 0;
  margin-right: 16px;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
  white-space: nowrap;
  padding: 0 5px;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
    padding: 0 0 0 5px;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
.toolbar-btn-label {
  margin-left: 6px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
[dir="rtl"] .btn-group > .btn,
.btn-group-vertical > .btn {
  float: right;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
[dir="rtl"] ul.typeahead-list i {
  margin-left: 0;
  margin-right: -10px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
ul.typeahead-list  > li > a.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .typeahead-list {
  text-align: right;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  min-width: 20px;
  color: transparent;
}
[dir="rtl"] .no-shortcut.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .command-shortcut.pull-right {
  float: left !important;
  float: left;
}
.command-shortcut:before {
  content: "(command mode)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
[dir="rtl"] .edit-shortcut.pull-right {
  float: left !important;
  float: left;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
[dir="ltr"] #find-and-replace .input-group-btn + .form-control {
  border-left: none;
}
[dir="rtl"] #find-and-replace .input-group-btn + .form-control {
  border-right: none;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/latest.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Predict-Bike-Sharing-Demand-with-AutoGluon-Template">Predict Bike Sharing Demand with AutoGluon Template<a class="anchor-link" href="#Predict-Bike-Sharing-Demand-with-AutoGluon-Template">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Project:-Predict-Bike-Sharing-Demand-with-AutoGluon">Project: Predict Bike Sharing Demand with AutoGluon<a class="anchor-link" href="#Project:-Predict-Bike-Sharing-Demand-with-AutoGluon">&#182;</a></h2><p>This notebook is a template with each step that you need to complete for the project.</p>
<p>Please fill in your code where there are explicit <code>?</code> markers in the notebook. You are welcome to add more cells and code as you see fit.</p>
<p>Once you have completed all the code implementations, please export your notebook as a HTML file so the reviews can view your code. Make sure you have all outputs correctly outputted.</p>
<p><code>File-&gt; Export Notebook As... -&gt; Export Notebook as HTML</code></p>
<p>There is a writeup to complete as well after all code implememtation is done. Please answer all questions and attach the necessary tables and charts. You can complete the writeup in either markdown or PDF.</p>
<p>Completing the code template and writeup template will cover all of the rubric points for this project.</p>
<p>The rubric contains "Stand Out Suggestions" for enhancing the project beyond the minimum requirements. The stand out suggestions are optional. If you decide to pursue the "stand out suggestions", you can include the code in this notebook and also discuss the results in the writeup file.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Install-packages">Install packages<a class="anchor-link" href="#Install-packages">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">!</span>pip install --quiet kaggle
<span class="o">!</span>pip install --quiet -U pip
<span class="o">!</span>pip install --quiet -U setuptools wheel
<span class="o">!</span>pip install --quiet -U <span class="s2">&quot;mxnet&lt;2.0.0&quot;</span> <span class="nv">bokeh</span><span class="o">==</span><span class="m">2</span>.0.1
<span class="o">!</span>pip install --quiet autogluon --no-cache-dir
<span class="c1"># Without --no-cache-dir, smaller aws instances may have trouble installing</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre><span class="ansi-yellow-fg">WARNING: Running pip as the &#39;root&#39; user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv</span>
<span class="ansi-yellow-fg">WARNING: You are using pip version 21.3.1; however, version 22.0.4 is available.
You should consider upgrading via the &#39;/usr/local/bin/python3.7 -m pip install --upgrade pip&#39; command.</span>
<span class="ansi-yellow-fg">WARNING: Running pip as the &#39;root&#39; user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv</span>
<span class="ansi-yellow-fg">WARNING: Running pip as the &#39;root&#39; user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv</span><span class="ansi-yellow-fg">
</span><span class="ansi-yellow-fg">WARNING: Running pip as the &#39;root&#39; user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv</span><span class="ansi-yellow-fg">
</span><span class="ansi-yellow-fg">WARNING: Running pip as the &#39;root&#39; user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv</span><span class="ansi-yellow-fg">
</span></pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Setup-Kaggle-API-Key">Setup Kaggle API Key<a class="anchor-link" href="#Setup-Kaggle-API-Key">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># create the .kaggle directory and an empty kaggle.json file</span>
<span class="o">!</span>mkdir -p /root/.kaggle
<span class="o">!</span>touch /root/.kaggle/kaggle.json
<span class="o">!</span>chmod <span class="m">600</span> /root/.kaggle/kaggle.json
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Fill in your user name and key from creating the kaggle account and API token file</span>
<span class="kn">import</span> <span class="nn">json</span>
<span class="n">kaggle_username</span> <span class="o">=</span> <span class="s2">&quot;search4soumya&quot;</span>
<span class="n">kaggle_key</span> <span class="o">=</span> <span class="s2">&quot;34b205749cf415db09e3997803f1cbdc&quot;</span>

<span class="c1"># Save API token the kaggle.json file</span>
<span class="k">with</span> <span class="nb">open</span><span class="p">(</span><span class="s2">&quot;/root/.kaggle/kaggle.json&quot;</span><span class="p">,</span> <span class="s2">&quot;w&quot;</span><span class="p">)</span> <span class="k">as</span> <span class="n">f</span><span class="p">:</span>
    <span class="n">f</span><span class="o">.</span><span class="n">write</span><span class="p">(</span><span class="n">json</span><span class="o">.</span><span class="n">dumps</span><span class="p">({</span><span class="s2">&quot;username&quot;</span><span class="p">:</span> <span class="n">kaggle_username</span><span class="p">,</span> <span class="s2">&quot;key&quot;</span><span class="p">:</span> <span class="n">kaggle_key</span><span class="p">}))</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Download-and-explore-dataset">Download and explore dataset<a class="anchor-link" href="#Download-and-explore-dataset">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Download the dataset, it will be in a .zip file so you&#39;ll need to unzip it as well.</span>
<span class="o">!</span>kaggle competitions download -c bike-sharing-demand
<span class="c1"># If you already downloaded it you can use the -o command to overwrite the file</span>
<span class="o">!</span>unzip -o bike-sharing-demand.zip
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>bike-sharing-demand.zip: Skipping, found more recently modified local copy (use --force to force download)
Archive:  bike-sharing-demand.zip
  inflating: sampleSubmission.csv    
  inflating: test.csv                
  inflating: train.csv               
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">from</span> <span class="nn">datetime</span> <span class="kn">import</span> <span class="n">datetime</span>

<span class="kn">from</span> <span class="nn">autogluon.tabular</span> <span class="kn">import</span> <span class="n">TabularPredictor</span>
<span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="kn">import</span> <span class="n">StandardScaler</span><span class="p">,</span><span class="n">LabelEncoder</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">train_test_split</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="kn">import</span> <span class="n">mean_absolute_error</span><span class="p">,</span> <span class="n">r2_score</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span> 

<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>/usr/local/lib/python3.7/site-packages/tqdm/auto.py:22: TqdmWarning: IProgress not found. Please update jupyter and ipywidgets. See https://ipywidgets.readthedocs.io/en/stable/user_install.html
  from .autonotebook import tqdm as notebook_tqdm
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Create the train dataset in pandas by reading the csv</span>
<span class="c1"># Set the parsing of the datetime column so you can use some of the `dt` features in pandas later</span>
<span class="n">train</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;train.csv&#39;</span><span class="p">)</span>
<span class="n">train</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span> <span class="s1">&#39;datetime&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">train</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span> <span class="s1">&#39;datetime&#39;</span><span class="p">])</span>

<span class="c1">#train[&#39;year&#39;] = pd.to_datetime(train.loc[:,&quot;datetime&quot;]).dt.year</span>
<span class="c1">#train[&#39;month&#39;]= pd.to_datetime(train.loc[:,&quot;datetime&quot;]).dt.month</span>
<span class="c1">#train[&#39;date&#39;]= pd.to_datetime(train.loc[:,&quot;datetime&quot;]).dt.day</span>
<span class="c1">#train[&#39;hour&#39;]= pd.to_datetime(train.loc[:,&quot;datetime&quot;]).dt.hour</span>
<span class="c1">#train = train.drop([&quot;datetime&quot;], axis = 1)</span>
<span class="n">train</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[7]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>datetime</th>
      <th>season</th>
      <th>holiday</th>
      <th>workingday</th>
      <th>weather</th>
      <th>temp</th>
      <th>atemp</th>
      <th>humidity</th>
      <th>windspeed</th>
      <th>casual</th>
      <th>registered</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2011-01-01 00:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>81</td>
      <td>0.0</td>
      <td>3</td>
      <td>13</td>
      <td>16</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2011-01-01 01:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.02</td>
      <td>13.635</td>
      <td>80</td>
      <td>0.0</td>
      <td>8</td>
      <td>32</td>
      <td>40</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2011-01-01 02:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.02</td>
      <td>13.635</td>
      <td>80</td>
      <td>0.0</td>
      <td>5</td>
      <td>27</td>
      <td>32</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2011-01-01 03:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>75</td>
      <td>0.0</td>
      <td>3</td>
      <td>10</td>
      <td>13</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2011-01-01 04:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>75</td>
      <td>0.0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># find the datatype for each of the attribute </span>
<span class="n">train</span><span class="o">.</span><span class="n">info</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>&lt;class &#39;pandas.core.frame.DataFrame&#39;&gt;
RangeIndex: 10886 entries, 0 to 10885
Data columns (total 12 columns):
 #   Column      Non-Null Count  Dtype         
---  ------      --------------  -----         
 0   datetime    10886 non-null  datetime64[ns]
 1   season      10886 non-null  int64         
 2   holiday     10886 non-null  int64         
 3   workingday  10886 non-null  int64         
 4   weather     10886 non-null  int64         
 5   temp        10886 non-null  float64       
 6   atemp       10886 non-null  float64       
 7   humidity    10886 non-null  int64         
 8   windspeed   10886 non-null  float64       
 9   casual      10886 non-null  int64         
 10  registered  10886 non-null  int64         
 11  count       10886 non-null  int64         
dtypes: datetime64[ns](1), float64(3), int64(8)
memory usage: 1020.7 KB
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Simple output of the train dataset to view some of the min/max/varition of the dataset features.</span>
<span class="n">train</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[9]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>season</th>
      <th>holiday</th>
      <th>workingday</th>
      <th>weather</th>
      <th>temp</th>
      <th>atemp</th>
      <th>humidity</th>
      <th>windspeed</th>
      <th>casual</th>
      <th>registered</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>10886.000000</td>
      <td>10886.000000</td>
      <td>10886.000000</td>
      <td>10886.000000</td>
      <td>10886.00000</td>
      <td>10886.000000</td>
      <td>10886.000000</td>
      <td>10886.000000</td>
      <td>10886.000000</td>
      <td>10886.000000</td>
      <td>10886.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>2.506614</td>
      <td>0.028569</td>
      <td>0.680875</td>
      <td>1.418427</td>
      <td>20.23086</td>
      <td>23.655084</td>
      <td>61.886460</td>
      <td>12.799395</td>
      <td>36.021955</td>
      <td>155.552177</td>
      <td>191.574132</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1.116174</td>
      <td>0.166599</td>
      <td>0.466159</td>
      <td>0.633839</td>
      <td>7.79159</td>
      <td>8.474601</td>
      <td>19.245033</td>
      <td>8.164537</td>
      <td>49.960477</td>
      <td>151.039033</td>
      <td>181.144454</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>0.82000</td>
      <td>0.760000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>13.94000</td>
      <td>16.665000</td>
      <td>47.000000</td>
      <td>7.001500</td>
      <td>4.000000</td>
      <td>36.000000</td>
      <td>42.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>3.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>20.50000</td>
      <td>24.240000</td>
      <td>62.000000</td>
      <td>12.998000</td>
      <td>17.000000</td>
      <td>118.000000</td>
      <td>145.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>4.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>2.000000</td>
      <td>26.24000</td>
      <td>31.060000</td>
      <td>77.000000</td>
      <td>16.997900</td>
      <td>49.000000</td>
      <td>222.000000</td>
      <td>284.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>4.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>4.000000</td>
      <td>41.00000</td>
      <td>45.455000</td>
      <td>100.000000</td>
      <td>56.996900</td>
      <td>367.000000</td>
      <td>886.000000</td>
      <td>977.000000</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Create the test pandas dataframe in pandas by reading the csv, remember to parse the datetime!</span>
<span class="n">test</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;test.csv&#39;</span><span class="p">)</span>
<span class="n">test</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span> <span class="s1">&#39;datetime&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">test</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span> <span class="s1">&#39;datetime&#39;</span><span class="p">])</span>

<span class="c1">#test[&#39;year&#39;] = pd.to_datetime(test.loc[:,&quot;datetime&quot;]).dt.year</span>
<span class="c1">#test[&#39;month&#39;]= pd.to_datetime(test.loc[:,&quot;datetime&quot;]).dt.month</span>
<span class="c1">#test[&#39;date&#39;]= pd.to_datetime(test.loc[:,&quot;datetime&quot;]).dt.day</span>
<span class="c1">#test[&#39;hour&#39;]= pd.to_datetime(test.loc[:,&quot;datetime&quot;]).dt.hour</span>
<span class="n">test</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[10]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>datetime</th>
      <th>season</th>
      <th>holiday</th>
      <th>workingday</th>
      <th>weather</th>
      <th>temp</th>
      <th>atemp</th>
      <th>humidity</th>
      <th>windspeed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2011-01-20 00:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>11.365</td>
      <td>56</td>
      <td>26.0027</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2011-01-20 01:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>0.0000</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2011-01-20 02:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>0.0000</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2011-01-20 03:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>56</td>
      <td>11.0014</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2011-01-20 04:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>56</td>
      <td>11.0014</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[11]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Same thing as train and test dataset</span>
<span class="n">submission</span> <span class="o">=</span>  <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;sampleSubmission.csv&#39;</span><span class="p">)</span>
<span class="n">submission</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span> <span class="s1">&#39;datetime&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">submission</span><span class="o">.</span><span class="n">loc</span><span class="p">[:,</span> <span class="s1">&#39;datetime&#39;</span><span class="p">])</span>
<span class="n">submission</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[11]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>datetime</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2011-01-20 00:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2011-01-20 01:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2011-01-20 02:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2011-01-20 03:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2011-01-20 04:00:00</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Step-3:-Train-a-model-using-AutoGluon&#8217;s-Tabular-Prediction">Step 3: Train a model using AutoGluon&#8217;s Tabular Prediction<a class="anchor-link" href="#Step-3:-Train-a-model-using-AutoGluon&#8217;s-Tabular-Prediction">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Requirements:</p>
<ul>
<li>We are prediting <code>count</code>, so it is the label we are setting.</li>
<li>Ignore <code>casual</code> and <code>registered</code> columns as they are also not present in the test dataset. </li>
<li>Use the <code>root_mean_squared_error</code> as the metric to use for evaluation.</li>
<li>Set a time limit of 10 minutes (600 seconds).</li>
<li>Use the preset <code>best_quality</code> to focus on creating the best model.</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[12]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">train_updated</span><span class="o">=</span> <span class="n">train</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;casual&#39;</span><span class="p">,</span> <span class="s1">&#39;registered&#39;</span><span class="p">],</span> <span class="n">axis</span> <span class="o">=</span> <span class="mi">1</span><span class="p">)</span>
<span class="n">predictor</span> <span class="o">=</span> <span class="n">TabularPredictor</span><span class="p">(</span>
    <span class="n">label</span><span class="o">=</span><span class="s2">&quot;count&quot;</span><span class="p">,</span> <span class="n">problem_type</span><span class="o">=</span><span class="s2">&quot;regression&quot;</span><span class="p">,</span> <span class="n">eval_metric</span><span class="o">=</span><span class="s2">&quot;root_mean_squared_error&quot;</span>
<span class="p">)</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span>
    <span class="n">train_data</span> <span class="o">=</span> <span class="n">train_updated</span><span class="p">,</span>
    <span class="n">time_limit</span><span class="o">=</span><span class="mi">600</span><span class="p">,</span>
    <span class="n">presets</span><span class="o">=</span><span class="s2">&quot;best_quality&quot;</span>
<span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>No path specified. Models will be saved in: &#34;AutogluonModels/ag-20220406_160327/&#34;
Presets specified: [&#39;best_quality&#39;]
Beginning AutoGluon training ... Time limit = 600s
AutoGluon will save models to &#34;AutogluonModels/ag-20220406_160327/&#34;
AutoGluon Version:  0.4.0
Python Version:     3.7.10
Operating System:   Linux
Train Data Rows:    10886
Train Data Columns: 9
Label Column: count
Preprocessing data ...
Using Feature Generators to preprocess the data ...
Fitting AutoMLPipelineFeatureGenerator...
	Available Memory:                    3048.7 MB
	Train Data (Original)  Memory Usage: 0.78 MB (0.0% of available memory)
	Inferring data type of each feature based on column values. Set feature_metadata_in to manually specify special dtypes of the features.
	Stage 1 Generators:
		Fitting AsTypeFeatureGenerator...
			Note: Converting 2 features to boolean dtype as they only contain 2 unique values.
	Stage 2 Generators:
		Fitting FillNaFeatureGenerator...
	Stage 3 Generators:
		Fitting IdentityFeatureGenerator...
		Fitting DatetimeFeatureGenerator...
	Stage 4 Generators:
		Fitting DropUniqueFeatureGenerator...
	Types of features in original data (raw dtype, special dtypes):
		(&#39;datetime&#39;, []) : 1 | [&#39;datetime&#39;]
		(&#39;float&#39;, [])    : 3 | [&#39;temp&#39;, &#39;atemp&#39;, &#39;windspeed&#39;]
		(&#39;int&#39;, [])      : 5 | [&#39;season&#39;, &#39;holiday&#39;, &#39;workingday&#39;, &#39;weather&#39;, &#39;humidity&#39;]
	Types of features in processed data (raw dtype, special dtypes):
		(&#39;float&#39;, [])                : 3 | [&#39;temp&#39;, &#39;atemp&#39;, &#39;windspeed&#39;]
		(&#39;int&#39;, [])                  : 3 | [&#39;season&#39;, &#39;weather&#39;, &#39;humidity&#39;]
		(&#39;int&#39;, [&#39;bool&#39;])            : 2 | [&#39;holiday&#39;, &#39;workingday&#39;]
		(&#39;int&#39;, [&#39;datetime_as_int&#39;]) : 5 | [&#39;datetime&#39;, &#39;datetime.year&#39;, &#39;datetime.month&#39;, &#39;datetime.day&#39;, &#39;datetime.dayofweek&#39;]
	0.3s = Fit runtime
	9 features in original data used to generate 13 features in processed data.
	Train Data (Processed) Memory Usage: 0.98 MB (0.0% of available memory)
Data preprocessing and feature engineering runtime = 0.34s ...
AutoGluon will gauge predictive performance using evaluation metric: &#39;root_mean_squared_error&#39;
	To change this, specify the eval_metric parameter of Predictor()
AutoGluon will fit 2 stack levels (L1 to L2) ...
Fitting 11 L1 models ...
Fitting model: KNeighborsUnif_BAG_L1 ... Training model for up to 399.67s of the 599.65s of remaining time.
	-101.5462	 = Validation score   (root_mean_squared_error)
	0.04s	 = Training   runtime
	0.1s	 = Validation runtime
Fitting model: KNeighborsDist_BAG_L1 ... Training model for up to 399.26s of the 599.24s of remaining time.
	-84.1251	 = Validation score   (root_mean_squared_error)
	0.03s	 = Training   runtime
	0.1s	 = Validation runtime
Fitting model: LightGBMXT_BAG_L1 ... Training model for up to 398.85s of the 598.83s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
2022-04-06 16:03:33,753	WARNING services.py:1758 -- WARNING: The object store is using /tmp instead of /dev/shm because /dev/shm has only 67108864 bytes available. This will harm performance! You may be able to free up space by deleting files in /dev/shm. If you are inside a Docker container, you can increase /dev/shm size by passing &#39;--shm-size=0.98gb&#39; to &#39;docker run&#39; (or add it to the run_options list in a Ray cluster config). Make sure to set this to more than 30% of available RAM.
	-131.4609	 = Validation score   (root_mean_squared_error)
	61.87s	 = Training   runtime
	7.29s	 = Validation runtime
Fitting model: LightGBM_BAG_L1 ... Training model for up to 325.2s of the 525.18s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-131.0542	 = Validation score   (root_mean_squared_error)
	26.67s	 = Training   runtime
	1.45s	 = Validation runtime
Fitting model: RandomForestMSE_BAG_L1 ... Training model for up to 295.4s of the 495.38s of remaining time.
	-116.6217	 = Validation score   (root_mean_squared_error)
	9.46s	 = Training   runtime
	0.43s	 = Validation runtime
Fitting model: CatBoost_BAG_L1 ... Training model for up to 282.73s of the 482.7s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-130.5183	 = Validation score   (root_mean_squared_error)
	204.72s	 = Training   runtime
	0.12s	 = Validation runtime
Fitting model: ExtraTreesMSE_BAG_L1 ... Training model for up to 74.4s of the 274.38s of remaining time.
	-124.6372	 = Validation score   (root_mean_squared_error)
	4.21s	 = Training   runtime
	0.43s	 = Validation runtime
Fitting model: NeuralNetFastAI_BAG_L1 ... Training model for up to 67.07s of the 267.05s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-137.1555	 = Validation score   (root_mean_squared_error)
	75.3s	 = Training   runtime
	0.39s	 = Validation runtime
Completed 1/20 k-fold bagging repeats ...
Fitting model: WeightedEnsemble_L2 ... Training model for up to 360.0s of the 187.77s of remaining time.
	-84.1251	 = Validation score   (root_mean_squared_error)
	0.67s	 = Training   runtime
	0.0s	 = Validation runtime
Fitting 9 L2 models ...
Fitting model: LightGBMXT_BAG_L2 ... Training model for up to 186.99s of the 186.97s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-60.41	 = Validation score   (root_mean_squared_error)
	51.85s	 = Training   runtime
	3.45s	 = Validation runtime
Fitting model: LightGBM_BAG_L2 ... Training model for up to 131.39s of the 131.37s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-55.0217	 = Validation score   (root_mean_squared_error)
	21.97s	 = Training   runtime
	0.22s	 = Validation runtime
Fitting model: RandomForestMSE_BAG_L2 ... Training model for up to 105.63s of the 105.61s of remaining time.
	-53.4627	 = Validation score   (root_mean_squared_error)
	25.35s	 = Training   runtime
	0.5s	 = Validation runtime
Fitting model: CatBoost_BAG_L2 ... Training model for up to 77.08s of the 77.06s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-55.4516	 = Validation score   (root_mean_squared_error)
	70.29s	 = Training   runtime
	0.07s	 = Validation runtime
Fitting model: ExtraTreesMSE_BAG_L2 ... Training model for up to 3.4s of the 3.38s of remaining time.
	-53.6395	 = Validation score   (root_mean_squared_error)
	7.15s	 = Training   runtime
	0.5s	 = Validation runtime
Completed 1/20 k-fold bagging repeats ...
Fitting model: WeightedEnsemble_L3 ... Training model for up to 360.0s of the -7.18s of remaining time.
	-52.7565	 = Validation score   (root_mean_squared_error)
	0.74s	 = Training   runtime
	0.0s	 = Validation runtime
AutoGluon training complete, total runtime = 608.19s ... Best model: &#34;WeightedEnsemble_L3&#34;
TabularPredictor saved. To load, use: predictor = TabularPredictor.load(&#34;AutogluonModels/ag-20220406_160327/&#34;)
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Review-AutoGluon's-training-run-with-ranking-of-models-that-did-the-best.">Review AutoGluon's training run with ranking of models that did the best.<a class="anchor-link" href="#Review-AutoGluon's-training-run-with-ranking-of-models-that-did-the-best.">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[13]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">predictor</span><span class="o">.</span><span class="n">leaderboard</span><span class="p">(</span><span class="n">silent</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">,</span> <span class="n">x</span> <span class="o">=</span> <span class="s1">&#39;model&#39;</span><span class="p">,</span> <span class="n">y</span> <span class="o">=</span> <span class="s1">&#39;score_val&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[13]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;AxesSubplot:xlabel=&#39;model&#39;&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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HcQGG2zA2LFjuf766wE488wz2XXXXdlmm23YdttteeGFF/joRz/KhAkTGDt2LBdd1HOSs0033ZQZM2bM3d9qq62YPHkyt99+O5ttthljx45l8803Z+bMmdmvg+M49aOr+vz7myuvvJK3vvWtXHZZGGt45plnGDt2LOeddx7jx4/n2WefZdiwYZx00klIYvr06dx3333ssMMO3H///QBMmTKFadOmMWLECI4++mi22WYbTj/9dJ5++mkmTJjAdtttx9JLL73AuffZZx/OP/98vv71r/P444/z+OOPM27cOJ599lluuukmhg4dyrXXXsvRRx/NBRdc0K/XxXGcwY+3/BPYYIMNuOaaazjyyCO56aabePjhh3nLW97C+PHjAVhuueUYOnQoN998MwcccAAA66yzDquuuupc57/99tszYsQIAK6++mpOOOEENt54Y7baaiteeuklHn744Y7n3nvvvfn9738PwPnnn8+ee+4JhAfQXnvtxfrrr8/nPve5+d4OHMdxWnjLP4G11lqLKVOmcPnll/PlL3+ZbbbZps8axVa9mXHBBRew9tprL/R3I0eOZMUVV2TatGmcd955/OxnPwPg2GOPZeutt+bCCy9k9uzZbLXVVn2uk+M43U9XOf/+nnL12GOPMWLECA444ACGDx/OKaecwuOPP86kSZMYP348zz33HMOGDWPLLbfk7LPPZptttuH+++/n4YcfZu2112bKlCnz6e24446cfPLJnHzyyUhi6tSpjB07tsfz77PPPpx44ok888wzbLjhhkBo+Y8cORIIYwqO4zid6Crn399Mnz6dL37xiyy22GIsvvjinHrqqZgZhx12GP/+978ZNmwY1157LZ/+9Kf51Kc+xQYbbMDQoUM588wzWXLJJRfQO/bYY/nsZz/LhhtuyOuvv86YMWO49NJLezz/nnvuyeGHH86xxx47t+yII47gwAMP5LjjjmPnnes5/9hxnEDOBq3MLJt4lYwbN84mT548X9m9997L29/+9gGqUffg19FxuhNJd5jZuE7HkgZ8Je0laYak1yUtcAJJoyU9L+l/CmU7SZopaZakL6Wc33EcxylHarfP3cAHgJ/3cPwHwBWtHUlDgJ8C2wNzgEmSLjazexLr0bVcddVVHHnkkfOVjRkzhgsvvHCAauQ4TjeQ5PzN7F7oHBlS0u7Ag8ALheIJwCwzeyB+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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[14]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">predictor</span><span class="o">.</span><span class="n">fit_summary</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>*** Summary of fit() ***
Estimated performance of each model:
                     model   score_val  pred_time_val    fit_time  pred_time_val_marginal  fit_time_marginal  stack_level  can_infer  fit_order
0      WeightedEnsemble_L3  -52.756529      11.611183  507.796664                0.001110           0.741333            3       True         15
1   RandomForestMSE_BAG_L2  -53.462706      10.822655  407.649460                0.495978          25.347389            2       True         12
2     ExtraTreesMSE_BAG_L2  -53.639497      10.823570  389.448018                0.496892           7.145947            2       True         14
3          LightGBM_BAG_L2  -55.021714      10.544282  404.269243                0.217604          21.967172            2       True         11
4          CatBoost_BAG_L2  -55.451555      10.399599  452.594824                0.072921          70.292753            2       True         13
5        LightGBMXT_BAG_L2  -60.410028      13.773225  434.147228                3.446548          51.845157            2       True         10
6    KNeighborsDist_BAG_L1  -84.125061       0.103631    0.031209                0.103631           0.031209            1       True          2
7      WeightedEnsemble_L2  -84.125061       0.104419    0.696553                0.000788           0.665344            2       True          9
8    KNeighborsUnif_BAG_L1 -101.546199       0.102858    0.035388                0.102858           0.035388            1       True          1
9   RandomForestMSE_BAG_L1 -116.621736       0.429818    9.459700                0.429818           9.459700            1       True          5
10    ExtraTreesMSE_BAG_L1 -124.637158       0.430937    4.211916                0.430937           4.211916            1       True          7
11         CatBoost_BAG_L1 -130.518258       0.124657  204.724337                0.124657         204.724337            1       True          6
12         LightGBM_BAG_L1 -131.054162       1.453156   26.674157                1.453156          26.674157            1       True          4
13       LightGBMXT_BAG_L1 -131.460909       7.291668   61.870079                7.291668          61.870079            1       True          3
14  NeuralNetFastAI_BAG_L1 -137.155528       0.389953   75.295285                0.389953          75.295285            1       True          8
Number of models trained: 15
Types of models trained:
{&#39;StackerEnsembleModel_NNFastAiTabular&#39;, &#39;StackerEnsembleModel_XT&#39;, &#39;WeightedEnsembleModel&#39;, &#39;StackerEnsembleModel_CatBoost&#39;, &#39;StackerEnsembleModel_LGB&#39;, &#39;StackerEnsembleModel_KNN&#39;, &#39;StackerEnsembleModel_RF&#39;}
Bagging used: True  (with 8 folds)
Multi-layer stack-ensembling used: True  (with 3 levels)
Feature Metadata (Processed):
(raw dtype, special dtypes):
(&#39;float&#39;, [])                : 3 | [&#39;temp&#39;, &#39;atemp&#39;, &#39;windspeed&#39;]
(&#39;int&#39;, [])                  : 3 | [&#39;season&#39;, &#39;weather&#39;, &#39;humidity&#39;]
(&#39;int&#39;, [&#39;bool&#39;])            : 2 | [&#39;holiday&#39;, &#39;workingday&#39;]
(&#39;int&#39;, [&#39;datetime_as_int&#39;]) : 5 | [&#39;datetime&#39;, &#39;datetime.year&#39;, &#39;datetime.month&#39;, &#39;datetime.day&#39;, &#39;datetime.dayofweek&#39;]
Plot summary of models saved to file: AutogluonModels/ag-20220406_160327/SummaryOfModels.html
*** End of fit() summary ***
</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[14]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>{&#39;model_types&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: &#39;StackerEnsembleModel_KNN&#39;,
  &#39;KNeighborsDist_BAG_L1&#39;: &#39;StackerEnsembleModel_KNN&#39;,
  &#39;LightGBMXT_BAG_L1&#39;: &#39;StackerEnsembleModel_LGB&#39;,
  &#39;LightGBM_BAG_L1&#39;: &#39;StackerEnsembleModel_LGB&#39;,
  &#39;RandomForestMSE_BAG_L1&#39;: &#39;StackerEnsembleModel_RF&#39;,
  &#39;CatBoost_BAG_L1&#39;: &#39;StackerEnsembleModel_CatBoost&#39;,
  &#39;ExtraTreesMSE_BAG_L1&#39;: &#39;StackerEnsembleModel_XT&#39;,
  &#39;NeuralNetFastAI_BAG_L1&#39;: &#39;StackerEnsembleModel_NNFastAiTabular&#39;,
  &#39;WeightedEnsemble_L2&#39;: &#39;WeightedEnsembleModel&#39;,
  &#39;LightGBMXT_BAG_L2&#39;: &#39;StackerEnsembleModel_LGB&#39;,
  &#39;LightGBM_BAG_L2&#39;: &#39;StackerEnsembleModel_LGB&#39;,
  &#39;RandomForestMSE_BAG_L2&#39;: &#39;StackerEnsembleModel_RF&#39;,
  &#39;CatBoost_BAG_L2&#39;: &#39;StackerEnsembleModel_CatBoost&#39;,
  &#39;ExtraTreesMSE_BAG_L2&#39;: &#39;StackerEnsembleModel_XT&#39;,
  &#39;WeightedEnsemble_L3&#39;: &#39;WeightedEnsembleModel&#39;},
 &#39;model_performance&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: -101.54619908446061,
  &#39;KNeighborsDist_BAG_L1&#39;: -84.12506123181602,
  &#39;LightGBMXT_BAG_L1&#39;: -131.46090891834504,
  &#39;LightGBM_BAG_L1&#39;: -131.054161598899,
  &#39;RandomForestMSE_BAG_L1&#39;: -116.62173601727898,
  &#39;CatBoost_BAG_L1&#39;: -130.51825769712914,
  &#39;ExtraTreesMSE_BAG_L1&#39;: -124.63715787314163,
  &#39;NeuralNetFastAI_BAG_L1&#39;: -137.15552768131909,
  &#39;WeightedEnsemble_L2&#39;: -84.12506123181602,
  &#39;LightGBMXT_BAG_L2&#39;: -60.41002822656081,
  &#39;LightGBM_BAG_L2&#39;: -55.02171376138084,
  &#39;RandomForestMSE_BAG_L2&#39;: -53.46270627583982,
  &#39;CatBoost_BAG_L2&#39;: -55.45155453776482,
  &#39;ExtraTreesMSE_BAG_L2&#39;: -53.639497320967585,
  &#39;WeightedEnsemble_L3&#39;: -52.756528550193295},
 &#39;model_best&#39;: &#39;WeightedEnsemble_L3&#39;,
 &#39;model_paths&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_160327/models/KNeighborsUnif_BAG_L1/&#39;,
  &#39;KNeighborsDist_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_160327/models/KNeighborsDist_BAG_L1/&#39;,
  &#39;LightGBMXT_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_160327/models/LightGBMXT_BAG_L1/&#39;,
  &#39;LightGBM_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_160327/models/LightGBM_BAG_L1/&#39;,
  &#39;RandomForestMSE_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_160327/models/RandomForestMSE_BAG_L1/&#39;,
  &#39;CatBoost_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_160327/models/CatBoost_BAG_L1/&#39;,
  &#39;ExtraTreesMSE_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_160327/models/ExtraTreesMSE_BAG_L1/&#39;,
  &#39;NeuralNetFastAI_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_160327/models/NeuralNetFastAI_BAG_L1/&#39;,
  &#39;WeightedEnsemble_L2&#39;: &#39;AutogluonModels/ag-20220406_160327/models/WeightedEnsemble_L2/&#39;,
  &#39;LightGBMXT_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_160327/models/LightGBMXT_BAG_L2/&#39;,
  &#39;LightGBM_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_160327/models/LightGBM_BAG_L2/&#39;,
  &#39;RandomForestMSE_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_160327/models/RandomForestMSE_BAG_L2/&#39;,
  &#39;CatBoost_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_160327/models/CatBoost_BAG_L2/&#39;,
  &#39;ExtraTreesMSE_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_160327/models/ExtraTreesMSE_BAG_L2/&#39;,
  &#39;WeightedEnsemble_L3&#39;: &#39;AutogluonModels/ag-20220406_160327/models/WeightedEnsemble_L3/&#39;},
 &#39;model_fit_times&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: 0.03538799285888672,
  &#39;KNeighborsDist_BAG_L1&#39;: 0.03120899200439453,
  &#39;LightGBMXT_BAG_L1&#39;: 61.870078563690186,
  &#39;LightGBM_BAG_L1&#39;: 26.67415738105774,
  &#39;RandomForestMSE_BAG_L1&#39;: 9.459700345993042,
  &#39;CatBoost_BAG_L1&#39;: 204.72433733940125,
  &#39;ExtraTreesMSE_BAG_L1&#39;: 4.211915969848633,
  &#39;NeuralNetFastAI_BAG_L1&#39;: 75.29528474807739,
  &#39;WeightedEnsemble_L2&#39;: 0.66534423828125,
  &#39;LightGBMXT_BAG_L2&#39;: 51.84515690803528,
  &#39;LightGBM_BAG_L2&#39;: 21.967171907424927,
  &#39;RandomForestMSE_BAG_L2&#39;: 25.347388744354248,
  &#39;CatBoost_BAG_L2&#39;: 70.29275250434875,
  &#39;ExtraTreesMSE_BAG_L2&#39;: 7.145946502685547,
  &#39;WeightedEnsemble_L3&#39;: 0.7413334846496582},
 &#39;model_pred_times&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: 0.10285758972167969,
  &#39;KNeighborsDist_BAG_L1&#39;: 0.10363078117370605,
  &#39;LightGBMXT_BAG_L1&#39;: 7.29166841506958,
  &#39;LightGBM_BAG_L1&#39;: 1.4531564712524414,
  &#39;RandomForestMSE_BAG_L1&#39;: 0.42981791496276855,
  &#39;CatBoost_BAG_L1&#39;: 0.12465715408325195,
  &#39;ExtraTreesMSE_BAG_L1&#39;: 0.4309365749359131,
  &#39;NeuralNetFastAI_BAG_L1&#39;: 0.3899526596069336,
  &#39;WeightedEnsemble_L2&#39;: 0.0007884502410888672,
  &#39;LightGBMXT_BAG_L2&#39;: 3.446547746658325,
  &#39;LightGBM_BAG_L2&#39;: 0.2176041603088379,
  &#39;RandomForestMSE_BAG_L2&#39;: 0.49597764015197754,
  &#39;CatBoost_BAG_L2&#39;: 0.0729212760925293,
  &#39;ExtraTreesMSE_BAG_L2&#39;: 0.49689221382141113,
  &#39;WeightedEnsemble_L3&#39;: 0.001110076904296875},
 &#39;num_bag_folds&#39;: 8,
 &#39;max_stack_level&#39;: 3,
 &#39;model_hyperparams&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;KNeighborsDist_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;LightGBMXT_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;LightGBM_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;RandomForestMSE_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;CatBoost_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;ExtraTreesMSE_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;NeuralNetFastAI_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;WeightedEnsemble_L2&#39;: {&#39;use_orig_features&#39;: False,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;LightGBMXT_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;LightGBM_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;RandomForestMSE_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;CatBoost_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;ExtraTreesMSE_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;WeightedEnsemble_L3&#39;: {&#39;use_orig_features&#39;: False,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True}},
 &#39;leaderboard&#39;:                      model   score_val  pred_time_val    fit_time  \
 0      WeightedEnsemble_L3  -52.756529      11.611183  507.796664   
 1   RandomForestMSE_BAG_L2  -53.462706      10.822655  407.649460   
 2     ExtraTreesMSE_BAG_L2  -53.639497      10.823570  389.448018   
 3          LightGBM_BAG_L2  -55.021714      10.544282  404.269243   
 4          CatBoost_BAG_L2  -55.451555      10.399599  452.594824   
 5        LightGBMXT_BAG_L2  -60.410028      13.773225  434.147228   
 6    KNeighborsDist_BAG_L1  -84.125061       0.103631    0.031209   
 7      WeightedEnsemble_L2  -84.125061       0.104419    0.696553   
 8    KNeighborsUnif_BAG_L1 -101.546199       0.102858    0.035388   
 9   RandomForestMSE_BAG_L1 -116.621736       0.429818    9.459700   
 10    ExtraTreesMSE_BAG_L1 -124.637158       0.430937    4.211916   
 11         CatBoost_BAG_L1 -130.518258       0.124657  204.724337   
 12         LightGBM_BAG_L1 -131.054162       1.453156   26.674157   
 13       LightGBMXT_BAG_L1 -131.460909       7.291668   61.870079   
 14  NeuralNetFastAI_BAG_L1 -137.155528       0.389953   75.295285   
 
     pred_time_val_marginal  fit_time_marginal  stack_level  can_infer  \
 0                 0.001110           0.741333            3       True   
 1                 0.495978          25.347389            2       True   
 2                 0.496892           7.145947            2       True   
 3                 0.217604          21.967172            2       True   
 4                 0.072921          70.292753            2       True   
 5                 3.446548          51.845157            2       True   
 6                 0.103631           0.031209            1       True   
 7                 0.000788           0.665344            2       True   
 8                 0.102858           0.035388            1       True   
 9                 0.429818           9.459700            1       True   
 10                0.430937           4.211916            1       True   
 11                0.124657         204.724337            1       True   
 12                1.453156          26.674157            1       True   
 13                7.291668          61.870079            1       True   
 14                0.389953          75.295285            1       True   
 
     fit_order  
 0          15  
 1          12  
 2          14  
 3          11  
 4          13  
 5          10  
 6           2  
 7           9  
 8           1  
 9           5  
 10          7  
 11          6  
 12          4  
 13          3  
 14          8  }</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Create-predictions-from-test-dataset">Create predictions from test dataset<a class="anchor-link" href="#Create-predictions-from-test-dataset">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[15]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#test_updated = test.drop([&quot;datetime&quot;], axis = 1)</span>
<span class="c1">#predictions = predictor.predict(test_updated)</span>
<span class="n">predictions</span> <span class="o">=</span> <span class="n">predictor</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">test</span><span class="p">)</span>
<span class="n">predictions</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[15]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>0    23.763222
1    41.620018
2    45.855522
3    48.996994
4    52.138283
Name: count, dtype: float32</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4 id="NOTE:-Kaggle-will-reject-the-submission-if-we-don't-set-everything-to-be-&gt;-0.">NOTE: Kaggle will reject the submission if we don't set everything to be &gt; 0.<a class="anchor-link" href="#NOTE:-Kaggle-will-reject-the-submission-if-we-don't-set-everything-to-be-&gt;-0.">&#182;</a></h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[16]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Describe the `predictions` series to see if there are any negative values</span>
<span class="n">predictions</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[16]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>count    6493.000000
mean      100.793816
std        90.438499
min         2.949378
25%        20.383324
50%        62.819935
75%       170.242981
max       363.760651
Name: count, dtype: float64</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[17]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># print(len(predictions))</span>
<span class="c1">#for items in predictions.iteritems():</span>
<span class="c1">#    print(items)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[18]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># How many negative values do we have?</span>
<span class="n">predictions</span><span class="o">.</span><span class="n">lt</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[18]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>False    6493
Name: count, dtype: int64</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[19]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Set them to zero</span>
<span class="n">predictions</span><span class="o">.</span><span class="n">iloc</span><span class="p">[</span><span class="n">predictions</span><span class="o">&lt;</span><span class="mi">0</span><span class="p">]</span> <span class="o">=</span> <span class="mi">0</span>
<span class="n">predictions</span><span class="o">.</span><span class="n">lt</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[19]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>False    6493
Name: count, dtype: int64</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Set-predictions-to-submission-dataframe,-save,-and-submit">Set predictions to submission dataframe, save, and submit<a class="anchor-link" href="#Set-predictions-to-submission-dataframe,-save,-and-submit">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[20]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">submission</span><span class="p">[</span><span class="s2">&quot;count&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">predictions</span>
<span class="n">submission</span><span class="o">.</span><span class="n">to_csv</span><span class="p">(</span><span class="s2">&quot;submission.csv&quot;</span><span class="p">,</span> <span class="n">index</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[21]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">!</span>kaggle competitions submit -c bike-sharing-demand -f submission.csv -m <span class="s2">&quot;first raw submission&quot;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>100%|█████████████████████████████████████████| 188k/188k [00:00&lt;00:00, 421kB/s]
Successfully submitted to Bike Sharing Demand</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4 id="View-submission-via-the-command-line-or-in-the-web-browser-under-the-competition's-page---My-Submissions">View submission via the command line or in the web browser under the competition's page - <code>My Submissions</code><a class="anchor-link" href="#View-submission-via-the-command-line-or-in-the-web-browser-under-the-competition's-page---My-Submissions">&#182;</a></h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[22]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">!</span>kaggle competitions submissions -c bike-sharing-demand <span class="p">|</span> tail -n +1 <span class="p">|</span> head -n <span class="m">6</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>fileName                     date                 description                        status    publicScore  privateScore  
---------------------------  -------------------  ---------------------------------  --------  -----------  ------------  
submission.csv               2022-04-06 16:14:59  first raw submission               complete  1.80645      1.80645       
submission_new_hpo.csv       2022-04-06 15:17:31  new features with hyperparameters  complete  0.47248      0.47248       
submission_new_features.csv  2022-04-06 14:57:16  new features                       complete  0.47063      0.47063       
submission.csv               2022-04-06 14:18:58  first raw submission               complete  1.80371      1.80371       
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4 id="Initial-score-of-1.806">Initial score of <code>1.806</code><a class="anchor-link" href="#Initial-score-of-1.806">&#182;</a></h4>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Step-4:-Exploratory-Data-Analysis-and-Creating-an-additional-feature">Step 4: Exploratory Data Analysis and Creating an additional feature<a class="anchor-link" href="#Step-4:-Exploratory-Data-Analysis-and-Creating-an-additional-feature">&#182;</a></h2><ul>
<li>Any additional feature will do, but a great suggestion would be to separate out the datetime into hour, day, or month parts.</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[23]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Create a histogram of all features to show the distribution of each one relative to the data. This is part of the exploritory data analysis</span>
<span class="n">train</span><span class="o">.</span><span class="n">hist</span><span class="p">(</span><span class="n">bins</span><span class="o">=</span><span class="mi">20</span><span class="p">,</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">20</span><span class="p">,</span><span class="mi">15</span><span class="p">))</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[24]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># create a new feature from train</span>
<span class="n">train</span><span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train</span><span class="p">[</span><span class="s1">&#39;datetime&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">year</span>
<span class="n">train</span><span class="p">[</span><span class="s1">&#39;month&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train</span><span class="p">[</span><span class="s1">&#39;datetime&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">month</span>
<span class="n">train</span><span class="p">[</span><span class="s1">&#39;day&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train</span><span class="p">[</span><span class="s1">&#39;datetime&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">day</span>
<span class="n">train</span><span class="p">[</span><span class="s1">&#39;hour&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train</span><span class="p">[</span><span class="s1">&#39;datetime&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">hour</span>
<span class="n">train</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;datetime&#39;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">train</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[24]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>season</th>
      <th>holiday</th>
      <th>workingday</th>
      <th>weather</th>
      <th>temp</th>
      <th>atemp</th>
      <th>humidity</th>
      <th>windspeed</th>
      <th>casual</th>
      <th>registered</th>
      <th>count</th>
      <th>year</th>
      <th>month</th>
      <th>day</th>
      <th>hour</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>81</td>
      <td>0.0</td>
      <td>3</td>
      <td>13</td>
      <td>16</td>
      <td>2011</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.02</td>
      <td>13.635</td>
      <td>80</td>
      <td>0.0</td>
      <td>8</td>
      <td>32</td>
      <td>40</td>
      <td>2011</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.02</td>
      <td>13.635</td>
      <td>80</td>
      <td>0.0</td>
      <td>5</td>
      <td>27</td>
      <td>32</td>
      <td>2011</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>75</td>
      <td>0.0</td>
      <td>3</td>
      <td>10</td>
      <td>13</td>
      <td>2011</td>
      <td>1</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>75</td>
      <td>0.0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>2011</td>
      <td>1</td>
      <td>1</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[25]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># create a new feature from test</span>
<span class="n">test</span><span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test</span><span class="p">[</span><span class="s1">&#39;datetime&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">year</span>
<span class="n">test</span><span class="p">[</span><span class="s1">&#39;month&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test</span><span class="p">[</span><span class="s1">&#39;datetime&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">month</span>
<span class="n">test</span><span class="p">[</span><span class="s1">&#39;day&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test</span><span class="p">[</span><span class="s1">&#39;datetime&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">day</span>
<span class="n">test</span><span class="p">[</span><span class="s1">&#39;hour&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test</span><span class="p">[</span><span class="s1">&#39;datetime&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">hour</span>
<span class="n">test</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;datetime&#39;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">test</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[25]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>season</th>
      <th>holiday</th>
      <th>workingday</th>
      <th>weather</th>
      <th>temp</th>
      <th>atemp</th>
      <th>humidity</th>
      <th>windspeed</th>
      <th>year</th>
      <th>month</th>
      <th>day</th>
      <th>hour</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>11.365</td>
      <td>56</td>
      <td>26.0027</td>
      <td>2011</td>
      <td>1</td>
      <td>20</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>0.0000</td>
      <td>2011</td>
      <td>1</td>
      <td>20</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>0.0000</td>
      <td>2011</td>
      <td>1</td>
      <td>20</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>56</td>
      <td>11.0014</td>
      <td>2011</td>
      <td>1</td>
      <td>20</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>56</td>
      <td>11.0014</td>
      <td>2011</td>
      <td>1</td>
      <td>20</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Make-category-types-for-these-so-models-know-they-are-not-just-numbers">Make category types for these so models know they are not just numbers<a class="anchor-link" href="#Make-category-types-for-these-so-models-know-they-are-not-just-numbers">&#182;</a></h2><ul>
<li>AutoGluon originally sees these as ints, but in reality they are int representations of a category.</li>
<li>Setting the dtype to category will classify these as categories in AutoGluon.</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[26]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">train</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;category&#39;</span><span class="p">)</span>
<span class="n">train</span><span class="p">[</span><span class="s1">&#39;weather&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train</span><span class="p">[</span><span class="s1">&#39;weather&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;category&#39;</span><span class="p">)</span>
<span class="n">test</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;category&#39;</span><span class="p">)</span>
<span class="n">test</span><span class="p">[</span><span class="s1">&#39;weather&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test</span><span class="p">[</span><span class="s1">&#39;weather&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;category&#39;</span><span class="p">)</span>

<span class="c1"># Convert the year/ month / day / hour to category</span>
<span class="n">train</span><span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train</span><span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;category&#39;</span><span class="p">)</span>
<span class="n">train</span><span class="p">[</span><span class="s1">&#39;month&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train</span><span class="p">[</span><span class="s1">&#39;month&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;category&#39;</span><span class="p">)</span>
<span class="n">train</span><span class="p">[</span><span class="s1">&#39;day&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train</span><span class="p">[</span><span class="s1">&#39;day&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;category&#39;</span><span class="p">)</span>
<span class="n">train</span><span class="p">[</span><span class="s1">&#39;hour&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train</span><span class="p">[</span><span class="s1">&#39;day&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;category&#39;</span><span class="p">)</span>
<span class="n">test</span><span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test</span><span class="p">[</span><span class="s1">&#39;year&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;category&#39;</span><span class="p">)</span>
<span class="n">test</span><span class="p">[</span><span class="s1">&#39;month&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test</span><span class="p">[</span><span class="s1">&#39;month&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;category&#39;</span><span class="p">)</span>
<span class="n">test</span><span class="p">[</span><span class="s1">&#39;day&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test</span><span class="p">[</span><span class="s1">&#39;day&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;category&#39;</span><span class="p">)</span>
<span class="n">test</span><span class="p">[</span><span class="s1">&#39;hour&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test</span><span class="p">[</span><span class="s1">&#39;day&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;category&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[27]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Inspect the datatype </span>
<span class="n">train</span><span class="o">.</span><span class="n">info</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>&lt;class &#39;pandas.core.frame.DataFrame&#39;&gt;
RangeIndex: 10886 entries, 0 to 10885
Data columns (total 15 columns):
 #   Column      Non-Null Count  Dtype   
---  ------      --------------  -----   
 0   season      10886 non-null  category
 1   holiday     10886 non-null  int64   
 2   workingday  10886 non-null  int64   
 3   weather     10886 non-null  category
 4   temp        10886 non-null  float64 
 5   atemp       10886 non-null  float64 
 6   humidity    10886 non-null  int64   
 7   windspeed   10886 non-null  float64 
 8   casual      10886 non-null  int64   
 9   registered  10886 non-null  int64   
 10  count       10886 non-null  int64   
 11  year        10886 non-null  category
 12  month       10886 non-null  category
 13  day         10886 non-null  category
 14  hour        10886 non-null  category
dtypes: category(6), float64(3), int64(6)
memory usage: 831.6 KB
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[28]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Inspect the datatype </span>
<span class="n">test</span><span class="o">.</span><span class="n">info</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>&lt;class &#39;pandas.core.frame.DataFrame&#39;&gt;
RangeIndex: 6493 entries, 0 to 6492
Data columns (total 12 columns):
 #   Column      Non-Null Count  Dtype   
---  ------      --------------  -----   
 0   season      6493 non-null   category
 1   holiday     6493 non-null   int64   
 2   workingday  6493 non-null   int64   
 3   weather     6493 non-null   category
 4   temp        6493 non-null   float64 
 5   atemp       6493 non-null   float64 
 6   humidity    6493 non-null   int64   
 7   windspeed   6493 non-null   float64 
 8   year        6493 non-null   category
 9   month       6493 non-null   category
 10  day         6493 non-null   category
 11  hour        6493 non-null   category
dtypes: category(6), float64(3), int64(3)
memory usage: 344.2 KB
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[29]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># View are new feature</span>
<span class="n">train</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[29]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>season</th>
      <th>holiday</th>
      <th>workingday</th>
      <th>weather</th>
      <th>temp</th>
      <th>atemp</th>
      <th>humidity</th>
      <th>windspeed</th>
      <th>casual</th>
      <th>registered</th>
      <th>count</th>
      <th>year</th>
      <th>month</th>
      <th>day</th>
      <th>hour</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>81</td>
      <td>0.0</td>
      <td>3</td>
      <td>13</td>
      <td>16</td>
      <td>2011</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.02</td>
      <td>13.635</td>
      <td>80</td>
      <td>0.0</td>
      <td>8</td>
      <td>32</td>
      <td>40</td>
      <td>2011</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.02</td>
      <td>13.635</td>
      <td>80</td>
      <td>0.0</td>
      <td>5</td>
      <td>27</td>
      <td>32</td>
      <td>2011</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>75</td>
      <td>0.0</td>
      <td>3</td>
      <td>10</td>
      <td>13</td>
      <td>2011</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>75</td>
      <td>0.0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>2011</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[30]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># View histogram of all features again now with the hour feature</span>
<span class="n">train</span><span class="o">.</span><span class="n">hist</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">20</span><span class="p">,</span><span class="mi">15</span><span class="p">))</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Step-5:-Rerun-the-model-with-the-same-settings-as-before,-just-with-more-features">Step 5: Rerun the model with the same settings as before, just with more features<a class="anchor-link" href="#Step-5:-Rerun-the-model-with-the-same-settings-as-before,-just-with-more-features">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[31]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">train_updated</span><span class="o">=</span> <span class="n">train</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;casual&#39;</span><span class="p">,</span> <span class="s1">&#39;registered&#39;</span><span class="p">],</span> <span class="n">axis</span> <span class="o">=</span> <span class="mi">1</span><span class="p">)</span>
<span class="n">predictor_new_features</span> <span class="o">=</span> <span class="n">TabularPredictor</span><span class="p">(</span>
    <span class="n">label</span><span class="o">=</span><span class="s2">&quot;count&quot;</span><span class="p">,</span> <span class="n">problem_type</span><span class="o">=</span><span class="s2">&quot;regression&quot;</span><span class="p">,</span> <span class="n">eval_metric</span><span class="o">=</span><span class="s2">&quot;root_mean_squared_error&quot;</span>
<span class="p">)</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span>
    <span class="n">train_data</span> <span class="o">=</span> <span class="n">train_updated</span><span class="p">,</span>
    <span class="n">time_limit</span><span class="o">=</span><span class="mi">600</span><span class="p">,</span>
    <span class="n">presets</span><span class="o">=</span><span class="s2">&quot;best_quality&quot;</span>
<span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>No path specified. Models will be saved in: &#34;AutogluonModels/ag-20220406_161831/&#34;
Presets specified: [&#39;best_quality&#39;]
Beginning AutoGluon training ... Time limit = 600s
AutoGluon will save models to &#34;AutogluonModels/ag-20220406_161831/&#34;
AutoGluon Version:  0.4.0
Python Version:     3.7.10
Operating System:   Linux
Train Data Rows:    10886
Train Data Columns: 12
Label Column: count
Preprocessing data ...
Using Feature Generators to preprocess the data ...
Fitting AutoMLPipelineFeatureGenerator...
	Available Memory:                    2116.69 MB
	Train Data (Original)  Memory Usage: 0.59 MB (0.0% of available memory)
	Inferring data type of each feature based on column values. Set feature_metadata_in to manually specify special dtypes of the features.
	Stage 1 Generators:
		Fitting AsTypeFeatureGenerator...
			Note: Converting 3 features to boolean dtype as they only contain 2 unique values.
	Stage 2 Generators:
		Fitting FillNaFeatureGenerator...
	Stage 3 Generators:
		Fitting IdentityFeatureGenerator...
		Fitting CategoryFeatureGenerator...
			Fitting CategoryMemoryMinimizeFeatureGenerator...
	Stage 4 Generators:
		Fitting DropUniqueFeatureGenerator...
	Types of features in original data (raw dtype, special dtypes):
		(&#39;category&#39;, []) : 6 | [&#39;season&#39;, &#39;weather&#39;, &#39;year&#39;, &#39;month&#39;, &#39;day&#39;, ...]
		(&#39;float&#39;, [])    : 3 | [&#39;temp&#39;, &#39;atemp&#39;, &#39;windspeed&#39;]
		(&#39;int&#39;, [])      : 3 | [&#39;holiday&#39;, &#39;workingday&#39;, &#39;humidity&#39;]
	Types of features in processed data (raw dtype, special dtypes):
		(&#39;category&#39;, [])  : 5 | [&#39;season&#39;, &#39;weather&#39;, &#39;month&#39;, &#39;day&#39;, &#39;hour&#39;]
		(&#39;float&#39;, [])     : 3 | [&#39;temp&#39;, &#39;atemp&#39;, &#39;windspeed&#39;]
		(&#39;int&#39;, [])       : 1 | [&#39;humidity&#39;]
		(&#39;int&#39;, [&#39;bool&#39;]) : 3 | [&#39;holiday&#39;, &#39;workingday&#39;, &#39;year&#39;]
	0.2s = Fit runtime
	12 features in original data used to generate 12 features in processed data.
	Train Data (Processed) Memory Usage: 0.44 MB (0.0% of available memory)
Data preprocessing and feature engineering runtime = 0.2s ...
AutoGluon will gauge predictive performance using evaluation metric: &#39;root_mean_squared_error&#39;
	To change this, specify the eval_metric parameter of Predictor()
AutoGluon will fit 2 stack levels (L1 to L2) ...
Fitting 11 L1 models ...
Fitting model: KNeighborsUnif_BAG_L1 ... Training model for up to 399.77s of the 599.79s of remaining time.
	-164.5576	 = Validation score   (root_mean_squared_error)
	0.09s	 = Training   runtime
	0.1s	 = Validation runtime
Fitting model: KNeighborsDist_BAG_L1 ... Training model for up to 399.25s of the 599.28s of remaining time.
	-179.0093	 = Validation score   (root_mean_squared_error)
	0.02s	 = Training   runtime
	0.1s	 = Validation runtime
Fitting model: LightGBMXT_BAG_L1 ... Training model for up to 398.88s of the 598.9s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-131.3643	 = Validation score   (root_mean_squared_error)
	56.14s	 = Training   runtime
	6.92s	 = Validation runtime
Fitting model: LightGBM_BAG_L1 ... Training model for up to 337.72s of the 537.74s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-132.024	 = Validation score   (root_mean_squared_error)
	25.38s	 = Training   runtime
	1.58s	 = Validation runtime
Fitting model: RandomForestMSE_BAG_L1 ... Training model for up to 309.17s of the 509.19s of remaining time.
	-131.5184	 = Validation score   (root_mean_squared_error)
	7.98s	 = Training   runtime
	0.45s	 = Validation runtime
Fitting model: CatBoost_BAG_L1 ... Training model for up to 298.16s of the 498.18s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-135.0409	 = Validation score   (root_mean_squared_error)
	244.4s	 = Training   runtime
	0.42s	 = Validation runtime
Fitting model: ExtraTreesMSE_BAG_L1 ... Training model for up to 50.32s of the 250.34s of remaining time.
	-129.8389	 = Validation score   (root_mean_squared_error)
	3.89s	 = Training   runtime
	0.45s	 = Validation runtime
Fitting model: NeuralNetFastAI_BAG_L1 ... Training model for up to 43.41s of the 243.43s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-136.5712	 = Validation score   (root_mean_squared_error)
	54.77s	 = Training   runtime
	0.43s	 = Validation runtime
Completed 1/20 k-fold bagging repeats ...
Fitting model: WeightedEnsemble_L2 ... Training model for up to 360.0s of the 185.01s of remaining time.
	-127.0029	 = Validation score   (root_mean_squared_error)
	1.0s	 = Training   runtime
	0.0s	 = Validation runtime
Fitting 9 L2 models ...
Fitting model: LightGBMXT_BAG_L2 ... Training model for up to 183.9s of the 183.88s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-126.883	 = Validation score   (root_mean_squared_error)
	19.49s	 = Training   runtime
	0.18s	 = Validation runtime
Fitting model: LightGBM_BAG_L2 ... Training model for up to 161.86s of the 161.84s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-127.0273	 = Validation score   (root_mean_squared_error)
	20.51s	 = Training   runtime
	0.16s	 = Validation runtime
Fitting model: RandomForestMSE_BAG_L2 ... Training model for up to 137.21s of the 137.19s of remaining time.
	-127.7583	 = Validation score   (root_mean_squared_error)
	28.6s	 = Training   runtime
	0.53s	 = Validation runtime
Fitting model: CatBoost_BAG_L2 ... Training model for up to 105.43s of the 105.41s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-126.3414	 = Validation score   (root_mean_squared_error)
	77.83s	 = Training   runtime
	0.17s	 = Validation runtime
Fitting model: ExtraTreesMSE_BAG_L2 ... Training model for up to 24.06s of the 24.04s of remaining time.
	-126.2244	 = Validation score   (root_mean_squared_error)
	7.06s	 = Training   runtime
	0.51s	 = Validation runtime
Fitting model: NeuralNetFastAI_BAG_L2 ... Training model for up to 13.69s of the 13.66s of remaining time.
	Fitting 8 child models (S1F1 - S1F8) | Fitting with ParallelLocalFoldFittingStrategy
	-127.5913	 = Validation score   (root_mean_squared_error)
	31.33s	 = Training   runtime
	0.57s	 = Validation runtime
Completed 1/20 k-fold bagging repeats ...
Fitting model: WeightedEnsemble_L3 ... Training model for up to 360.0s of the -21.49s of remaining time.
	-125.5492	 = Validation score   (root_mean_squared_error)
	0.62s	 = Training   runtime
	0.0s	 = Validation runtime
AutoGluon training complete, total runtime = 622.39s ... Best model: &#34;WeightedEnsemble_L3&#34;
TabularPredictor saved. To load, use: predictor = TabularPredictor.load(&#34;AutogluonModels/ag-20220406_161831/&#34;)
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[32]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">predictor_new_features</span><span class="o">.</span><span class="n">leaderboard</span><span class="p">(</span><span class="n">silent</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">,</span> <span class="n">x</span> <span class="o">=</span> <span class="s1">&#39;model&#39;</span><span class="p">,</span> <span class="n">y</span> <span class="o">=</span> <span class="s1">&#39;score_val&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[32]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;AxesSubplot:xlabel=&#39;model&#39;&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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pIr3HlC89tprDB48oD7EHMfpx1R68zeze81s1lL+7SDgt1Xu01954YUX2H333dlyyy3ZbLPNuOiii5g4cSLbbbcdW265JePGjWP+/Pm89NJLHHbYYWy++eaMHj2am266CYDzzjuPPffck5122omdd96ZF154gY9//OOMGzeO0aNHc9lll3V572222YaZM2cuPN5hhx2YNGkSd955J9tuuy2jR49mu+22Y9aspRWP4zh1pDdeNQ8APtgUdq6k14EJwMlmZq0ulHQ4cDjAyJEjs0ayDH/84x95y1vewlVXhb6GZ599ltGjR3PRRRcxduxYnnvuOYYOHcoZZ5yBJGbMmMF9993He97zHu6//34ApkyZwvTp01lttdU44YQT2GmnnTjnnHN45plnGDduHLvssgsrrLDCEvc+4IADuPjii/nGN77B3LlzmTt3LmPGjOG5557j1ltvZfDgwdxwww2ccMIJTJgwoVfzxXGc/s9S3/wl3SDp7hZbs0Fvde3bgf+Y2d2F4IPNbHNg+7gd2tX1ZjbezMaY2Zjhw4f3IDm9y+abb87111/Pcccdx6233spjjz3Gm9/8ZsaOHQvAyiuvzODBg7nttts45JBDANh4441ZZ511Fhr/XXfdldVWWw2A6667ju985ztstdVW7LDDDrz00ks89thjLe+9//778/vf/x6Aiy++mH333RcIP0D77bcfm222GV/4whcW+zpwHMdpsNQ3fzPbpYL+gcBvmvSeiH/nS7oQGAecX+EefcaGG27IlClTuPrqq/nKV77CTjvt1LZG8a3ezJgwYQIbbbTRUq8bMWIEq6++OtOnT+eiiy7iZz/7GQAnnXQSO+64I5dccgmzZ89mhx12aDtOjuMMfLI1+0haBtif8HbfCBsMDDOzpyQNAfYAbkh1z94emvnkk0+y2mqrccghhzBs2DB++tOfMnfuXCZOnMjYsWOZP38+Q4cOZfvtt+eCCy5gp5124v777+exxx5jo402YsqUKYvp7bbbbpx55pmceeaZSGLq1KmMHj26y/sfcMABnHbaaTz77LNsscUWQHjzHzFiBBD6FBzHcVpRyfhL2hs4ExgOXCVpmpntFk+/C3jczB4uXLIccG00/IMIhv8XVeLQl8yYMYMvfelLLLPMMgwZMoSzzjoLM+Ooo47ixRdfZOjQodxwww189rOf5TOf+Qybb745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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[33]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">predictor_new_features</span><span class="o">.</span><span class="n">fit_summary</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>*** Summary of fit() ***
Estimated performance of each model:
                     model   score_val  pred_time_val    fit_time  pred_time_val_marginal  fit_time_marginal  stack_level  can_infer  fit_order
0      WeightedEnsemble_L3 -125.549249      12.579924  578.095041                0.001142           0.618263            3       True         16
1     ExtraTreesMSE_BAG_L2 -126.224376      10.963675  399.734051                0.509020           7.064251            2       True         14
2          CatBoost_BAG_L2 -126.341428      10.625166  470.496004                0.170511          77.826205            2       True         13
3        LightGBMXT_BAG_L2 -126.882963      10.638863  412.154849                0.184208          19.485049            2       True         10
4      WeightedEnsemble_L2 -127.002890       8.667664  368.182854                0.000834           1.000991            2       True          9
5          LightGBM_BAG_L2 -127.027322      10.609968  413.177339                0.155313          20.507540            2       True         11
6   NeuralNetFastAI_BAG_L2 -127.591267      11.029107  423.995921                0.574452          31.326122            2       True         15
7   RandomForestMSE_BAG_L2 -127.758281      10.985277  421.267612                0.530622          28.597812            2       True         12
8     ExtraTreesMSE_BAG_L1 -129.838861       0.446793    3.892455                0.446793           3.892455            1       True          7
9        LightGBMXT_BAG_L1 -131.364280       6.924995   56.136920                6.924995          56.136920            1       True          3
10  RandomForestMSE_BAG_L1 -131.518418       0.447000    7.977908                0.447000           7.977908            1       True          5
11         LightGBM_BAG_L1 -132.023986       1.580334   25.376784                1.580334          25.376784            1       True          4
12         CatBoost_BAG_L1 -135.040950       0.420721  244.403494                0.420721         244.403494            1       True          6
13  NeuralNetFastAI_BAG_L1 -136.571169       0.427321   54.771086                0.427321          54.771086            1       True          8
14   KNeighborsUnif_BAG_L1 -164.557615       0.103014    0.093662                0.103014           0.093662            1       True          1
15   KNeighborsDist_BAG_L1 -179.009302       0.104477    0.017490                0.104477           0.017490            1       True          2
Number of models trained: 16
Types of models trained:
{&#39;StackerEnsembleModel_NNFastAiTabular&#39;, &#39;StackerEnsembleModel_XT&#39;, &#39;WeightedEnsembleModel&#39;, &#39;StackerEnsembleModel_CatBoost&#39;, &#39;StackerEnsembleModel_LGB&#39;, &#39;StackerEnsembleModel_KNN&#39;, &#39;StackerEnsembleModel_RF&#39;}
Bagging used: True  (with 8 folds)
Multi-layer stack-ensembling used: True  (with 3 levels)
Feature Metadata (Processed):
(raw dtype, special dtypes):
(&#39;category&#39;, [])  : 5 | [&#39;season&#39;, &#39;weather&#39;, &#39;month&#39;, &#39;day&#39;, &#39;hour&#39;]
(&#39;float&#39;, [])     : 3 | [&#39;temp&#39;, &#39;atemp&#39;, &#39;windspeed&#39;]
(&#39;int&#39;, [])       : 1 | [&#39;humidity&#39;]
(&#39;int&#39;, [&#39;bool&#39;]) : 3 | [&#39;holiday&#39;, &#39;workingday&#39;, &#39;year&#39;]
Plot summary of models saved to file: AutogluonModels/ag-20220406_161831/SummaryOfModels.html
*** End of fit() summary ***
</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[33]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>{&#39;model_types&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: &#39;StackerEnsembleModel_KNN&#39;,
  &#39;KNeighborsDist_BAG_L1&#39;: &#39;StackerEnsembleModel_KNN&#39;,
  &#39;LightGBMXT_BAG_L1&#39;: &#39;StackerEnsembleModel_LGB&#39;,
  &#39;LightGBM_BAG_L1&#39;: &#39;StackerEnsembleModel_LGB&#39;,
  &#39;RandomForestMSE_BAG_L1&#39;: &#39;StackerEnsembleModel_RF&#39;,
  &#39;CatBoost_BAG_L1&#39;: &#39;StackerEnsembleModel_CatBoost&#39;,
  &#39;ExtraTreesMSE_BAG_L1&#39;: &#39;StackerEnsembleModel_XT&#39;,
  &#39;NeuralNetFastAI_BAG_L1&#39;: &#39;StackerEnsembleModel_NNFastAiTabular&#39;,
  &#39;WeightedEnsemble_L2&#39;: &#39;WeightedEnsembleModel&#39;,
  &#39;LightGBMXT_BAG_L2&#39;: &#39;StackerEnsembleModel_LGB&#39;,
  &#39;LightGBM_BAG_L2&#39;: &#39;StackerEnsembleModel_LGB&#39;,
  &#39;RandomForestMSE_BAG_L2&#39;: &#39;StackerEnsembleModel_RF&#39;,
  &#39;CatBoost_BAG_L2&#39;: &#39;StackerEnsembleModel_CatBoost&#39;,
  &#39;ExtraTreesMSE_BAG_L2&#39;: &#39;StackerEnsembleModel_XT&#39;,
  &#39;NeuralNetFastAI_BAG_L2&#39;: &#39;StackerEnsembleModel_NNFastAiTabular&#39;,
  &#39;WeightedEnsemble_L3&#39;: &#39;WeightedEnsembleModel&#39;},
 &#39;model_performance&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: -164.55761532708044,
  &#39;KNeighborsDist_BAG_L1&#39;: -179.00930229155557,
  &#39;LightGBMXT_BAG_L1&#39;: -131.36428010836647,
  &#39;LightGBM_BAG_L1&#39;: -132.0239863139782,
  &#39;RandomForestMSE_BAG_L1&#39;: -131.5184179587791,
  &#39;CatBoost_BAG_L1&#39;: -135.04094986598034,
  &#39;ExtraTreesMSE_BAG_L1&#39;: -129.83886085889378,
  &#39;NeuralNetFastAI_BAG_L1&#39;: -136.57116928107604,
  &#39;WeightedEnsemble_L2&#39;: -127.00289024236629,
  &#39;LightGBMXT_BAG_L2&#39;: -126.88296316088866,
  &#39;LightGBM_BAG_L2&#39;: -127.02732173390828,
  &#39;RandomForestMSE_BAG_L2&#39;: -127.7582814458088,
  &#39;CatBoost_BAG_L2&#39;: -126.34142789538188,
  &#39;ExtraTreesMSE_BAG_L2&#39;: -126.22437555536484,
  &#39;NeuralNetFastAI_BAG_L2&#39;: -127.59126743897964,
  &#39;WeightedEnsemble_L3&#39;: -125.5492485032556},
 &#39;model_best&#39;: &#39;WeightedEnsemble_L3&#39;,
 &#39;model_paths&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_161831/models/KNeighborsUnif_BAG_L1/&#39;,
  &#39;KNeighborsDist_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_161831/models/KNeighborsDist_BAG_L1/&#39;,
  &#39;LightGBMXT_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_161831/models/LightGBMXT_BAG_L1/&#39;,
  &#39;LightGBM_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_161831/models/LightGBM_BAG_L1/&#39;,
  &#39;RandomForestMSE_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_161831/models/RandomForestMSE_BAG_L1/&#39;,
  &#39;CatBoost_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_161831/models/CatBoost_BAG_L1/&#39;,
  &#39;ExtraTreesMSE_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_161831/models/ExtraTreesMSE_BAG_L1/&#39;,
  &#39;NeuralNetFastAI_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_161831/models/NeuralNetFastAI_BAG_L1/&#39;,
  &#39;WeightedEnsemble_L2&#39;: &#39;AutogluonModels/ag-20220406_161831/models/WeightedEnsemble_L2/&#39;,
  &#39;LightGBMXT_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_161831/models/LightGBMXT_BAG_L2/&#39;,
  &#39;LightGBM_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_161831/models/LightGBM_BAG_L2/&#39;,
  &#39;RandomForestMSE_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_161831/models/RandomForestMSE_BAG_L2/&#39;,
  &#39;CatBoost_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_161831/models/CatBoost_BAG_L2/&#39;,
  &#39;ExtraTreesMSE_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_161831/models/ExtraTreesMSE_BAG_L2/&#39;,
  &#39;NeuralNetFastAI_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_161831/models/NeuralNetFastAI_BAG_L2/&#39;,
  &#39;WeightedEnsemble_L3&#39;: &#39;AutogluonModels/ag-20220406_161831/models/WeightedEnsemble_L3/&#39;},
 &#39;model_fit_times&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: 0.09366178512573242,
  &#39;KNeighborsDist_BAG_L1&#39;: 0.017490386962890625,
  &#39;LightGBMXT_BAG_L1&#39;: 56.13692021369934,
  &#39;LightGBM_BAG_L1&#39;: 25.376784324645996,
  &#39;RandomForestMSE_BAG_L1&#39;: 7.977908372879028,
  &#39;CatBoost_BAG_L1&#39;: 244.403493642807,
  &#39;ExtraTreesMSE_BAG_L1&#39;: 3.8924551010131836,
  &#39;NeuralNetFastAI_BAG_L1&#39;: 54.77108573913574,
  &#39;WeightedEnsemble_L2&#39;: 1.000990867614746,
  &#39;LightGBMXT_BAG_L2&#39;: 19.48504900932312,
  &#39;LightGBM_BAG_L2&#39;: 20.50753951072693,
  &#39;RandomForestMSE_BAG_L2&#39;: 28.597811937332153,
  &#39;CatBoost_BAG_L2&#39;: 77.82620477676392,
  &#39;ExtraTreesMSE_BAG_L2&#39;: 7.06425142288208,
  &#39;NeuralNetFastAI_BAG_L2&#39;: 31.32612180709839,
  &#39;WeightedEnsemble_L3&#39;: 0.618262767791748},
 &#39;model_pred_times&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: 0.10301446914672852,
  &#39;KNeighborsDist_BAG_L1&#39;: 0.1044766902923584,
  &#39;LightGBMXT_BAG_L1&#39;: 6.924994707107544,
  &#39;LightGBM_BAG_L1&#39;: 1.5803337097167969,
  &#39;RandomForestMSE_BAG_L1&#39;: 0.44699978828430176,
  &#39;CatBoost_BAG_L1&#39;: 0.42072129249572754,
  &#39;ExtraTreesMSE_BAG_L1&#39;: 0.4467926025390625,
  &#39;NeuralNetFastAI_BAG_L1&#39;: 0.4273214340209961,
  &#39;WeightedEnsemble_L2&#39;: 0.0008344650268554688,
  &#39;LightGBMXT_BAG_L2&#39;: 0.18420839309692383,
  &#39;LightGBM_BAG_L2&#39;: 0.15531325340270996,
  &#39;RandomForestMSE_BAG_L2&#39;: 0.5306224822998047,
  &#39;CatBoost_BAG_L2&#39;: 0.17051100730895996,
  &#39;ExtraTreesMSE_BAG_L2&#39;: 0.5090200901031494,
  &#39;NeuralNetFastAI_BAG_L2&#39;: 0.5744519233703613,
  &#39;WeightedEnsemble_L3&#39;: 0.0011420249938964844},
 &#39;num_bag_folds&#39;: 8,
 &#39;max_stack_level&#39;: 3,
 &#39;model_hyperparams&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;KNeighborsDist_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;LightGBMXT_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;LightGBM_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;RandomForestMSE_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;CatBoost_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;ExtraTreesMSE_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;NeuralNetFastAI_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;WeightedEnsemble_L2&#39;: {&#39;use_orig_features&#39;: False,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;LightGBMXT_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;LightGBM_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;RandomForestMSE_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;CatBoost_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;ExtraTreesMSE_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;NeuralNetFastAI_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;WeightedEnsemble_L3&#39;: {&#39;use_orig_features&#39;: False,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True}},
 &#39;leaderboard&#39;:                      model   score_val  pred_time_val    fit_time  \
 0      WeightedEnsemble_L3 -125.549249      12.579924  578.095041   
 1     ExtraTreesMSE_BAG_L2 -126.224376      10.963675  399.734051   
 2          CatBoost_BAG_L2 -126.341428      10.625166  470.496004   
 3        LightGBMXT_BAG_L2 -126.882963      10.638863  412.154849   
 4      WeightedEnsemble_L2 -127.002890       8.667664  368.182854   
 5          LightGBM_BAG_L2 -127.027322      10.609968  413.177339   
 6   NeuralNetFastAI_BAG_L2 -127.591267      11.029107  423.995921   
 7   RandomForestMSE_BAG_L2 -127.758281      10.985277  421.267612   
 8     ExtraTreesMSE_BAG_L1 -129.838861       0.446793    3.892455   
 9        LightGBMXT_BAG_L1 -131.364280       6.924995   56.136920   
 10  RandomForestMSE_BAG_L1 -131.518418       0.447000    7.977908   
 11         LightGBM_BAG_L1 -132.023986       1.580334   25.376784   
 12         CatBoost_BAG_L1 -135.040950       0.420721  244.403494   
 13  NeuralNetFastAI_BAG_L1 -136.571169       0.427321   54.771086   
 14   KNeighborsUnif_BAG_L1 -164.557615       0.103014    0.093662   
 15   KNeighborsDist_BAG_L1 -179.009302       0.104477    0.017490   
 
     pred_time_val_marginal  fit_time_marginal  stack_level  can_infer  \
 0                 0.001142           0.618263            3       True   
 1                 0.509020           7.064251            2       True   
 2                 0.170511          77.826205            2       True   
 3                 0.184208          19.485049            2       True   
 4                 0.000834           1.000991            2       True   
 5                 0.155313          20.507540            2       True   
 6                 0.574452          31.326122            2       True   
 7                 0.530622          28.597812            2       True   
 8                 0.446793           3.892455            1       True   
 9                 6.924995          56.136920            1       True   
 10                0.447000           7.977908            1       True   
 11                1.580334          25.376784            1       True   
 12                0.420721         244.403494            1       True   
 13                0.427321          54.771086            1       True   
 14                0.103014           0.093662            1       True   
 15                0.104477           0.017490            1       True   
 
     fit_order  
 0          16  
 1          14  
 2          13  
 3          10  
 4           9  
 5          11  
 6          15  
 7          12  
 8           7  
 9           3  
 10          5  
 11          4  
 12          6  
 13          8  
 14          1  
 15          2  }</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[34]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Remember to set all negative values to zero</span>
<span class="n">predictions_new_features</span> <span class="o">=</span> <span class="n">predictor_new_features</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">test</span><span class="p">)</span>
<span class="n">predictions_new_features</span><span class="o">.</span><span class="n">iloc</span><span class="p">[</span><span class="n">predictions_new_features</span><span class="o">&lt;</span><span class="mi">0</span><span class="p">]</span> <span class="o">=</span> <span class="mi">0</span>
<span class="n">predictions_new_features</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[34]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>0    81.573090
1    74.948402
2    74.948402
3    80.359009
4    80.359009
Name: count, dtype: float32</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[35]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Same submitting predictions</span>
<span class="n">submission_new_features</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;./sampleSubmission.csv&#39;</span><span class="p">,</span> <span class="n">parse_dates</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;datetime&quot;</span><span class="p">])</span>
<span class="n">submission_new_features</span><span class="p">[</span><span class="s2">&quot;count&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">predictions_new_features</span>
<span class="n">submission_new_features</span><span class="o">.</span><span class="n">to_csv</span><span class="p">(</span><span class="s2">&quot;submission_new_features.csv&quot;</span><span class="p">,</span> <span class="n">index</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[36]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">!</span>kaggle competitions submit -c bike-sharing-demand -f submission_new_features.csv -m <span class="s2">&quot;new features&quot;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>100%|█████████████████████████████████████████| 189k/189k [00:00&lt;00:00, 403kB/s]
Successfully submitted to Bike Sharing Demand</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[37]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">!</span>kaggle competitions submissions -c bike-sharing-demand <span class="p">|</span> tail -n +1 <span class="p">|</span> head -n <span class="m">6</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>fileName                     date                 description                        status    publicScore  privateScore  
---------------------------  -------------------  ---------------------------------  --------  -----------  ------------  
submission_new_features.csv  2022-04-06 16:29:22  new features                       complete  1.31956      1.31956       
submission.csv               2022-04-06 16:14:59  first raw submission               complete  1.80645      1.80645       
submission_new_hpo.csv       2022-04-06 15:17:31  new features with hyperparameters  complete  0.47248      0.47248       
submission_new_features.csv  2022-04-06 14:57:16  new features                       complete  0.47063      0.47063       
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4 id="New-Score-of-1.319">New Score of <code>1.319</code><a class="anchor-link" href="#New-Score-of-1.319">&#182;</a></h4>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Step-6:-Hyper-parameter-optimization">Step 6: Hyper parameter optimization<a class="anchor-link" href="#Step-6:-Hyper-parameter-optimization">&#182;</a></h2><ul>
<li>There are many options for hyper parameter optimization.</li>
<li>Options are to change the AutoGluon higher level parameters or the individual model hyperparameters.</li>
<li>The hyperparameters of the models themselves that are in AutoGluon. Those need the <code>hyperparameter</code> and <code>hyperparameter_tune_kwargs</code> arguments.</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[38]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">train_updated</span><span class="o">=</span> <span class="n">train</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;casual&#39;</span><span class="p">,</span> <span class="s1">&#39;registered&#39;</span><span class="p">],</span> <span class="n">axis</span> <span class="o">=</span> <span class="mi">1</span><span class="p">)</span>
<span class="n">predictor_new_hpo</span> <span class="o">=</span> <span class="n">TabularPredictor</span><span class="p">(</span>
    <span class="n">label</span><span class="o">=</span><span class="s1">&#39;count&#39;</span><span class="p">,</span> <span class="n">problem_type</span><span class="o">=</span><span class="s1">&#39;regression&#39;</span><span class="p">,</span> <span class="n">eval_metric</span><span class="o">=</span><span class="s1">&#39;root_mean_squared_error&#39;</span>
<span class="p">)</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span>
    <span class="n">train_data</span> <span class="o">=</span> <span class="n">train_updated</span><span class="p">,</span>
    <span class="n">time_limit</span><span class="o">=</span><span class="mi">600</span><span class="p">,</span>
    <span class="n">num_bag_folds</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span>
    <span class="n">num_bag_sets</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
    <span class="n">num_stack_levels</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
    <span class="n">presets</span><span class="o">=</span><span class="s1">&#39;best_quality&#39;</span>
<span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>No path specified. Models will be saved in: &#34;AutogluonModels/ag-20220406_163254/&#34;
Presets specified: [&#39;best_quality&#39;]
Beginning AutoGluon training ... Time limit = 600s
AutoGluon will save models to &#34;AutogluonModels/ag-20220406_163254/&#34;
AutoGluon Version:  0.4.0
Python Version:     3.7.10
Operating System:   Linux
Train Data Rows:    10886
Train Data Columns: 12
Label Column: count
Preprocessing data ...
Using Feature Generators to preprocess the data ...
Fitting AutoMLPipelineFeatureGenerator...
	Available Memory:                    2180.95 MB
	Train Data (Original)  Memory Usage: 0.59 MB (0.0% of available memory)
	Inferring data type of each feature based on column values. Set feature_metadata_in to manually specify special dtypes of the features.
	Stage 1 Generators:
		Fitting AsTypeFeatureGenerator...
			Note: Converting 3 features to boolean dtype as they only contain 2 unique values.
	Stage 2 Generators:
		Fitting FillNaFeatureGenerator...
	Stage 3 Generators:
		Fitting IdentityFeatureGenerator...
		Fitting CategoryFeatureGenerator...
			Fitting CategoryMemoryMinimizeFeatureGenerator...
	Stage 4 Generators:
		Fitting DropUniqueFeatureGenerator...
	Types of features in original data (raw dtype, special dtypes):
		(&#39;category&#39;, []) : 6 | [&#39;season&#39;, &#39;weather&#39;, &#39;year&#39;, &#39;month&#39;, &#39;day&#39;, ...]
		(&#39;float&#39;, [])    : 3 | [&#39;temp&#39;, &#39;atemp&#39;, &#39;windspeed&#39;]
		(&#39;int&#39;, [])      : 3 | [&#39;holiday&#39;, &#39;workingday&#39;, &#39;humidity&#39;]
	Types of features in processed data (raw dtype, special dtypes):
		(&#39;category&#39;, [])  : 5 | [&#39;season&#39;, &#39;weather&#39;, &#39;month&#39;, &#39;day&#39;, &#39;hour&#39;]
		(&#39;float&#39;, [])     : 3 | [&#39;temp&#39;, &#39;atemp&#39;, &#39;windspeed&#39;]
		(&#39;int&#39;, [])       : 1 | [&#39;humidity&#39;]
		(&#39;int&#39;, [&#39;bool&#39;]) : 3 | [&#39;holiday&#39;, &#39;workingday&#39;, &#39;year&#39;]
	0.2s = Fit runtime
	12 features in original data used to generate 12 features in processed data.
	Train Data (Processed) Memory Usage: 0.44 MB (0.0% of available memory)
Data preprocessing and feature engineering runtime = 0.26s ...
AutoGluon will gauge predictive performance using evaluation metric: &#39;root_mean_squared_error&#39;
	To change this, specify the eval_metric parameter of Predictor()
AutoGluon will fit 2 stack levels (L1 to L2) ...
Fitting 11 L1 models ...
Fitting model: KNeighborsUnif_BAG_L1 ... Training model for up to 399.72s of the 599.72s of remaining time.
	-164.5576	 = Validation score   (root_mean_squared_error)
	0.04s	 = Training   runtime
	0.11s	 = Validation runtime
Fitting model: KNeighborsDist_BAG_L1 ... Training model for up to 399.3s of the 599.31s of remaining time.
	-179.0093	 = Validation score   (root_mean_squared_error)
	0.02s	 = Training   runtime
	0.1s	 = Validation runtime
Fitting model: LightGBMXT_BAG_L1 ... Training model for up to 398.92s of the 598.92s of remaining time.
	Fitting 5 child models (S1F1 - S1F5) | Fitting with ParallelLocalFoldFittingStrategy
	-132.2356	 = Validation score   (root_mean_squared_error)
	22.04s	 = Training   runtime
	2.8s	 = Validation runtime
Fitting model: LightGBM_BAG_L1 ... Training model for up to 373.31s of the 573.31s of remaining time.
	Fitting 5 child models (S1F1 - S1F5) | Fitting with ParallelLocalFoldFittingStrategy
	-133.1379	 = Validation score   (root_mean_squared_error)
	15.19s	 = Training   runtime
	1.22s	 = Validation runtime
Fitting model: RandomForestMSE_BAG_L1 ... Training model for up to 355.1s of the 555.1s of remaining time.
	-131.5184	 = Validation score   (root_mean_squared_error)
	7.74s	 = Training   runtime
	0.44s	 = Validation runtime
Fitting model: CatBoost_BAG_L1 ... Training model for up to 344.31s of the 544.31s of remaining time.
	Fitting 5 child models (S1F1 - S1F5) | Fitting with ParallelLocalFoldFittingStrategy
	-134.9171	 = Validation score   (root_mean_squared_error)
	260.82s	 = Training   runtime
	0.45s	 = Validation runtime
Fitting model: ExtraTreesMSE_BAG_L1 ... Training model for up to 80.7s of the 280.7s of remaining time.
	-129.8389	 = Validation score   (root_mean_squared_error)
	4.02s	 = Training   runtime
	0.43s	 = Validation runtime
Fitting model: NeuralNetFastAI_BAG_L1 ... Training model for up to 73.7s of the 273.7s of remaining time.
	Fitting 5 child models (S1F1 - S1F5) | Fitting with ParallelLocalFoldFittingStrategy
	-134.4384	 = Validation score   (root_mean_squared_error)
	62.17s	 = Training   runtime
	0.35s	 = Validation runtime
Fitting model: XGBoost_BAG_L1 ... Training model for up to 8.65s of the 208.66s of remaining time.
	Fitting 5 child models (S1F1 - S1F5) | Fitting with ParallelLocalFoldFittingStrategy
	-134.0351	 = Validation score   (root_mean_squared_error)
	11.17s	 = Training   runtime
	0.18s	 = Validation runtime
Fitting model: WeightedEnsemble_L2 ... Training model for up to 360.0s of the 194.47s of remaining time.
	-127.416	 = Validation score   (root_mean_squared_error)
	0.71s	 = Training   runtime
	0.0s	 = Validation runtime
Fitting 9 L2 models ...
Fitting model: LightGBMXT_BAG_L2 ... Training model for up to 193.63s of the 193.61s of remaining time.
	Fitting 5 child models (S1F1 - S1F5) | Fitting with ParallelLocalFoldFittingStrategy
	-127.495	 = Validation score   (root_mean_squared_error)
	12.1s	 = Training   runtime
	0.16s	 = Validation runtime
Fitting model: LightGBM_BAG_L2 ... Training model for up to 178.95s of the 178.93s of remaining time.
	Fitting 5 child models (S1F1 - S1F5) | Fitting with ParallelLocalFoldFittingStrategy
	-127.8354	 = Validation score   (root_mean_squared_error)
	12.97s	 = Training   runtime
	0.12s	 = Validation runtime
Fitting model: RandomForestMSE_BAG_L2 ... Training model for up to 163.28s of the 163.25s of remaining time.
	-129.0028	 = Validation score   (root_mean_squared_error)
	31.51s	 = Training   runtime
	0.54s	 = Validation runtime
Fitting model: CatBoost_BAG_L2 ... Training model for up to 128.54s of the 128.51s of remaining time.
	Fitting 5 child models (S1F1 - S1F5) | Fitting with ParallelLocalFoldFittingStrategy
	-126.9299	 = Validation score   (root_mean_squared_error)
	46.01s	 = Training   runtime
	0.14s	 = Validation runtime
Fitting model: ExtraTreesMSE_BAG_L2 ... Training model for up to 79.83s of the 79.81s of remaining time.
	-126.7581	 = Validation score   (root_mean_squared_error)
	7.53s	 = Training   runtime
	0.51s	 = Validation runtime
Fitting model: NeuralNetFastAI_BAG_L2 ... Training model for up to 69.03s of the 69.01s of remaining time.
	Fitting 5 child models (S1F1 - S1F5) | Fitting with ParallelLocalFoldFittingStrategy
	-127.5938	 = Validation score   (root_mean_squared_error)
	58.27s	 = Training   runtime
	0.45s	 = Validation runtime
Fitting model: XGBoost_BAG_L2 ... Training model for up to 7.14s of the 7.11s of remaining time.
	Fitting 5 child models (S1F1 - S1F5) | Fitting with ParallelLocalFoldFittingStrategy
	-128.1077	 = Validation score   (root_mean_squared_error)
	11.04s	 = Training   runtime
	0.1s	 = Validation runtime
Fitting model: WeightedEnsemble_L3 ... Training model for up to 360.0s of the -6.95s of remaining time.
	-126.0245	 = Validation score   (root_mean_squared_error)
	0.58s	 = Training   runtime
	0.0s	 = Validation runtime
AutoGluon training complete, total runtime = 607.8s ... Best model: &#34;WeightedEnsemble_L3&#34;
TabularPredictor saved. To load, use: predictor = TabularPredictor.load(&#34;AutogluonModels/ag-20220406_163254/&#34;)
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[39]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">predictor_new_hpo</span><span class="o">.</span><span class="n">leaderboard</span><span class="p">(</span><span class="n">silent</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">,</span> <span class="n">x</span> <span class="o">=</span> <span class="s1">&#39;model&#39;</span><span class="p">,</span> <span class="n">y</span> <span class="o">=</span> <span class="s1">&#39;score_val&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[39]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;AxesSubplot:xlabel=&#39;model&#39;&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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aTx3naTZhXMrt5kHpwWuu+46dt11126r4ThORWj3yf9OYE/g58VEMzsLOAtA0kbA+WY2vfCV/c1sSpu/PaR45ZVXGD58SL2IOY5TYdp68jezu81sdj9f2w/4XTu/U1VeeOEFdtllFzbZZBM23HBDzjnnHG677Ta22GILNtlkEyZOnMjzzz/Piy++yEEHHcRGG23EuHHjuPbaawE444wz2G233dh2223ZbrvteOGFF/jwhz/MxIkTGTduHBdccEGvv7355psza9as14633nprpkyZwq233srb3vY2xo0bxxZbbMHs2f0Vj+M4dWQgHjX3Bd7bI+10Sa8Ck4HjzcyaXSjpYOBggNVWW62jSpbh8ssv501vehOXXBL6Gp599lnGjRvHOeecw4QJE3juuecYOXIkJ510EpKYOXMm99xzDzvuuCP33nsvAFOnTmXGjBmssMIKHH300Wy77bacdtppPPPMM0ycOJHtt9+epZZaapHf3nfffTn33HP56le/yty5c5k7dy7jx4/nueee48Ybb2T48OFcffXVHH300UyePHlA74vjONWn3yd/SVdLurPJ1tOhN7v2rcC/zezOQvL+ZrYRsGXcDuztejObZGbjzWz86NGjW8jOwLLRRhtx1VVXceSRR3LjjTfy6KOP8sY3vpEJEyYAsOyyyzJ8+HBuuukmDjjgAADWW289Vl999dec/w477MAKK6wAwJVXXsm3vvUtNt10U7beemtefPFFHn300aa/vc8++/CHP/wBgHPPPZe99toLCH9Ae++9NxtuuCGf/exnF3o7cBzHadDvk7+Zbd+G/PcBv+0h7/H4+byks4GJwJlt/EbXWGeddZg6dSqXXnopX/rSl9h2222TZRSf6s2MyZMns+666/Z73SqrrMKKK67IjBkzOOecc/jZz34GwLHHHss222zDeeedx8MPP8zWW2+drJPjOEOfjjX7SFoM2IfwdN9IGw6MMrOnJI0AdgWuzvWbAz0084knnmCFFVbggAMOYNSoUfz0pz9l7ty53HbbbUyYMIHnn3+ekSNHsuWWW3LWWWex7bbbcu+99/Loo4+y7rrrMnXq1IXk7bTTTpx88smcfPLJSGLatGmMGzeu19/fd999OfHEE3n22WfZeOONgfDkv8oqqwChT8FxHKcZbTl/SXsAJwOjgUskTTezneLprYDHzOzBwiVLAFdE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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[40]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">predictor_new_hpo</span><span class="o">.</span><span class="n">fit_summary</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>*** Summary of fit() ***
Estimated performance of each model:
                     model   score_val  pred_time_val    fit_time  pred_time_val_marginal  fit_time_marginal  stack_level  can_infer  fit_order
0      WeightedEnsemble_L3 -126.024454       7.287316  506.642303                0.000840           0.577709            3       True         18
1     ExtraTreesMSE_BAG_L2 -126.758064       6.592508  390.742841                0.512512           7.531238            2       True         15
2          CatBoost_BAG_L2 -126.929862       6.222085  429.224041                0.142090          46.012437            2       True         14
3      WeightedEnsemble_L2 -127.416046       4.472858  357.513214                0.001343           0.714263            2       True         10
4        LightGBMXT_BAG_L2 -127.495030       6.235814  395.314057                0.155818          12.102453            2       True         11
5   NeuralNetFastAI_BAG_L2 -127.593820       6.533052  441.482420                0.453056          58.270816            2       True         16
6          LightGBM_BAG_L2 -127.835382       6.204650  396.178436                0.124655          12.966832            2       True         12
7           XGBoost_BAG_L2 -128.107689       6.178818  394.250103                0.098823          11.038499            2       True         17
8   RandomForestMSE_BAG_L2 -129.002787       6.619954  414.724845                0.539958          31.513241            2       True         13
9     ExtraTreesMSE_BAG_L1 -129.838861       0.430477    4.023007                0.430477           4.023007            1       True          7
10  RandomForestMSE_BAG_L1 -131.518418       0.439047    7.743191                0.439047           7.743191            1       True          5
11       LightGBMXT_BAG_L1 -132.235580       2.802750   22.037296                2.802750          22.037296            1       True          3
12         LightGBM_BAG_L1 -133.137872       1.215981   15.188118                1.215981          15.188118            1       True          4
13          XGBoost_BAG_L1 -134.035131       0.179951   11.167985                0.179951          11.167985            1       True          9
14  NeuralNetFastAI_BAG_L1 -134.438397       0.351665   62.171011                0.351665          62.171011            1       True          8
15         CatBoost_BAG_L1 -134.917111       0.447576  260.824446                0.447576         260.824446            1       True          6
16   KNeighborsUnif_BAG_L1 -164.557615       0.107866    0.038385                0.107866           0.038385            1       True          1
17   KNeighborsDist_BAG_L1 -179.009302       0.104683    0.018164                0.104683           0.018164            1       True          2
Number of models trained: 18
Types of models trained:
{&#39;StackerEnsembleModel_NNFastAiTabular&#39;, &#39;StackerEnsembleModel_XT&#39;, &#39;StackerEnsembleModel_XGBoost&#39;, &#39;WeightedEnsembleModel&#39;, &#39;StackerEnsembleModel_CatBoost&#39;, &#39;StackerEnsembleModel_LGB&#39;, &#39;StackerEnsembleModel_KNN&#39;, &#39;StackerEnsembleModel_RF&#39;}
Bagging used: True  (with 5 folds)
Multi-layer stack-ensembling used: True  (with 3 levels)
Feature Metadata (Processed):
(raw dtype, special dtypes):
(&#39;category&#39;, [])  : 5 | [&#39;season&#39;, &#39;weather&#39;, &#39;month&#39;, &#39;day&#39;, &#39;hour&#39;]
(&#39;float&#39;, [])     : 3 | [&#39;temp&#39;, &#39;atemp&#39;, &#39;windspeed&#39;]
(&#39;int&#39;, [])       : 1 | [&#39;humidity&#39;]
(&#39;int&#39;, [&#39;bool&#39;]) : 3 | [&#39;holiday&#39;, &#39;workingday&#39;, &#39;year&#39;]
Plot summary of models saved to file: AutogluonModels/ag-20220406_163254/SummaryOfModels.html
*** End of fit() summary ***
</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt output_prompt">Out[40]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>{&#39;model_types&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: &#39;StackerEnsembleModel_KNN&#39;,
  &#39;KNeighborsDist_BAG_L1&#39;: &#39;StackerEnsembleModel_KNN&#39;,
  &#39;LightGBMXT_BAG_L1&#39;: &#39;StackerEnsembleModel_LGB&#39;,
  &#39;LightGBM_BAG_L1&#39;: &#39;StackerEnsembleModel_LGB&#39;,
  &#39;RandomForestMSE_BAG_L1&#39;: &#39;StackerEnsembleModel_RF&#39;,
  &#39;CatBoost_BAG_L1&#39;: &#39;StackerEnsembleModel_CatBoost&#39;,
  &#39;ExtraTreesMSE_BAG_L1&#39;: &#39;StackerEnsembleModel_XT&#39;,
  &#39;NeuralNetFastAI_BAG_L1&#39;: &#39;StackerEnsembleModel_NNFastAiTabular&#39;,
  &#39;XGBoost_BAG_L1&#39;: &#39;StackerEnsembleModel_XGBoost&#39;,
  &#39;WeightedEnsemble_L2&#39;: &#39;WeightedEnsembleModel&#39;,
  &#39;LightGBMXT_BAG_L2&#39;: &#39;StackerEnsembleModel_LGB&#39;,
  &#39;LightGBM_BAG_L2&#39;: &#39;StackerEnsembleModel_LGB&#39;,
  &#39;RandomForestMSE_BAG_L2&#39;: &#39;StackerEnsembleModel_RF&#39;,
  &#39;CatBoost_BAG_L2&#39;: &#39;StackerEnsembleModel_CatBoost&#39;,
  &#39;ExtraTreesMSE_BAG_L2&#39;: &#39;StackerEnsembleModel_XT&#39;,
  &#39;NeuralNetFastAI_BAG_L2&#39;: &#39;StackerEnsembleModel_NNFastAiTabular&#39;,
  &#39;XGBoost_BAG_L2&#39;: &#39;StackerEnsembleModel_XGBoost&#39;,
  &#39;WeightedEnsemble_L3&#39;: &#39;WeightedEnsembleModel&#39;},
 &#39;model_performance&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: -164.55761532708044,
  &#39;KNeighborsDist_BAG_L1&#39;: -179.00930229155557,
  &#39;LightGBMXT_BAG_L1&#39;: -132.23557968942964,
  &#39;LightGBM_BAG_L1&#39;: -133.13787152819958,
  &#39;RandomForestMSE_BAG_L1&#39;: -131.5184179587791,
  &#39;CatBoost_BAG_L1&#39;: -134.91711055532375,
  &#39;ExtraTreesMSE_BAG_L1&#39;: -129.83886085889378,
  &#39;NeuralNetFastAI_BAG_L1&#39;: -134.4383968570832,
  &#39;XGBoost_BAG_L1&#39;: -134.03513068529045,
  &#39;WeightedEnsemble_L2&#39;: -127.41604620850603,
  &#39;LightGBMXT_BAG_L2&#39;: -127.4950300053687,
  &#39;LightGBM_BAG_L2&#39;: -127.83538230272552,
  &#39;RandomForestMSE_BAG_L2&#39;: -129.00278664393468,
  &#39;CatBoost_BAG_L2&#39;: -126.92986174833601,
  &#39;ExtraTreesMSE_BAG_L2&#39;: -126.7580640060822,
  &#39;NeuralNetFastAI_BAG_L2&#39;: -127.59381983109179,
  &#39;XGBoost_BAG_L2&#39;: -128.10768863016457,
  &#39;WeightedEnsemble_L3&#39;: -126.02445436104549},
 &#39;model_best&#39;: &#39;WeightedEnsemble_L3&#39;,
 &#39;model_paths&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_163254/models/KNeighborsUnif_BAG_L1/&#39;,
  &#39;KNeighborsDist_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_163254/models/KNeighborsDist_BAG_L1/&#39;,
  &#39;LightGBMXT_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_163254/models/LightGBMXT_BAG_L1/&#39;,
  &#39;LightGBM_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_163254/models/LightGBM_BAG_L1/&#39;,
  &#39;RandomForestMSE_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_163254/models/RandomForestMSE_BAG_L1/&#39;,
  &#39;CatBoost_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_163254/models/CatBoost_BAG_L1/&#39;,
  &#39;ExtraTreesMSE_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_163254/models/ExtraTreesMSE_BAG_L1/&#39;,
  &#39;NeuralNetFastAI_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_163254/models/NeuralNetFastAI_BAG_L1/&#39;,
  &#39;XGBoost_BAG_L1&#39;: &#39;AutogluonModels/ag-20220406_163254/models/XGBoost_BAG_L1/&#39;,
  &#39;WeightedEnsemble_L2&#39;: &#39;AutogluonModels/ag-20220406_163254/models/WeightedEnsemble_L2/&#39;,
  &#39;LightGBMXT_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_163254/models/LightGBMXT_BAG_L2/&#39;,
  &#39;LightGBM_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_163254/models/LightGBM_BAG_L2/&#39;,
  &#39;RandomForestMSE_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_163254/models/RandomForestMSE_BAG_L2/&#39;,
  &#39;CatBoost_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_163254/models/CatBoost_BAG_L2/&#39;,
  &#39;ExtraTreesMSE_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_163254/models/ExtraTreesMSE_BAG_L2/&#39;,
  &#39;NeuralNetFastAI_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_163254/models/NeuralNetFastAI_BAG_L2/&#39;,
  &#39;XGBoost_BAG_L2&#39;: &#39;AutogluonModels/ag-20220406_163254/models/XGBoost_BAG_L2/&#39;,
  &#39;WeightedEnsemble_L3&#39;: &#39;AutogluonModels/ag-20220406_163254/models/WeightedEnsemble_L3/&#39;},
 &#39;model_fit_times&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: 0.03838539123535156,
  &#39;KNeighborsDist_BAG_L1&#39;: 0.01816415786743164,
  &#39;LightGBMXT_BAG_L1&#39;: 22.037296056747437,
  &#39;LightGBM_BAG_L1&#39;: 15.188117980957031,
  &#39;RandomForestMSE_BAG_L1&#39;: 7.743190765380859,
  &#39;CatBoost_BAG_L1&#39;: 260.82444643974304,
  &#39;ExtraTreesMSE_BAG_L1&#39;: 4.0230066776275635,
  &#39;NeuralNetFastAI_BAG_L1&#39;: 62.171010971069336,
  &#39;XGBoost_BAG_L1&#39;: 11.167985439300537,
  &#39;WeightedEnsemble_L2&#39;: 0.7142632007598877,
  &#39;LightGBMXT_BAG_L2&#39;: 12.102453470230103,
  &#39;LightGBM_BAG_L2&#39;: 12.966831922531128,
  &#39;RandomForestMSE_BAG_L2&#39;: 31.513241052627563,
  &#39;CatBoost_BAG_L2&#39;: 46.01243734359741,
  &#39;ExtraTreesMSE_BAG_L2&#39;: 7.531237602233887,
  &#39;NeuralNetFastAI_BAG_L2&#39;: 58.27081608772278,
  &#39;XGBoost_BAG_L2&#39;: 11.038499116897583,
  &#39;WeightedEnsemble_L3&#39;: 0.5777091979980469},
 &#39;model_pred_times&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: 0.10786581039428711,
  &#39;KNeighborsDist_BAG_L1&#39;: 0.10468292236328125,
  &#39;LightGBMXT_BAG_L1&#39;: 2.8027503490448,
  &#39;LightGBM_BAG_L1&#39;: 1.2159812450408936,
  &#39;RandomForestMSE_BAG_L1&#39;: 0.43904685974121094,
  &#39;CatBoost_BAG_L1&#39;: 0.44757580757141113,
  &#39;ExtraTreesMSE_BAG_L1&#39;: 0.4304769039154053,
  &#39;NeuralNetFastAI_BAG_L1&#39;: 0.35166501998901367,
  &#39;XGBoost_BAG_L1&#39;: 0.17995095252990723,
  &#39;WeightedEnsemble_L2&#39;: 0.0013427734375,
  &#39;LightGBMXT_BAG_L2&#39;: 0.15581774711608887,
  &#39;LightGBM_BAG_L2&#39;: 0.12465453147888184,
  &#39;RandomForestMSE_BAG_L2&#39;: 0.5399582386016846,
  &#39;CatBoost_BAG_L2&#39;: 0.1420896053314209,
  &#39;ExtraTreesMSE_BAG_L2&#39;: 0.5125117301940918,
  &#39;NeuralNetFastAI_BAG_L2&#39;: 0.45305633544921875,
  &#39;XGBoost_BAG_L2&#39;: 0.09882259368896484,
  &#39;WeightedEnsemble_L3&#39;: 0.0008399486541748047},
 &#39;num_bag_folds&#39;: 5,
 &#39;max_stack_level&#39;: 3,
 &#39;model_hyperparams&#39;: {&#39;KNeighborsUnif_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;KNeighborsDist_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;LightGBMXT_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;LightGBM_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;RandomForestMSE_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;CatBoost_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;ExtraTreesMSE_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;NeuralNetFastAI_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;XGBoost_BAG_L1&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;WeightedEnsemble_L2&#39;: {&#39;use_orig_features&#39;: False,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;LightGBMXT_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;LightGBM_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;RandomForestMSE_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;CatBoost_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;ExtraTreesMSE_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True,
   &#39;use_child_oof&#39;: True},
  &#39;NeuralNetFastAI_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;XGBoost_BAG_L2&#39;: {&#39;use_orig_features&#39;: True,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True},
  &#39;WeightedEnsemble_L3&#39;: {&#39;use_orig_features&#39;: False,
   &#39;max_base_models&#39;: 25,
   &#39;max_base_models_per_type&#39;: 5,
   &#39;save_bag_folds&#39;: True}},
 &#39;leaderboard&#39;:                      model   score_val  pred_time_val    fit_time  \
 0      WeightedEnsemble_L3 -126.024454       7.287316  506.642303   
 1     ExtraTreesMSE_BAG_L2 -126.758064       6.592508  390.742841   
 2          CatBoost_BAG_L2 -126.929862       6.222085  429.224041   
 3      WeightedEnsemble_L2 -127.416046       4.472858  357.513214   
 4        LightGBMXT_BAG_L2 -127.495030       6.235814  395.314057   
 5   NeuralNetFastAI_BAG_L2 -127.593820       6.533052  441.482420   
 6          LightGBM_BAG_L2 -127.835382       6.204650  396.178436   
 7           XGBoost_BAG_L2 -128.107689       6.178818  394.250103   
 8   RandomForestMSE_BAG_L2 -129.002787       6.619954  414.724845   
 9     ExtraTreesMSE_BAG_L1 -129.838861       0.430477    4.023007   
 10  RandomForestMSE_BAG_L1 -131.518418       0.439047    7.743191   
 11       LightGBMXT_BAG_L1 -132.235580       2.802750   22.037296   
 12         LightGBM_BAG_L1 -133.137872       1.215981   15.188118   
 13          XGBoost_BAG_L1 -134.035131       0.179951   11.167985   
 14  NeuralNetFastAI_BAG_L1 -134.438397       0.351665   62.171011   
 15         CatBoost_BAG_L1 -134.917111       0.447576  260.824446   
 16   KNeighborsUnif_BAG_L1 -164.557615       0.107866    0.038385   
 17   KNeighborsDist_BAG_L1 -179.009302       0.104683    0.018164   
 
     pred_time_val_marginal  fit_time_marginal  stack_level  can_infer  \
 0                 0.000840           0.577709            3       True   
 1                 0.512512           7.531238            2       True   
 2                 0.142090          46.012437            2       True   
 3                 0.001343           0.714263            2       True   
 4                 0.155818          12.102453            2       True   
 5                 0.453056          58.270816            2       True   
 6                 0.124655          12.966832            2       True   
 7                 0.098823          11.038499            2       True   
 8                 0.539958          31.513241            2       True   
 9                 0.430477           4.023007            1       True   
 10                0.439047           7.743191            1       True   
 11                2.802750          22.037296            1       True   
 12                1.215981          15.188118            1       True   
 13                0.179951          11.167985            1       True   
 14                0.351665          62.171011            1       True   
 15                0.447576         260.824446            1       True   
 16                0.107866           0.038385            1       True   
 17                0.104683           0.018164            1       True   
 
     fit_order  
 0          18  
 1          15  
 2          14  
 3          10  
 4          11  
 5          16  
 6          12  
 7          17  
 8          13  
 9           7  
 10          5  
 11          3  
 12          4  
 13          9  
 14          8  
 15          6  
 16          1  
 17          2  }</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[41]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Remember to set all negative values to zero</span>
<span class="n">predictor_new_hpo</span> <span class="o">=</span> <span class="n">predictor_new_hpo</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">test</span><span class="p">)</span>
<span class="n">predictor_new_hpo</span><span class="o">.</span><span class="n">iloc</span><span class="p">[</span><span class="n">predictor_new_hpo</span><span class="o">&lt;</span><span class="mi">0</span><span class="p">]</span> <span class="o">=</span> <span class="mi">0</span>
<span class="n">predictor_new_hpo</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[41]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>0    86.789070
1    65.932465
2    65.932465
3    77.006897
4    77.006897
Name: count, dtype: float32</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[42]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Same submitting predictions</span>
<span class="n">submission_new_hpo</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;./sampleSubmission.csv&#39;</span><span class="p">,</span> <span class="n">parse_dates</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;datetime&quot;</span><span class="p">])</span>
<span class="n">submission_new_hpo</span><span class="p">[</span><span class="s2">&quot;count&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">predictor_new_hpo</span>
<span class="n">submission_new_hpo</span><span class="o">.</span><span class="n">to_csv</span><span class="p">(</span><span class="s2">&quot;submission_new_hpo.csv&quot;</span><span class="p">,</span> <span class="n">index</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[43]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">!</span>kaggle competitions submit -c bike-sharing-demand -f submission_new_hpo.csv -m <span class="s2">&quot;new features with hyperparameters&quot;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>100%|█████████████████████████████████████████| 188k/188k [00:00&lt;00:00, 377kB/s]
Successfully submitted to Bike Sharing Demand</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[44]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">!</span>kaggle competitions submissions -c bike-sharing-demand <span class="p">|</span> tail -n +1 <span class="p">|</span> head -n <span class="m">6</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>fileName                     date                 description                        status    publicScore  privateScore  
---------------------------  -------------------  ---------------------------------  --------  -----------  ------------  
submission_new_hpo.csv       2022-04-06 16:43:16  new features with hyperparameters  complete  1.33246      1.33246       
submission_new_features.csv  2022-04-06 16:29:22  new features                       complete  1.31956      1.31956       
submission.csv               2022-04-06 16:14:59  first raw submission               complete  1.80645      1.80645       
submission_new_hpo.csv       2022-04-06 15:17:31  new features with hyperparameters  complete  0.47248      0.47248       
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4 id="New-Score-of-1.332">New Score of <code>1.332</code><a class="anchor-link" href="#New-Score-of-1.332">&#182;</a></h4>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Step-7:-Write-a-Report">Step 7: Write a Report<a class="anchor-link" href="#Step-7:-Write-a-Report">&#182;</a></h2><h3 id="Refer-to-the-markdown-file-for-the-full-report">Refer to the markdown file for the full report<a class="anchor-link" href="#Refer-to-the-markdown-file-for-the-full-report">&#182;</a></h3><h3 id="Creating-plots-and-table-for-report">Creating plots and table for report<a class="anchor-link" href="#Creating-plots-and-table-for-report">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[46]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Take the 3 kaggle scores and creating a line plot to show improvement (Test)</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span>
    <span class="p">{</span>
        <span class="s2">&quot;test_eval&quot;</span><span class="p">:</span> <span class="p">[</span><span class="s2">&quot;initial&quot;</span><span class="p">,</span> <span class="s2">&quot;add_features&quot;</span><span class="p">,</span> <span class="s2">&quot;hpo&quot;</span><span class="p">],</span>
        <span class="s2">&quot;score&quot;</span><span class="p">:</span> <span class="p">[</span><span class="mf">1.806</span><span class="p">,</span> <span class="mf">1.319</span><span class="p">,</span> <span class="mf">1.332</span><span class="p">]</span>
    <span class="p">}</span>
<span class="p">)</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s2">&quot;test_eval&quot;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s2">&quot;score&quot;</span><span class="p">,</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">8</span><span class="p">,</span> <span class="mi">6</span><span class="p">))</span><span class="o">.</span><span class="n">get_figure</span><span class="p">()</span>
<span class="n">fig</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s1">&#39;img/model_test_score.png&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Hyperparameter-table">Hyperparameter table<a class="anchor-link" href="#Hyperparameter-table">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[47]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># The 3 hyperparameters we tuned with the kaggle score as the result</span>
<span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">({</span>
    <span class="s2">&quot;model&quot;</span><span class="p">:</span> <span class="p">[</span><span class="s2">&quot;initial&quot;</span><span class="p">,</span> <span class="s2">&quot;add_features&quot;</span><span class="p">,</span> <span class="s2">&quot;hpo&quot;</span><span class="p">],</span>
    <span class="s2">&quot;num_bag_folds&quot;</span><span class="p">:</span> <span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">5</span><span class="p">],</span>
    <span class="s2">&quot;num_bag_sets&quot;</span><span class="p">:</span> <span class="p">[</span><span class="mi">20</span><span class="p">,</span> <span class="mi">20</span><span class="p">,</span> <span class="mi">1</span><span class="p">],</span>
    <span class="s2">&quot;num_stack_levels&quot;</span><span class="p">:</span> <span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">],</span>
    <span class="s2">&quot;score&quot;</span><span class="p">:</span> <span class="p">[</span><span class="mf">1.806</span><span class="p">,</span> <span class="mf">1.319</span><span class="p">,</span> <span class="mf">1.332</span><span class="p">]</span>
<span class="p">})</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[47]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>model</th>
      <th>num_bag_folds</th>
      <th>num_bag_sets</th>
      <th>num_stack_levels</th>
      <th>score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>initial</td>
      <td>0</td>
      <td>20</td>
      <td>0</td>
      <td>1.806</td>
    </tr>
    <tr>
      <th>1</th>
      <td>add_features</td>
      <td>0</td>
      <td>20</td>
      <td>0</td>
      <td>1.319</td>
    </tr>
    <tr>
      <th>2</th>
      <td>hpo</td>
      <td>5</td>
      <td>1</td>
      <td>1</td>
      <td>1.332</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>
