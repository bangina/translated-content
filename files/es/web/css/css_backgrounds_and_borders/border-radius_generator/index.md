---
title: Generador de border-radius
slug: Web/CSS/CSS_Backgrounds_and_Borders/Border-radius_generator
original_slug: Web/CSS/CSS_Background_and_Borders/Border-radius_generator
---

Esta herramienta puede ser usada para generar efectos de {{cssxref("border-radius")}} de CSS3.

#### Herramienta

```html hidden
<div id="container">
    <div class="group section">
        <div id="preview" class="col span_12">
            <div id="subject">
                <div id="top-left" class="radius-container"
                    data-X="left" data-Y="top">
                </div>
                <div id="top-right" class="radius-container"
                    data-X="right" data-Y="top">
                </div>
                <div id="bottom-right" class="radius-container"
                    data-X="right" data-Y="bottom">
                </div>
                <div id="bottom-left" class="radius-container"
                    data-X="left" data-Y="bottom">
                </div>

                <div id="radius-ui-sliders">
                    <div id="tlr" class="ui-input-slider" data-topic="top-left"
                         data-unit=" px" data-sensivity="2"></div>

                    <div id="tlw" class="ui-input-slider" data-topic="top-left-w"
                         data-unit=" px" data-sensivity="2"></div>

                    <div id="tlh" class="ui-input-slider" data-topic="top-left-h"
                        data-unit=" px" data-sensivity="2"></div>

                    <div id="trr" class="ui-input-slider" data-topic="top-right"
                         data-unit=" px" data-sensivity="2"></div>

                    <div id="trw" class="ui-input-slider" data-topic="top-right-w"
                         data-unit=" px" data-sensivity="2"></div>

                    <div id="trh" class="ui-input-slider" data-topic="top-right-h"
                        data-unit=" px" data-sensivity="2"></div>

                    <div id="brr" class="ui-input-slider" data-topic="bottom-right"
                         data-unit=" px" data-sensivity="2"></div>

                    <div id="brw" class="ui-input-slider" data-topic="bottom-right-w"
                         data-unit=" px" data-sensivity="2"></div>

                    <div id="brh" class="ui-input-slider" data-topic="bottom-right-h"
                        data-unit=" px" data-sensivity="2"></div>

                    <div id="blr" class="ui-input-slider" data-topic="bottom-left"
                         data-unit=" px" data-sensivity="2"></div>

                    <div id="blw" class="ui-input-slider" data-topic="bottom-left-w"
                         data-unit=" px" data-sensivity="2"></div>

                    <div id="blh" class="ui-input-slider" data-topic="bottom-left-h"
                        data-unit=" px" data-sensivity="2"></div>
                </div>
            </div>
        </div>
    </div>
    <div id="controls" class="group section">

        <div class="group section">
            <div id="dimensions">
                <div class="ui-input-slider" data-topic="width" data-info="width"
                     data-unit=" px" data-min="150" data-max="700" data-sensivity="1"></div>

                <div class="ui-input-slider" data-topic="height" data-info="height"
                    data-unit=" px" data-min="75" data-max="350" data-sensivity="1"></div>
            </div>

            <div id="output"></div>
        </div>

        <div class="group section">
            <div id="radius-lock">
                <div class="info"> rounded corner </div>
                <div class="ui-checkbox" data-topic='top-left'></div>
                <div class="ui-checkbox" data-topic='top-right'></div>
                <div class="ui-checkbox" data-topic='bottom-right'></div>
                <div class="ui-checkbox" data-topic='bottom-left'></div>
            </div>

            <div id="unit-selection">
                <div class="info"> select border units </div>
            </div>
        </div>

    </div>
</div>
```

