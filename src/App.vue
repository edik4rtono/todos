<template>
   <div class="container">
		<div class="row justify-content-center">
			<div class="col-md-6">
				<h1 class="text-center">Todolist</h1>
				<hr>
				<input type="text" class="form-control" placeholder="Input todolist & enter" v-model="todos.name" v-on:keyup.enter="addTodo" >
        <button>+</button>
       
				<hr>
				<ul class="list-group">
					<li class="list-item" v-for="item in todos">{{ item.name }}</li>
				</ul>
			</div>
		</div>
	</div>
  
</template>

<script>
import { mapMutations, mapActions, mapState }  from 'vuex'

export default {

  
  data: () => {
		return {
			todos: [
				{
					name: 'Todo 1',
					done: true,
				},
				{
					name: 'Todo 2',
					done: false,
				},
				{
					name: 'Todo 3',
					done: false,
				},	
			],
			todos: {
				name: '',
				done: false
			}
		}},
  
  methods: {
    addTodo() {
      
       
      if(this.todos.name != ''){
        // alert(this.todos.name);
        console.log(this.todos.name)
        // this.todos.push(this.todos)
				this.todos = {
					name: '',
					done: false
        }
        
      }
     
      // this.homeScore = value;
    },
    
    
   
    
  },

};
</script>