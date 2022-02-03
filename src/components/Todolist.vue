<template>
    <div>
        <header>
            My Todo App in Vue Js
            <button v-on:click="deleteData">Delete All Tasks</button>
        </header>
        <body>
        <FormComponent />
        <ListComponent />
        </body>
    </div>
</template>
<script>
import ListComponent from './ListComponent.vue'
import FormComponent from './FormComponent.vue'
export default {
  name: 'TodoList',
  components: {
      ListComponent,
      FormComponent
  },
  methods: {
    deleteData: function(){
           localStorage.clear('task')
        }
  },
  }
</script>