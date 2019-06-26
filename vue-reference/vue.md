# Vue.js Reference

Globally register a Vue component:

```
Vue.component('my-component-name', {
  // ... options ...
})
```

Then the component can be used in any Vue instance declared after the component.

Locally register a component, define as plain javascript objects: `var ComponentA = {}`. Or with by requiring it: `import Component from './components/Component.vue';`
Then in the Vue instance use a components option and declare the components that will be used:

```
new Vue({
    el: '#app',
    components: {
        'component-a': ComponentA,
    }
})
```

Props can either be an array of strings: `['This', 'is', 'props']` or they can be an object with prop name and data type: `{ title: String, age: Number }`.

Passing props:

- Static: `<component-a title="This is the title"></component-a>`
- Dynamic: `<component-a v-bind:title="post.title"></component-a>`

When using props in Laravel need to use props method inside a Vue component (e.g ProjectTitle.vue):

```
<template>
    <p>{{ title }}</p>
</template>
<script>
    export default {
        props: ['title']
    }
</script>
```

Then inside the blade file use title component: `<project-title :title="{{ json_encode($projects) }}"></project-title>`. The \$projects variable is passed from the controller. `:title` needs to match value in the props method.
