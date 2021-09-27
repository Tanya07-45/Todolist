 <template>
     <div clas="todo-list">
<!-- directive is a special token in the markup that allows the vue framework to do something to a element. -->
<!-- when we remove title property it shiws errorin console because title i sequired according to our script -->
    <Todoitem
      v-for="todo in todos"
      :key="todo._id"
      :title="todo.title"
      :description="todo['description']" />
     
     
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
</style>