```css hidden
/*  GRID OF TEN
 * ========================================================================== */

.span_12 {
 width: 100%;
}

.span_11 {
 width: 91.46%;
}

.span_10 {
 width: 83%;
}

.span_9 {
 width: 74.54%;
}

.span_8 {
 width: 66.08%;
}

.span_7 {
 width: 57.62%;
}

.span_6 {
 width: 49.16%;
}

.span_5 {
 width: 40.7%;
}

.span_4 {
 width: 32.24%;
}

.span_3 {
 width: 23.78%;
}

.span_2 {
 width: 15.32%;
}

.span_1 {
 width: 6.86%;
}




/*  SECTIONS
 * ========================================================================== */

.section {
 clear: both;
 padding: 0px;
 margin: 0px;
}

/*  GROUPING
 * ========================================================================== */


.group:before, .group:after {
    content: "";
    display: table;
}

.group:after {
    clear:both;
}

.group {
    zoom: 1; /* For IE 6/7 (trigger hasLayout) */
}

/*  GRID COLUMN SETUP
 * ========================================================================== */

.col {
 display: block;
 float:left;
 margin: 1% 0 1% 1.6%;
}

.col:first-child {
 margin-left: 0;
} /* all browsers except IE6 and lower */


/*
 * UI Component
 */

.ui-input-slider-container {
 height: 20px;
 margin: 10px 0;
 font-family: "Segoe UI", Arial, Helvetica, sans-serif;
 -moz-user-select: none;
 user-select: none;
}

.ui-input-slider-container * {
 float: left;
 height: 100%;
 line-height: 100%;
}

/* Input Slider */

.ui-input-slider > input {
 margin: 0;
 padding: 0;
 width: 50px;
 text-align: center;

 -moz-box-sizing: border-box;
 -webkit-box-sizing: border-box;
 box-sizing: border-box;
}

.ui-input-slider-info {
 width: 90px;
 padding: 0px 10px 0px 0px;
 text-align: right;
 text-transform: lowercase;
}

.ui-input-slider-left, .ui-input-slider-right {
 width: 16px;
 cursor: pointer;
 background: url("https://mdn.mozillademos.org/files/5679/arrows.png") center left no-repeat;
}

.ui-input-slider-right {
 background: url("https://mdn.mozillademos.org/files/5679/arrows.png") center right no-repeat;
}

.ui-input-slider-name {
 width: 90px;
 padding: 0 10px 0 0;
 text-align: right;
 text-transform: lowercase;
}

.ui-input-slider-btn-set {
 width: 25px;
 background-color: #2C9FC9;
 border-radius: 5px;
 color: #FFF;
 font-weight: bold;
 line-height: 14px;
 text-align: center;
}

.ui-input-slider-btn-set:hover {
 background-color: #379B4A;
 cursor: pointer;
}

/*
 * UI Component
 */

/* Checkbox */

.ui-checkbox {
 text-align: center;
 font-size: 16px;
 font-family: "Segoe UI", Arial, Helvetica, sans-serif;
 line-height: 1.5em;
 color: #FFF;

 -moz-user-select: none;
 -webkit-user-select: none;
 -ms-user-select: none;
 user-select: none;
}

.ui-checkbox > input {
  display: none;
}

.ui-checkbox > label {
 font-size: 12px;
 padding: 0.333em 1.666em 0.5em;
 height: 1em;
 line-height: 1em;

 background-color: #888;
 background-image: url("https://mdn.mozillademos.org/files/5683/disabled.png");
 background-position: center center;
 background-repeat: no-repeat;

 color: #FFF;
 border-radius: 3px;
 font-weight: bold;
 float: left;
}

.ui-checkbox .text {
 padding-left: 34px;
 background-position: center left 10px;
}

.ui-checkbox .left {
 padding-right: 34px;
 padding-left: 1.666em;
 background-position: center right 10px;
}

.ui-checkbox > label:hover {
 cursor: pointer;
}

.ui-checkbox > input:checked + label {
 background-image: url("https://mdn.mozillademos.org/files/5681/checked.png");
 background-color: #379B4A;
}

body {
 max-width: 1000px;
 margin: 0 auto;

 font-family: "Segoe UI", Arial, Helvetica, sans-serif;

 -moz-box-sizing: border-box;
 -webkit-box-sizing: border-box;
 box-sizing: border-box;

 -moz-user-select: none;
 -webkit-user-select: none;
 -ms-user-select: none;
 user-select: none;
}

#container {
 width: 100%;

 -moz-box-sizing: border-box;
 -webkit-box-sizing: border-box;
 box-sizing: border-box;
}

/******************************************************************************/
/******************************************************************************/
/*
 * Preview Area
 */

#preview {
 height: 500px;
 border: 1px solid #CCC;
 border-radius: 3px;
 text-align: center;
 overflow: hidden;
 position: relative;
}

#preview .content {
 width: 100%;
 height: 100%;
 display: block;
}

#preview input {
 color: #333;
 border: 1px solid #CCC;
 border-radius: 3px;
}

#subject {
 width: 400px;
 height: 150px;
 margin: 0 auto;
 border: 3px solid #C60;
 background: #FFF;
 position: relative;
}

.radius {
 width: 50%;
 height: 50%;
 border: 1px solid #CCC;
 display: none;
 position: absolute;
 z-index: 1;
 -moz-box-sizing: border-box;
 -webkit-box-sizing: border-box;
 box-sizing: border-box;
}

.handle {
 width: 16px;
 height: 16px;
 position: absolute;
 z-index: 2;
}

.handle-top-left {
 top: -12px;
 left: -12px;
 cursor: se-resize;
 background: url("https://mdn.mozillademos.org/files/5677/resize-handle.png") top left no-repeat;
}

.handle-top-right {
 top: -12px;
 right: -12px;
 cursor: sw-resize;
 background: url("https://mdn.mozillademos.org/files/5677/resize-handle.png") top right no-repeat;
}

.handle-bottom-right {
 bottom: -12px;
 right: -12px;
 cursor: nw-resize;
 background: url("https://mdn.mozillademos.org/files/5677/resize-handle.png") bottom right no-repeat;
}

.handle-bottom-left {
 bottom: -12px;
 left: -12px;
 cursor: ne-resize;
 background: url("https://mdn.mozillademos.org/files/5677/resize-handle.png") bottom left no-repeat;
}


.radius-container {
 position: absolute;
 display : block;
 z-index: 1;

 -moz-box-sizing: border-box;
 -webkit-box-sizing: border-box;
 box-sizing: border-box;
}


/* TOP LEFT */
#top-left {
 top: 0;
 left: 0;
}

#top-left .radius {
 border-top-left-radius: 100%;
 top: 0;
 left: 0;
}

/* TOP RIGHT */
#top-right {
 top: 0;
 right: 0;
}

#top-right .radius {
 border-top-right-radius: 100%;
 top: 0;
 right: 0;
}

/* BOTTOM RIGHT */
#bottom-right {
 bottom: 0;
 right: 0;
}

#bottom-right .radius {
 border-bottom-right-radius: 100%;
 bottom: 0;
 right: 0;
}

/* BOTTOM lEFT */
#bottom-left {
 bottom: 0;
 left: 0;
}

#bottom-left .radius {
 border-bottom-left-radius: 100%;
 bottom: 0;
}

/* INPUT SLIDERS */

#preview .ui-input-slider {
 margin: 10px;
 position: absolute;
 z-index: 10;
}

#radius-ui-sliders {
 width: 100%;
 height: 100%;
 min-height: 75px;
 min-width: 150px;
 padding: 20px 50px;
 top: -20px;
 left: -50px;
 position: relative;
}

#tlr {
 top: -30px;
 left: -50px;
 display: none;
}

#tlw {
 top: -30px;
 left: 30px;
}

#tlh {
 top: 20px;
 left: -50px;
}

#trr {
 top: -30px;
 right: -50px;
 display: none;
}

#trw {
 top: -30px;
 right: 30px;
}

#trh {
 top: 20px;
 right: -50px;
}

#brr {
 bottom: -30px;
 right: -50px;
 display: none;
}

#brw {
 bottom: -30px;
 right: 30px;
}

#brh {
 bottom: 20px;
 right: -50px;
}

#blr {
 bottom: -30px;
 left: -50px;
 display: none;
}

#blw {
 bottom: -30px;
 left: 30px;
}

#blh {
 bottom: 20px;
 left: -50px;
}

#preview .ui-input-slider-left, #preview .ui-input-slider-right {
 visibility: hidden;
}

#preview .ui-input-slider-container:hover .ui-input-slider-left {
 visibility: visible;
}

#preview .ui-input-slider-container:hover .ui-input-slider-right {
 visibility: visible;
}

/*
 *
 */

#unit-selection {
 width: 200px;
 height: 75px;
 margin: 30px 30px 0 0;
 padding: 30px;
 border: 3px solid #555;
 border-radius: 10px;
 position: relative;
 float: right;
}

#unit-selection .info {
 height: 20%;
 width: 100%;
 line-height: 20%;
 font-size: 20px;
 text-align: center;
 position: relative;
 top: 40%;
}

#unit-selection .dropdown {
 width: 50px;
 height: 20px;
 margin: 10px;
 padding: 0;
 border-radius: 3px;
 position: absolute;
 overflow: hidden;
}

#unit-selection select {
 width: 50px;
 height: 20px;
 marign: 0;
 padding: 0 0 0 10px;
 background: #555;
 border: 1px solid #555;
 border: none;
 color: #FFF;
 float: left;
}

#unit-selection select option {
 background: #FFF;
 color: #333;
}

#unit-selection select:hover {
 cursor: pointer;
}

#unit-selection .dropdown:before {
 content: "";
 width: 18px;
 height: 20px;
 display: block;
 background-color: #555;
 background-image: url("https://mdn.mozillademos.org/files/5675/dropdown.png");
 background-position: center center;
 background-repeat: no-repeat;
 top: 0px;
 right: 0px;
 position: absolute;
 z-index: 1;
 pointer-events: none;
}

#unit-selection .unit-top-left {
 top: 0;
 left: 0;
 display: none;
}

#unit-selection .unit-top-left-w {
 top: -22px;
 left: 30px;
}

#unit-selection .unit-top-left-h {
 top: 20px;
 left: -37px;
}

#unit-selection .unit-top-right {
 top: 0;
 right: 0;
 display: none;
}

#unit-selection .unit-top-right-w {
 top: -22px;
 right: 30px;
}

#unit-selection .unit-top-right-h {
 top: 20px;
 right: -37px;
}

#unit-selection .unit-bottom-right {
 bottom: 0;
 right: 0;
 display: none;
}

#unit-selection .unit-bottom-right-w {
 bottom: -22px;
 right: 30px;
}

#unit-selection .unit-bottom-right-h {
 bottom: 20px;
 right: -37px;
}

#unit-selection .unit-bottom-left {
 bottom: 0;
 left: 0;
 display: none;
}

#unit-selection .unit-bottom-left-w {
 bottom: -22px;
 left: 30px;
}

#unit-selection .unit-bottom-left-h {
 bottom: 20px;
 left: -37px;
}

/******************************************************************************/
/******************************************************************************/


#radius-lock {
 width: 200px;
 height: 75px;
 margin: 30px 0 0 30px;
 padding: 30px;
 border: 3px solid #555;
 border-radius: 10px;
 position: relative;
 float: left;
}

#radius-lock .ui-checkbox {
 color: #FFF;
 position: absolute;
}

#radius-lock .ui-checkbox > label {
 height: 20px;
 width: 34px;
 padding: 0;
}

#radius-lock .info {
 height: 20%;
 width: 100%;
 line-height: 20%;
 font-size: 20px;
 text-align: center;
 position: relative;
 top: 40%;
}

#radius-lock [data-topic="top-left"] {
 top: 10px;
 left: 10px;
}

#radius-lock [data-topic="top-right"] {
 top: 10px;
 right: 10px;
}

#radius-lock [data-topic="bottom-right"] {
 bottom: 10px;
 right: 10px;
}

#radius-lock [data-topic="bottom-left"] {
 bottom: 10px;
 left: 10px;
}

/**
 * Controls
 */

#dimensions {
 width: 200px;
 color: #444;
 float:left;
}

#dimensions input {
 background: #555;
 color: #FFF;
 border: none;
 border-radius: 3px;
}

#output {
 width: 500px;
 padding: 10px 0;
 margin: 10px 0;
 color: #555;
 text-align: center;
 border: 1px dashed #999;
 border-radius: 3px;
 -moz-user-select: text;
 -webkit-user-select: text;
 -ms-user-select: text;
 user-select: text;

 float: right;
}
```

