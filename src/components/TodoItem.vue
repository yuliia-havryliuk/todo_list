<template>
    <li>
      <span v-bind:class="{done:todo.completed}">
          <input type="checkbox"
                 v-on:change="todo.completed= !todo.completed">
          <strong>{{index +1}}</strong>
          {{todo.title | uppercase}}
          <button class="rm" v-on:click="$emit('remove-todo',todo.id)"
          > &times;</button>
      </span>
    </li>
</template>

<script>
    export default {
        props:{
            todo:{
                type:Object,
                required: true
            },
            index: Number
        },
        filters: {
            uppercase(value){
                return value.toUpperCase()

            }
        }
    }
</script>

<style scoped>
li{
    display: flex;
    justify-content: space-between;
    padding: 1rem 2rem;
    margin-bottom: 1rem;

}
    .rm{
        background: #ff641e;
        color: beige;
        border-radius: 50%;
        font-weight: bold;
    }
input{
        margin-right: 1rem;
    }
strong{
    margin-right: 1rem;
}
    .done{
        text-decoration: line-through;
    }
</style>