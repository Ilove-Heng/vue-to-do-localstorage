<script>
import { toRef , onMounted,computed,watch,reactive} from 'vue';
setup(){
    const state = reactive({
      todos : [],
      name  : '',
      input_content: '',
      input_category = null,
    })
       const todos_asc = computed(()=> state.todos.sort((a,b)=> {
         return b.createdAt - a.createdAt
       }))


  return {
      ...toRef(state),
      todos_asc,
  }
}
</script>

<template>
  <main class="app">
    <section class="greeting">
      <h2 class="title">
        What's up, <input type="text" placeholder="Name here" v-model="name" />
      </h2>
    </section>
  </main>
</template>

<style scoped></style>
