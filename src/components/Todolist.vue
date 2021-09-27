 <template>
     <div clas="todo-list">
<!-- directive is a special token in the markup that allows the vue framework to do something to a element. -->
<!-- when we remove title property it shiws errorin console because title i sequired according to our script -->
    <Todoitem
       v-bind:title="'Walk the dog'"
      v-bind:description="'Go to forrest near the Zoo'" />

      <!-- this will only work when you want to describe in string case -->
    <Todoitem
      title="Buy a bread"
      description="Whole grain bread would be good"/>
    <Todoitem
      :title="todoTitle"
      :description="todoDescription" />
        </div>
        <!-- if we write"'todoTitle'" like this then we are sending string not variable -->
</template>
<script>
import Todoitem from '@/components/Todoitem'
export default {
  components: {
    Todoitem
     },
  data() {
    return {
      todoTitle: 'Learn Programming',
      todoDescription: 'Preferable Tomorrow!'
    }
  }
}
</script>
