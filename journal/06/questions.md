# Single Page Applications with Vue
01. What is the entrypoint of an application?

  > App.vue

02. What is the difference between a vue `component` and `page`?

  > design 

03. What is ***Component-Based Architecture***?

  > method for encapsulating individual pieces of a larger user interface (aka components) into self-sustaining, independent micro-systems

04. What are the three tags that make up a Vue component?

  > template script style

05. What are ***lifecycle hooks***? What are lifecycle hooks used for?

  > Lifecycle hooks are a window into how the library you’re using works behind-the-scenes. Lifecycle hooks allow you to know when your component is created, added to the DOM, updated, or destroyed

06. Which component in Vue does the vue-router use to mount pages onto?

  > App.vue

07. What is the difference between the `AppState` and the state object within a component?

  > appState is global state is scoped

08. What is the responsibility of `Services` in our Vue projects?

  > to change data in the appState

09. What are ***props*** and how are they used? Provide an example

  > a copy of a thing thats passed down to a component, a list of things

10. What is the Vue method used to create watchable objects such as `state` or `AppState`?

  > computed(() => thing)
