<template>
<div v-if="todos.length">
    <input @keypress.enter="addTodo()" type='text' name='todo' v-model="val" placeholder="Add a Todo...">
    <button @click="addTodo()">Add</button>
<ul>
   <li @click="delTodo(todo.text)"  :class='{ "completed" : todo.comp }'  v-for='todo in todos' :key='todo.text' v-text='todo.text'></li>
</ul>
</div>
<div v-else>Oops! Nothing left to do :)</div>
</template>
<script>
export default{
     name: 'HelloWorld',
    data(){
        return{
            some:true,
            val :'',
            todos:[
                {text:'wake Up' , comp:true},
                {text:'clean Room',comp:true},
                {text:'Do some coding',comp:false},
                {text:'Go to work',comp:false},
                ]
        }
    },
    methods:{
        addTodo() {

            let newtodo = {text:this.val,comp:false}
           this.todos.push(newtodo)
           this.val = '';
           
        },
       toggleClass(todo){
           todo.comp = !todo.comp;
           
        //   for(let i =0 ; i<this.todos.length; i++){
        //     //   console.log(this.todos[i].text)
        //     if(this.todos[i].text == todo){
        //         // let to = this.todos[i];
        //         this.todos[i].comp = !this.todos[i].comp;
        //     // console.log(to)
        //     }
        //   }
       },
       delTodo(id)
       {
           this.todos = this.todos.filter(todo=> todo.text != id)
        //   for(let i =0 ; i<this.todos.length; i++){
        //     //   console.log(this.todos[i].text)
        //     if(this.todos[i].text == todo){
        //         let to = {text:this.todos[i].text, comp:this.todos[i].comp};
        //         console.log(to)
        //         this.todos.filter(function(to){
        //             // if(this.todos.to)
        //         })
        //         // this.todos[i].comp = !this.todos[i].comp;
        //         // this.todos.filter(to => !this.todos.to)
        //     // console.log(to)
        //     }
        //   }
       }
    }
}
</script>
<style scoped>
*{
    box-sizing:border-box;
    font-family:sans-serif; 
}
.completed{
    border-right:2px #228822 solid;
}
div{
    width:500px;
    margin:auto;
}
input{
    width:80%;
    height:40px;
    border:1px darkgrey solid;
    border-radius:5px;
    background:#eee;
    padding-right:10px;
    padding-left:10px;
}
button{
    width:calc((100% - 80%) - 2px);
    height:40px;
    background:#228822;
    border:none;
    border-radius:5px;
    margin-left:2px;
    color:white;
    cursor:pointer;
}
ul{
    width:100%;
    list-style:none;
    padding:0;
    margin:0;
    margin-top:70px;
}
li{
    width:100%;
    display:flex;
    justify-content:flex-start;
    align-items:center;
    height:40px;
    margin-top:10px;
    border-radius:5px;
    background:#eee;
    padding-right:10px;
    padding-left:10px;
    font-size:16px;
    font-weight:bold;
    border-top-right-radius:0;
    border-bottom-right-radius:0;
     border-right:2px red solid;
     cursor: pointer;
}
</style>