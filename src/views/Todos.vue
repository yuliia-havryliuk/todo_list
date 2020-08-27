 <template>
        <div>
            <h2> What do you plan today? :)</h2>
            <router-link to="/">
                <img src="https://avatanplus.com/files/resources/original/57a726e809c0715664effa68.png">
            </router-link>
            <div class ="addAndSelect">
                <AddTodo
                        @add-todo="addTodo"/>
                <select v-model="filter">
                    <option value="all">All</option>
                    <option value="completed">Completed</option>
                    <option value="not-completed">Not Completed</option>
                </select>
            </div>
            <Loader v-if ="loading" />
            <TodoList
                    v-else-if="filteredTodos.length"
                    v-bind:todos1="filteredTodos"
                    @remove-todo="removeTodo"
            />
            <p v-else> No todos!</p>
        </div>
    </template>

 <script>
    import TodoList from '@/components/TodoList'
    import AddTodo from '@/components/AddTodo'
    import Loader from '@/components/Loader'
    export default {
        name: 'App',
        data() {
            return {
                todos: [],
                loading: true,
                filter: 'all'
            }
        },
        mounted() {
            fetch('https://jsonplaceholder.typicode.com/todos?_limit=3')
                .then(response => response.json())
                .then(json => {
                    // setTimeout(() =>{
                        this.todos = json
                        this.loading = false
                    // }, 1000)
                })
        },
        //     watch:{
        //         filter(value){
        // }
        //     },
        computed: {
            // eslint-disable-next-line vue/return-in-computed-property
            filteredTodos(){
                if (this.filter === 'all') {
                    return this.todos
                }
                if (this.filter === 'completed') {
                    return this.todos.filter(t => t.completed)
                }
                if (this.filter === 'not-completed') {
                    return this.todos.filter(t => !t.completed)
                }
            }
        },
        methods: {
            removeTodo(id) {
                this.todos = this.todos.filter(t => t.id !== id)
            },
            addTodo(todo) {
                this.todos.push(todo)
            }
        },
        components: {
            TodoList, AddTodo, Loader
        }
    }

</script>

<style scoped>
select{
    display: inline-block;
    width: 160px;
    height: 30px;
    line-height: 30px;
    margin: 5px 5px 5px 5px;
}
img{
    max-width: 90px;
    max-height: 90px;
}
</style>