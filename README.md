# Creenv slider

A simple and fully customizable slider, in native javascript. No need for complexity.

## Usage

```js
var Slider = require("@creenv/slider");

var callbackChange = function (val) {
  console.log("value has changed: "+val);
}

var callbackChangeFinished = function (val) {
  console.log("user has finished sliding: "+val);
}

var mySlider = new Slider(0, 100, 0.5, 10, callbackChange, callbackChangeFinished);
document.body.appendChild(mySlider.dom);
```

## Custom the style 

The css of the slider will be inserted into the < head > tags, within < style > tags identified by `id="creenv-slider-style"`, right at the beginning. You can overwrite any of these rules to apply you own rules. Only 3 classes are used by @creenv/slider:

| Class | What ? |
|---|---|
| *.creenv-slider-container* | The container of the whole slider. Its background-color will be the background color of the slider |
| *.creenv-slider-progress* | The progress bar. Its width will be programatically set to match the value of the slider |
| *.creenv-slider-cursor* | The draggable cursor |

## Constructor 

**Slider**(*min*: **number**, *max*: **number**, *step*: **number**, *value*: **number**, *callbackChange*: **function**, *callbackChangeFinished*: **function**, *vertical*: **boolean**)

| Parameter | Type | What? | Default value |
| --- | --- | --- | --- |
| *min* | **number** | The left value of the slider | *0* |
| *max* | **number** | The right value of the slider | *100* |
| *step* | **number** | Step between each possible value | *0.5* |
| *value* | **number** | Default value the slider can take | *10* |
| *callbackChange* | **function** | Callback function called when a change is detected to the value. Set it to *undefined* if you don't want any action | `()=>{}` |
| *callbackChangeFinished* | **function** | Callback function called when the user is done sliding. Will only be triggered when mouseclick is released. Set it to *undefined* if you don't want any action | `()=>{}` |
| *vertical* | **bolean** | If set to true, the slider will be vertical. It will need a container which height will be the desired slider's height | *false* |

## Accessible (read/write) class members 

| Member | Type | What ? |
|---|---|---|
| *.value* | **number** | Current value of the slider |
| *.min* | **number** | The left value of the slider |
| *.max* | **number** | The right value of the slider |
| *.step* | **number** | The step between each possible value |
| *.onChange* | **function** | Called when value changes because of user input |
| *.onChangeFinished* | **function** | Called when value change is finished |
| *.dom* | **HTMLElement** | The dom element representing the entire slider component |
| *.x* | **number** | X Offset of the slider, from the left of the window. If vertical is set to true, Y of the slider |
| *.width* | **number** | Width, in px, of the slider. If *vertical* is set to true, height of the slider |
| *.container* | **HTMLElement** | DOM element of the container (=.dom) |
| *.progress* | **HTMLElement** | DOM element of the progress bar inside the container |
| *.cursor* | **HTMLElement** | DOM element of the cursor inside the container |