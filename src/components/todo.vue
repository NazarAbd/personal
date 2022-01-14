<template>
<div>
    <input type='text' id="val" name='todo' v-model="val" placeholder="Add a Todo...">
    <button @click="addTodo()">Add</button>
<ul>
   <li  v-for='todo in todos' :key='todo.id'>{{todo.text}}</li> 
</ul>
</div>
</template>
<script>
export default{
     name: 'HelloWorld',
    data(){
        return{
            todos:[ 
                { id:0 , text: 'do something' },
                { id:1, text: 'do another thing'}
            ]
        }
    },
    methods:{
        addTodo(){
             let x = { id: Math.random(), text : val.value};
             console.log(x);
            //  console.log( { id: Math.random(), text : val.value});
             this.todos = this.todos.push( { id: Math.random(), text : val.value});
        },
    }
}
</script>
<style scoped>
*{
    box-sizing:border-box;
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
    font-size:14px;
}
</style>