# Vue.js demo app

Based on udemy course ["Vue - The Complete Guide"](https://www.udemy.com/course/vuejs-2-the-complete-guide) section 10.

![screenshot](./ui_screenshot.png)

## vue concepts applied:

- **Slots**: In BaseCard.vue
- **Dynamic styling**: In BaseButton.vue. Shows how to have one global component for all buttons that can then be used in different variations.
- **Dynamic Components**: In TheResources.vue. Shows how to switch between different components using the component tag and buttons.
- **Inject/Provide Feature**: Shown in TheResources.vue -**Input Forms**: In AddResource.vue. Using refs to create a data object and uses inject/provide to submit the new data to the parent component.
- **Modal Dialog**: Input validation performed in AddResource.vue, if input is invalid a modal is shown (BaseDialog.vue, again using vue's slot functionality), with button to close it.

More information on individual features is found in the components as comments.
