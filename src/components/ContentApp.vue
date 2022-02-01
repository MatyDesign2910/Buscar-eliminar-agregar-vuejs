<template>
  <div id="contenedor">
    <Search v-on:query-change="querySearch"></Search>
    <v-main>
      <v-container class="px-9 py-9">
        <v-row>
          <v-col cols="12">
            <h2>Categoría</h2>
            <TodoAdd v-on:add-todo="addTodo"></TodoAdd>
            <Todo
              v-bind:todolist="copyTodo"
              v-on:delete-todo="deleteTodo"
            ></Todo>
            <!--<Card></Card>-->
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </div>
</template>

<script>
//import Card from './Card.vue';
import Todo from "./Todo.vue";
import TodoAdd from "./TodoAdd.vue";
import Search from './Search.vue';
//import TodoItem from './TodoItem.vue';

export default {
  name: "ContentApp",
  components: {
    //Card,
    Todo,
    TodoAdd,
    Search,
    //TodoItem,
  },
  methods: {
    deleteTodo(id) {
      this.todo = this.todo.filter((todo) => todo.id != id);
      this.copyTodo = [...this.todo];
    },
    addTodo(todo) {
      this.todo.push(todo);
      this.copyTodo = [...this.todo];
    },
    querySearch(query) {
      if (query.trim() === "") {
        this.copyTodo = [...this.todo];
      } else {
        const temp = this.todo.filter(todo =>{
          return todo.title.includes(query);
        });
        this.copyTodo = [...temp];
      }
    },
  },

  data() {
    return {
      todo: [
        {
          id: 0,
          title: "Collar de perro",
          completed: false,
        },
        {
          id: 1,
          title: "Comida de gato",
          completed: false,
        },
        {
          id: 2,
          title: "Capa de salchicha",
          completed: false,
        },
        {
          id: 3,
          title: "Hueso de juguete",
          completed: true,
        },
      ],
      copyTodo: [
        {
          id: 0,
          title: "Collar de perro",
          completed: false,
        },
        {
          id: 1,
          title: "Comida de gato",
          completed: false,
        },
        {
          id: 2,
          title: "Capa de salchicha",
          completed: false,
        },
        {
          id: 3,
          title: "Hueso de juguete",
          completed: true,
        },
      ],
    };
  },
  created() {
    this.copyTodo = [...this.todo];
  },
};
</script>
