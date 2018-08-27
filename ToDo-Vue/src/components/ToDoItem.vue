<template>
    <li class="todo-item">
         <div  class="todo-item-left">
              <input 
              type="checkbox" 
              v-model="completed"
              @change="doneEdit"
              >
            <div 
            class="todo-item-label"
            v-if="!editing"
            @dblclick="editToDo"
            :class="{completed : completed}"
            >{{title}}</div>
            <input
            @blur="doneEdit"
            @keyup.enter="doneEdit"
            @keyup.esc="cancelEdit"
            v-else 
            class="todo-item-edit" 
            type="text" 
            v-model="title"
            v-focus
            >
            </div>
            <div>
              <button @click="pluralize">Plural</button>
              <span 
                class="removeTodo"
                @click="removeTodo(index)"
                >
                  &times;
              </span>
            </div>
                
    </li>
</template>

<script>
export default {
  name: "ToDoItem",
  props: {
    item: {
      type: Object,
      required: true
    },
    index: {
      type: Number,
      required: true
    },
    checkAll: {
      type: Boolean,
      required: true
    }
  },
  data() {
    //this data is coming form the prop (item)
    return {
      id: this.item.id,
      title: this.item.title,
      completed: this.item.completed,
      editing: this.item.editing,
      beforeEditCache: ""
    };
  },
  directives: {
    focus: {
      // directive definition
      inserted: function(el) {
        el.focus();
      }
    }
  },
  watch: {
    checkAll() {
      if (this.checkAll) {
        this.completed = true;
      } else {
        this.completed = this.item.completed;
      }
    }
  },
  created() {
    eventBus.$on("pluralize", this.handlePluralize);
  },
  beforeDestroy() {
    eventBus.$off("pluralize", this.handlePluralize);
  },
  methods: {
    removeTodo(index) {
      eventBus.$emit("removedTodo", index);
    },
    editToDo() {
      this.editing = true;
      this.beforeEditCache = this.title;
    },
    doneEdit() {
      if (this.title === "" || this.title.trim() === "") {
        this.title = this.beforeEditCache;
      }
      this.editing = false;
      eventBus.$emit("finishedEdit", {
        index: this.index,
        item: {
          id: this.id,
          title: this.title,
          completed: this.completed,
          editing: this.editing
        }
      });
    },
    cancelEdit() {
      this.title = this.beforeEditCache;
      this.editing = false;
    },
    pluralize() {
      eventBus.$emit("pluralize");
    },
    handlePluralize() {
      this.title = this.title + "s";
      eventBus.$emit("finishedEdit", {
        index: this.index,
        item: {
          id: this.id,
          title: this.title,
          completed: this.completed,
          editing: this.editing
        }
      });
    }
  }
};
</script>

<style lang="scss" scoped>
.todo-item {
  display: flex;
  justify-content: space-between;
  padding: 5px 10px;
  .removeTodo {
    font-size: 26px;
    cursor: pointer;
  }
  animation-duration: 0.3s;
}
.todo-item-left {
  display: flex;
  align-items: center;
}
.todo-item-label {
  padding: 10px;

  margin-left: 12px;
}
.todo-item-edit {
  font-size: 24px;
  color: #2c3e50;
  margin-left: 12px;
  width: 100%;
  padding: 10px;
  border: 1px solid rgba(51, 51, 51, 0.068);
  &:focus {
    outline: none;
  }
}
.completed {
  text-decoration: line-through;
}
</style>
