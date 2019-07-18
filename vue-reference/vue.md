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

# Props

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
This can be done the same when consuming an API then passing the data from the API into the child component.

Consume an API in Vue component file and pass data to child component:

1. Must require the child component and register it.
2. Use child component in template tags, and pass the data stored in info[] to its props.
3. Then register parent component with the Vue instance and then can be used inside laravel blade template.

```
<template>
    <child-component :props="info"></child-component>
</template>

<script>
    import ChildComponent from './ChildComponent.vue';
    import axios from 'axios';

    export default {
        data() {
            return {
                info: [],
                errors: []
            }
        },
        components: {
            "child-component": ChildComponent
        },
        mounted() {
            axios.get('URL').then(response => {
                this.info = response.data
            }).catch(error => {
                this.errors.push(error)
            })
        }
    }
</script>
```

Then can loop through info array and display the data.
