# Switch button

Form control to toggle the state of a single setting. Generates a styled checkbox input element.



## Usage

To create an unselected switch with `name` and `value` attributes:

~~~javascript
import m from "mithril";
import switchButton from "polythene-switch-button";

m(switchButton, {
  name: "organisation",
  value: "EFF"
});
~~~

An (initially) selected switch with a label:

~~~javascript
m(switchButton, {
  checked: true,
  label: "Label"
});
~~~

### Dynamic values

To read the checked state use `getState`:

~~~javascript
m(switchButton, {
  getState: state => vnode.state.checked = state.checked
})
~~~

To set the checked state, use `checked` as a function:

~~~javascript
m(switchButton, {
  checked: () => vnode.state.checked
})
~~~

Of course you can also use `events` with an `onclick` event:

~~~javascript
m(switchButton, {
  events: {
    onclick: () => vnode.state.checked = !vnode.state.checked
  }
})
~~~



## Appearance

### Styling

Below are examples how to change the switch appearance, either with a theme or with CSS.

You can find more information about theming in [Theme](../polythene-theme).

#### Themed component

Switch is composed from Selection control, and it uses its style variables.

~~~javascript
switchButton.theme(".blue-switch-button", {
  color_light_on:    "#2196F3",
  color_light_off:   "#2196F3",
  color_light_label: "#2196F3"
});

m(switchButton, {
  class: "blue-switch-button",
  label: "Label"
});
~~~


#### CSS

Change CSS using the CSS Classes at the bottom of this page.

#### Colors

The icon color can be set using `style`.

~~~javascript
m(switchButton, {
  style: { color: "#2196F3" }
});
~~~


### Icons

To use alternative icons, use options `iconOn` and `iconOff` (see also "msvg" at [icon](../polythene-icon)):

~~~javascript
import iconStar from "mmsvg/google/msvg/toggle/star";
import iconStarOutline from "mmsvg/google/msvg/toggle/star-border";

m(switchButton, {
  iconOn: { msvg: iconStar },
  iconOff: { msvg: iconStarOutline }
});
~~~



## Options

### Common component options

| **Parameter** |  **Mandatory** | **Type** | **Default** | **Description** |
| ------------- | -------------- | -------- | ----------- | --------------- |
| **element**   | optional       | String   | "div"       | HTML element tag for the switch container |
| **class**     | optional       | String   |             | Extra CSS class appended to "pe-switch-control" |
| **id**        | optional       | String   |             | HTML element id for the switch container |
| **before**    | optional       | Mithril element |      | Extra content before main content; note that this content is placed left of subsequent elements with a lower stacking depth |
| **after**     | optional       | Mithril element |      | Extra content after main content; note that this content is placed right of preceding elements with a higher stacking depth |
| **events**    | optional       | Object   |             | Options object containing one or more standard events such as `onclick` |
| **tabindex**  | optional       | Integer  |             | Tab index |

### Switch specific

| **Parameter** |  **Mandatory** | **Type** | **Default** | **Description** |
| ------------- | -------------- | -------- | ----------- | --------------- |
| **name**      | optional | String | | Input element name |
| **label**     | optional | String | | Text label |
| **checked**   | optional | Boolean or Function | false | Checked state; use as function to set the value from outside |
| **value**     | optional | String | "1" | Input element value |
| **disabled**  | optional | Boolean |  | Set to true to disable the switch |

### Appearance

| **Parameter**  |  **Mandatory** | **Type** | **Default** | **Description** |
| -------------- | -------------- | -------- | ----------- | --------------- |
| **iconOn**     | optional | Options object for [icon](../polythene-icon) | | Assigns a different icon for the on state |
| **iconOff**    | optional | Options object for [icon](../polythene-icon) | | Assigns a different icon for the off state |
| **iconButton** | optional | Options object for the icon button | | Add attributes like `wash` and `ink` |
| **size**       | optional | String | "regular" | Equivalent to [icon's type](../polythene-icon) option; either "small" (16px), "regular" (24px), "medium" (32px), "large" (40px) |

### Dynamic values

| **Parameter** |  **Mandatory** | **Type** | **Default** | **Description** |
| ------------- | -------------- | -------- | ----------- | --------------- |
| **getState**  | optional | Function(state {Object}) | | Callback function that accepts the field state (Object with properties `checked` {Boolean}, `value` {String}, `el` {HTMLElement}) |
| **selectable** | optional | Function(checked {Boolean}) | | Use to set the active state based on the switch state; function that accepts the field checked value (Boolean) |



### Composition

Switch is composed from:

* [Selection control](../polythene-selection-control)
  * [Icon button](../polythene-icon-button)
  * [Icon](../polythene-icon)
  * [Shadow](../polythene-shadow)



## CSS classes

See also: [Selection control classes](../polythene-selection-control) 

### Control

| **Element** | **Key**     |  **Class** |
| ----------- | ----------- | --------------- |
| Component   | component   | `pe-switch-control` |

### Control view

| **Element** | **Key**     |  **Class** |
| ----------- | ----------- | --------------- |
| Track       | track       | `pe-switch-control__track` |
| Thumb       | thumb       | `pe-switch-control__thumb` |
| Knob        | knob        | `pe-switch-control__knob` |
