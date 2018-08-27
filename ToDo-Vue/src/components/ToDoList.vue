<template>
    <div>
        <input type="text"
        v-model="newTodo"
        class="todo-input"
        @keyup.enter="addTodo"
        >
        <ul>
          <transition-group 
          enter-active-class="animated fadeInUp"
          leave-active-class="animated fadeOutDown"
          >
            <ToDoItem
            v-for="(item, index) in todosFiltered"
            :key="item.id"
            :item="item"
            :index="index"
            :checkAll="!anyRemaining" 
            />
            </transition-group>
        </ul>
        <div class="extra-container">
          <Todocheckall :anyRemaining="anyRemaining"/>
            <Todoitemsremaining :remaining="remaining"/>
          
        </div>
         <div class="extra-container">
     <todofiltered/>

      <div>
        <transition name="fade">
        <Todoclearcompleted
        :showClearCompletedButton="showClearCompletedButton"
        />
        </transition>
      </div>

    </div>
    </div>
</template>

<script>
import ToDoItem from "./ToDoItem";
import Todoitemsremaining from "./Todoitemsremaining";
import Todocheckall from "./Todocheckall";
import Todofiltered from "./Todofiltered";
import Todoclearcompleted from "./Todoclearcompleted";
export default {
  name: "ToDoList",
  components: {
    ToDoItem,
    Todoitemsremaining,
    Todocheckall,
    Todofiltered,
    Todoclearcompleted
  },
  data() {
    return {
      filter: "all",
      beforeEditCache: "",
      idToDo: 3,
      newTodo: "",
      todos: [
        {
          id: 1,
          title: "one",
          completed: false,
          editing: false
        },
        {
          id: 2,
          title: "tow",
          completed: false,
          editing: false
        }
      ]
    };
  },
  created() {
    eventBus.$on("removedTodo", index => this.removeTodo(index));
    eventBus.$on("finishedEdit", data => this.finishedEdit(data));
    eventBus.$on("checkAllChanged", checked => this.checkAllTodo(checked));
    eventBus.$on("filterChanged", filter => (this.filter = filter));
    eventBus.$on("clearCompletedTodos", () => this.clearCompleted());
  },
  beforeDestroy() {
    eventBus.$off("removedTodo");
    eventBus.$off("finishedEdit");
    eventBus.$off("checkAllChanged");
    eventBus.$off("filterChanged");
    eventBus.$off("clearCompletedTodos");
  },
  computed: {
    remaining() {
      return this.todos.filter(item => !item.completed).length;
    },
    anyRemaining() {
      return this.remaining;
    },
    todosFiltered() {
      if (this.filter == "active") {
        return this.todos.filter(item => !item.completed);
      } else if (this.filter == "completed") {
        return this.todos.filter(item => item.completed);
      }
      return this.todos;
    },
    showClearCompletedButton() {
      return this.todos.filter(item => item.completed).length > 0;
    }
  },
  methods: {
    addTodo() {
      if (this.newTodo !== "" && this.newTodo.trim() !== "") {
        this.todos.push({
          id: this.idToDo,
          title: this.newTodo,
          completed: false,
          editing: false
        });
        this.newTodo = "";
        this.idToDo++;
      }
    },
    removeTodo(index) {
      this.todos.splice(index, 1);
    },
    checkAllTodo() {
      this.todos.forEach(item => (item.completed = event.target.checked));
    },
    clearCompleted() {
      this.todos = this.todos.filter(item => !item.completed);
    },
    finishedEdit(data) {
      this.todos.splice(data.index, 1, data.item);
    }
  }
};
</script>

<style lang="scss" scoped>
ul {
  list-style: none;
  padding: 0;
  text-align: left;
}
.todo-input {
  width: 100%;
  border: 1px solid rgba(51, 51, 51, 0.068);
  padding: 10px 15px;
  font-size: 20px;
  &:focus {
    outline: none;
  }
}

.extra-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 16px;
  border-top: 1px solid lightgrey;
  padding-top: 14px;
  margin-bottom: 14px;
}

.active {
  background: lightgreen;
}
// CSS Transitions
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>

