 <template>
     <div class="todo-list">
<!-- directive is a special token in the markup that allows the vue framework to do something to a element. -->
<!-- when we remove title property it shiws errorin console because title i sequired according to our script -->
    <div v-if="todos && todos.length > 0">
      <Todoitem
        v-for="todo in todos"
        :key="todo._id"
        :_id="todo._id"
        :title="todo.title"
        :description="todo['description']" />
    </div>
      <div v-else class="no-todos">
      No todos :( Let's create one!
      </div>
     
     </div>

    
</template>
<script>
import Todoitem from '@/components/Todoitem'
export default {
  components: {
    Todoitem
     },
 props: {
    todos: {
      required: true,
      type: Array
    }
 }
}
</script>
<style scoped>
/* it is not working  */
  .todo-list {
    flex:1;
  }
  .no-todos {
    padding: 20px;
    font-size: 23px;
    font-weight: bold;
    text-align: center;
  }
</style>