```js hidden
'use strict';


/**
 * UI-InputSliderManager
 */

var InputSliderManager = (function InputSliderManager() {

 var subscribers = {};
 var sliders = [];

 var InputComponent = function InputComponent(obj) {
  var input = document.createElement('input');
  input.setAttribute('type', 'text');

  input.addEventListener('click', function(e) {
   this.select();
  });

  input.addEventListener('change', function(e) {
   var value = parseInt(e.target.value);

   if (isNaN(value) === true)
    setValue(obj.topic, obj.value);
   else
    setValue(obj.topic, value);
  });

  subscribe(obj.topic, function(value) {
   input.value = value + obj.unit;
  });

  return input;
 }

 var SliderComponent = function SliderComponent(obj, sign) {
  var slider = document.createElement('div');
  var startX = null;
  var start_value = 0;

  slider.addEventListener("click", function(e) {
   setValue(obj.topic, obj.value + obj.step * sign);
  });

  slider.addEventListener("mousedown", function(e) {
   startX = e.clientX;
   start_value = obj.value;
   document.body.style.cursor = "e-resize";
   document.addEventListener("mousemove", sliderMotion);
  });

  document.addEventListener("mouseup", function(e) {
   document.removeEventListener("mousemove", sliderMotion);
   document.body.style.cursor = "auto";
   slider.style.cursor = "pointer";
  });

  var sliderMotion = function sliderMotion(e) {
   slider.style.cursor = "e-resize";
   var delta = (e.clientX - startX) / obj.sensivity | 0;
   var value = delta * obj.step + start_value;
   setValue(obj.topic, value);
  }

  return slider;
 }

 var InputSlider = function(node) {
  var min  = node.getAttribute('data-min') | 0;
  var max  = node.getAttribute('data-max') | 0;
  var step = node.getAttribute('data-step') | 0;
  var value = node.getAttribute('data-value') | 0;
  var topic = node.getAttribute('data-topic');
  var unit = node.getAttribute('data-unit');
  var name  = node.getAttribute('data-info');
  var sensivity = node.getAttribute('data-sensivity') | 0;

  this.min = min;
  this.max = max > 0 ? max : 100;
  this.step = step === 0 ? 1 : step;
  this.topic = topic;
  this.node = node;
  this.unit = unit;
  this.sensivity = sensivity > 0 ? sensivity : 5;

  var input = new InputComponent(this);
  var slider_left  = new SliderComponent(this, -1);
  var slider_right = new SliderComponent(this,  1);

  slider_left.className = 'ui-input-slider-left';
  slider_right.className = 'ui-input-slider-right';

  if (name) {
   var info = document.createElement('span');
   info.className = 'ui-input-slider-info';
   info.textContent = name;
   node.appendChild(info);
  }

  node.appendChild(slider_left);
  node.appendChild(input);
  node.appendChild(slider_right);
  node.className = 'ui-input-slider ui-input-slider-container';

  this.input = input;
  sliders[topic] = this;
  setValue(topic, value);
 }

 var setValue = function setValue(topic, value, send_notify) {
  var slider = sliders[topic];
  if (slider === undefined)
   return;

  if (value > slider.max) value = slider.max;
  if (value < slider.min) value = slider.min;

  slider.value = value;
  slider.node.setAttribute('data-value', value);

  if (send_notify !== undefined && send_notify === false) {
   slider.input.value = value + slider.unit;
   return;
  }

  notify.call(slider);
 }

 var setMax = function setMax(topic, value) {
  var slider = sliders[topic];
  if (slider === undefined)
   return;

  slider.max = value;
  setValue(topic, slider.value);
 }

 var setMin = function setMin(topic, value) {
  var slider = sliders[topic];
  if (slider === undefined)
   return;

  slider.min = value;
  setValue(topic, slider.value);
 }

 var setUnit = function setUnit(topic, unit) {
  var slider = sliders[topic];
  if (slider === undefined)
   return;

  slider.unit = unit;
  setValue(topic, slider.value);
 }

 var getNode =  function getNode(topic) {
  return sliders[topic].node;
 }

 var subscribe = function subscribe(topic, callback) {
  if (subscribers[topic] === undefined)
   subscribers[topic] = [];
  subscribers[topic].push(callback);
 }

 var unsubscribe = function unsubscribe(topic, callback) {
  subscribers[topic].indexOf(callback);
  subscribers[topic].splice(index, 1);
 }

 var notify = function notify() {
  for (var i in subscribers[this.topic]) {
   subscribers[this.topic][i](this.value);
  }
 }

 var init = function init() {
  var elem = document.querySelectorAll('.ui-input-slider');
  var size = elem.length;
  for (var i = 0; i < size; i++)
   new InputSlider(elem[i]);
 }

 return {
  init : init,
  setMax : setMax,
  setMin : setMin,
  setUnit : setUnit,
  getNode : getNode,
  setValue : setValue,
  subscribe : subscribe,
  unsubscribe : unsubscribe
 }

})();

/**
 * UI-ButtonManager
 */

var ButtonManager = (function CheckBoxManager() {

 var subscribers = [];
 var buttons = [];

 var CheckBox = function CheckBox(node) {
  var topic = node.getAttribute('data-topic');
  var state = node.getAttribute('data-state');
  var name = node.getAttribute('data-label');
  var align = node.getAttribute('data-text-on');

  state = (state === "true");

  var checkbox = document.createElement("input");
  var label = document.createElement("label");

  var id = 'checkbox-' + topic;
  checkbox.id = id;
  checkbox.setAttribute('type', 'checkbox');
  checkbox.checked = state;

  label.setAttribute('for', id);
  if (name) {
   label.className = 'text';
   if (align)
    label.className += ' ' + align;
   label.textContent = name;
  }

  node.appendChild(checkbox);
  node.appendChild(label);

  this.node = node;
  this.topic = topic;
  this.checkbox = checkbox;

  checkbox.addEventListener('change', function(e) {
   notify.call(this);
  }.bind(this));

  buttons[topic] = this;
 }

 var getNode =  function getNode(topic) {
  return buttons[topic].node;
 }

 var setValue = function setValue(topic, value) {
  try {
   buttons[topic].checkbox.checked = value;
  }
  catch(error) {
   console.log(error);
  }
 }

 var subscribe = function subscribe(topic, callback) {
  if (subscribers[topic] === undefined)
   subscribers[topic] = [];

  subscribers[topic].push(callback);
 }

 var unsubscribe = function unsubscribe(topic, callback) {
  subscribers[topic].indexOf(callback);
  subscribers[topic].splice(index, 1);
 }

 var notify = function notify() {
  for (var i = 0; i < subscribers[this.topic].length; i++)
   subscribers[this.topic][i](this.checkbox.checked);
 }

 var init = function init() {
  var elem = document.querySelectorAll('.ui-checkbox');
  var size = elem.length;
  for (var i = 0; i < size; i++)
   new CheckBox(elem[i]);
 }

 return {
  init : init,
  setValue : setValue,
  subscribe : subscribe,
  unsubscribe : unsubscribe
 }

})();


window.addEventListener("load", function() {
 BorderRadius.init();
});

var BorderRadius = (function BorderRadius() {

 function getElemById(id) {
  return document.getElementById(id);
 }

 /**
  * Shadow dragging
  */
 var PreviewMouseTracking = (function Drag() {
  var active = false;
  var lastX = 0;
  var lastY = 0;
  var subscribers = [];

  var init = function init(id) {
   var elem = getElemById(id);
   elem.addEventListener('mousedown', dragStart, false);
   document.addEventListener('mouseup', dragEnd, false);
  }

  var dragStart = function dragStart(e) {
   if (e.button !== 0)
    return;

   active = true;
   lastX = e.clientX;
   lastY = e.clientY;
   document.addEventListener('mousemove', mouseDrag, false);
  }

  var dragEnd = function dragEnd(e) {
   if (e.button !== 0)
    return;

   if (active === true) {
    active = false;
    document.removeEventListener('mousemove', mouseDrag, false);
   }
  }

  var mouseDrag = function mouseDrag(e) {
   notify(e.clientX - lastX, e.clientY - lastY);
   lastX = e.clientX;
   lastY = e.clientY;
  }

  var subscribe = function subscribe(callback) {
   subscribers.push(callback);
  }

  var unsubscribe = function unsubscribe(callback) {
   var index = subscribers.indexOf(callback);
   subscribers.splice(index, 1);
  }

  var notify = function notify(deltaX, deltaY) {
   for (var i in subscribers)
    subscribers[i](deltaX, deltaY);
  }

  return {
   init : init,
   subscribe : subscribe,
   unsubscribe : unsubscribe
  }

 })();

 var subject;
 var units = ['px', '%'];
 var output = null;

 var UnitSelector = function UnitSelector(topic) {

  this.container = document.createElement("div");
  this.select = document.createElement("select");
  for (var i in units) {
   var option = document.createElement("option");
   option.value = i;
   option.textContent = units[i];
   this.select.appendChild(option);
  }

  this.container.className = 'dropdown ' + 'unit-' + topic;
  this.container.appendChild(this.select);
 }

 UnitSelector.prototype.setValue = function setValue(value) {
  this.salect.value = value;
 }


 var RadiusContainer = function RadiusContainer(node) {
  var radius = document.createElement('div');
  var handle = document.createElement('div');
  var x = node.getAttribute('data-x');
  var y = node.getAttribute('data-y');
  var active = false;

  this.id = node.id;
  this.node = node;
  this.radius = radius;
  this.handle = handle;
  this.width = 100;
  this.height = 50;
  this.size = 0;
  this.rounded = false;

  this.unitX = 0;
  this.unitY = 0;
  this.unitR = 0;

  this.maxW = 100;
  this.maxH = 100;
  this.maxR = 100;

  this.topic = y + '-' + x;

  var sliderW = InputSliderManager.getNode(this.topic + '-w');
  var sliderH = InputSliderManager.getNode(this.topic + '-h');
  var sliderR = InputSliderManager.getNode(this.topic);

  this.setUnitX(this.unitX);
  this.setUnitY(this.unitY);
  this.setUnitR(this.unitR);

  this.updateWidth();
  this.updateHeight();
  this.updateRadius();

  if (x === 'left') this.resizeX =  1;
  if (x === 'right') this.resizeX = -1;
  if (y === 'top') this.resizeY =  1;
  if (y === 'bottom') this.resizeY = -1;

  radius.className = 'radius';

  var unit_selector = document.getElementById("unit-selection");
  var unitW = new UnitSelector(this.topic + '-w');
  var unitH = new UnitSelector(this.topic + '-h');
  var unitR = new UnitSelector(this.topic);

  unit_selector.appendChild(unitW.container);
  unit_selector.appendChild(unitH.container);
  unit_selector.appendChild(unitR.container);
  node.appendChild(radius);
  subject.appendChild(handle);

  unitW.select.addEventListener('change', function(e) {
   this.setUnitX(e.target.value | 0);
  }.bind(this));

  unitH.select.addEventListener('change', function(e) {
   this.setUnitY(e.target.value | 0);
  }.bind(this));

  unitR.select.addEventListener('change', function(e) {
   this.setUnitR(e.target.value | 0);
  }.bind(this));

  if (x === 'left' && y == 'top') handle.className = 'handle handle-top-left'
  if (x === 'right' && y == 'top') handle.className = 'handle handle-top-right';
  if (x === 'right' && y == 'bottom') handle.className = 'handle handle-bottom-right';
  if (x === 'left' && y == 'bottom')  handle.className = 'handle handle-bottom-left';

  handle.addEventListener("mousedown", function(e) {
   active = true;
   this.radius.style.display = 'block';
   PreviewMouseTracking.subscribe(this.updateContainer.bind(this));
  }.bind(this));

  document.addEventListener("mouseup", function(e) {
   this.radius.style.display = 'none';
   if (active === true)
    PreviewMouseTracking.unsubscribe(this.updateContainer.bind(this));
  }.bind(this));

  InputSliderManager.subscribe(this.topic + '-w', this.setWidth.bind(this));
  InputSliderManager.subscribe(this.topic + '-h', this.setHeight.bind(this));
  InputSliderManager.subscribe(this.topic, this.setRadius.bind(this));

  ButtonManager.subscribe(this.topic, function(value) {
   this.rounded = value;
   if (value === true) {
    unitW.container.style.display = 'none';
    unitH.container.style.display = 'none';
    unitR.container.style.display = 'block';
    sliderW.style.display = 'none';
    sliderH.style.display = 'none';
    sliderR.style.display = 'block';
    this.setUnitR(this.unitR);
    this.updateRadius();
   }

   if (value === false) {
    unitW.container.style.display = 'block';
    unitH.container.style.display = 'block';
    unitR.container.style.display = 'none';
    sliderW.style.display = 'block';
    sliderH.style.display = 'block';
    sliderR.style.display = 'none';
    this.setUnitX(this.unitX);
    this.setUnitY(this.unitY);
    this.updateWidth();
    this.updateHeight();
   }

   this.updateBorderRadius();

  }.bind(this));

  this.updateBorderRadius();
 }

 RadiusContainer.prototype.updateWidth = function updateWidth() {
  this.node.style.width = this.width + units[this.unitX];
  var value = Math.round(this.width / 2);
  InputSliderManager.setValue(this.topic + '-w', value, false);
 }

 RadiusContainer.prototype.updateHeight = function updateHeight() {
  this.node.style.height = this.height + units[this.unitY];
  var value = Math.round(this.height / 2);
  InputSliderManager.setValue(this.topic + '-h', value, false);
 }

 RadiusContainer.prototype.updateRadius = function updateRadius() {
  var value = Math.round(this.size / 2);
  this.node.style.width = this.size + units[this.unitR];
  this.node.style.height = this.size + units[this.unitR];
  InputSliderManager.setValue(this.topic, value, false);
 }

 RadiusContainer.prototype.setWidth = function setWidth(value) {
  this.radius.style.display = 'block';
  this.width = 2 * value;
  this.node.style.width = this.width + units[this.unitX];
  this.updateBorderRadius();
 }

 RadiusContainer.prototype.setHeight = function setHeight(value) {
  this.radius.style.display = 'block';
  this.height = 2 * value;
  this.node.style.height = this.height + units[this.unitY];
  this.updateBorderRadius();
 }

 RadiusContainer.prototype.setRadius = function setRadius(value) {
  this.radius.style.display = 'block';
  this.size = 2 * value;
  this.node.style.width = this.size + units[this.unitR];
  this.node.style.height = this.size + units[this.unitR];
  this.updateBorderRadius();
 }

 RadiusContainer.prototype.setUnitX = function setUnitX(value) {
  this.unitX = value;
  if (this.unitX === 0) this.maxW = 2 * subject.clientWidth;
  if (this.unitX === 1) this.maxW = 200;
  InputSliderManager.setUnit(this.topic + '-w', units[this.unitX]);
  InputSliderManager.setMax(this.topic + '-w', this.maxW / 2);
 }

 RadiusContainer.prototype.setUnitY = function setUnitY(value) {
  this.unitY = value;
  if (this.unitY === 0) this.maxH = 2 * subject.clientHeight;
  if (this.unitY === 1) this.maxH = 200;
  InputSliderManager.setUnit(this.topic + '-h', units[this.unitY]);
  InputSliderManager.setMax(this.topic + '-h', this.maxH / 2);
 }

 RadiusContainer.prototype.setUnitR = function setUnitR(value) {
  this.unitR = value;

  if (this.unitR === 0)
   this.maxR = 2 * Math.min(subject.clientHeight , subject.clientWidth);

  if (this.unitR === 1)
   this.maxR = 200;

  InputSliderManager.setUnit(this.topic, units[this.unitR]);
  InputSliderManager.setMax(this.topic, this.maxR / 2);
 }

 RadiusContainer.prototype.updateUnits = function updateUnits(unit) {
  if (this.rounded) {
   this.setUnitR(this.unitR);
   return;
  }

  if (unit === 0)
   this.setUnitX(this.unitX);

  if (unit === 1)
   this.setUnitY(this.unitY);
 }

 RadiusContainer.prototype.composeBorderRadius = function composeBorderRadius () {

  if (this.rounded === true) {
   var unit = units[this.unitR];
   var value = Math.round(this.size / 2);
   return value + unit;
  }

  var unitX = units[this.unitX];
  var unitY = units[this.unitY];
  var valueX = Math.round(this.width / 2);
  var valueY = Math.round(this.height / 2);

  if (valueX === valueY && this.unitX === this.unitY)
   return valueX + unitX;

  return valueX + unitX + ' ' + valueY + unitY;
 }

 RadiusContainer.prototype.updateBorderRadius = function updateBorderRadius () {
  var radius = this.composeBorderRadius();
  var corner = 0;

  if (this.topic === 'top-left') {
   subject.style.borderTopLeftRadius = radius;
   corner = 0;
  }

  if (this.topic === 'top-right') {
   subject.style.borderTopRightRadius = radius;
   corner = 1;
  }

  if (this.topic === 'bottom-right') {
   subject.style.borderBottomRightRadius = radius;
   corner = 2;
  }

  if (this.topic === 'bottom-left') {
   subject.style.borderBottomLeftRadius = radius;
   corner = 3;
  }

  Tool.updateOutput(corner, radius);
 }

 RadiusContainer.prototype.updateContainer = function updateContainer(deltaX, deltaY) {

  if (this.rounded === true) {
   this.size += this.resizeX * deltaX + this.resizeY * deltaY;
   if (this.size < 0) this.size = 0;
   if (this.size > this.maxR) this.size = this.maxR;
   this.updateRadius();
   this.updateBorderRadius();
   return;
  }

  if (deltaX) {
   this.width += this.resizeX * deltaX;
   if (this.width < 0) this.width = 0;
   if (this.width > this.maxW) this.width = this.maxW;
   this.updateWidth();
  }

  if (deltaY) {
   this.height += this.resizeY * deltaY;
   if (this.height < 0) this.height = 0;
   if (this.height > this.maxH) this.height = this.maxH;
   this.updateHeight();
  }

  if (deltaX || deltaY)
   this.updateBorderRadius();
 }


 /**
  * Tool Manager
  */
 var Tool = (function Tool() {
  var preview;
  var preview_ui;
  var radius_containers = [];
  var border_width = 3;
  var borders1 = [null, null, null, null];
  var borders2 = [0, 0, 0, 0];

  var updateUIWidth = function updateUIWidth(value) {
   var pwidth = subject.parentElement.clientWidth;
   var left = (pwidth - value) / 2;
   subject.style.width = value + "px";

   for (var i = 0; i < 4; i++)
    radius_containers[i].updateUnits(0);
  }

  var updateUIHeight = function updateUIHeight(value) {
   var pheight = subject.parentElement.clientHeight;
   var top = (pheight - value) / 2;
   subject.style.height = value + "px";
   subject.style.top = top - border_width + "px";

   for (var i = 0; i < 4; i++)
    radius_containers[i].updateUnits(1);
  }

  var updatePreviewUIWidth = function updatePreviewUIWidth() {
   var p = subject.parentElement.clientWidth;
   var v = preview_ui.clientWidth;
   console.log(p, v, (p - v ) / 2);
   preview_ui.style.left = (p - v) / 2 + "px" ;
  }

  var updatePreviewUIHeight = function updatePreviewUIHeight() {
   var p = subject.parentElement.clientHeight;
   var v = preview_ui.clientHeight;
   console.log(p, v, (p - v ) / 2);
   preview_ui.style.top = (p - v) / 2 + "px" ;
  }

  var updateOutput = function updateOutput(corner, radius) {
   var values = radius.split(" ");

   borders1[corner] = values[0];
   borders2[corner] = values[0];

   if (values.length === 2)
    borders2[corner] = values[1];

   var border_1_value = borders1.join(" ");
   var border_2_value = borders2.join(" ");
   var border_radius = 'border-radius: ' + border_1_value;

   if (border_2_value !== border_1_value)
    border_radius += ' / ' + border_2_value;

   border_radius += ';';
   output.textContent = border_radius;
  }

  var init = function init() {
   preview = getElemById("preview");
   subject = getElemById("subject");
   output = getElemById("output");
   preview_ui = getElemById("radius-ui-sliders");

   var elem = document.querySelectorAll('.radius-container');
   var size = elem.length;
   for (var i = 0; i < size; i++)
    radius_containers[i] = new RadiusContainer(elem[i]);

   InputSliderManager.subscribe("width", updateUIWidth);
   InputSliderManager.subscribe("height", updateUIHeight);

   InputSliderManager.setValue("width", subject.clientWidth);
   InputSliderManager.setValue("height", subject.clientHeight);
  }

  return {
   init : init,
   updateOutput : updateOutput
  }

 })();

 /**
  * Init Tool
  */
 var init = function init() {
  ButtonManager.init();
  InputSliderManager.init();
  PreviewMouseTracking.init("preview");
  Tool.init();
 }

 return {
  init : init
 }

})();
```

{{ EmbedLiveSample('border-radius-generator', '100%', '800px', '') }}
