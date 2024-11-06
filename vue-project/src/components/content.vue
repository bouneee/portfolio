<script>
export default{
    data(){
        return{
            task:'',
            listTask:[],
            pic:'',
        }
    },
    methods:{
        addTask(){
            this.listTask.push(this.task);
            this.task = '';
        },
        sortTask(){
            this.listTask.sort();
        },
        del(){
            delete this.listTask[this.pic]
        }
    }
}
</script>
<template>  
<div class="content">
    <div class="container">
        <h3>Add task</h3>
        <input type="text" class="i1" v-model="task"> <input type="button" value="Add" class="i2" @click="addTask()">
        <h3>Tasks</h3>
        <ul class="tasks">
            <li v-for="(i, index) in listTask"> <input type="radio" name="task" :value="index" v-model="pic" class="checked">{{ i }}</li>
        </ul>
        <input type="button" class="sortbtn" value="Sort" @click="sortTask()"><input type="button" class="delbtn" value="Delete" @click="del()">
    </div>
</div>
    
</template>

<style scoped>
.container{
    width: 80%;
    margin: 75px auto;
    padding: 25px;
    background-color: rgb(178, 179, 249);

}
.i1{
    width: 70%;
    height: 35px;
    border: 1px color(#000001);
    border-radius: 5px;
    margin-right: 10px;
    margin-top: 10px;
    margin-bottom: 10px;
    font-size: 20px;
}
.i2{
    font-size: 20px;
    width: 20%;
    height: 35px;
    border: none;
    margin-top: 10px;
    margin-bottom: 10px;
    background-color: rgb(36, 18, 110);
    text-transform: uppercase;
    color: aliceblue;
}
.i2:hover{
    background-color: rgb(31, 21, 81);
}
.container h3{
    font-size: 20px;
    text-transform: uppercase;
    margin-right: 10px;
    margin-left: 10px;
}
.tasks{
    margin-top: 10px;
    margin-bottom: 10px;
    font-size: 16spx;
    display: flex;
    flex-direction: column;

}
li{
    padding-top: 5px;
}
.sortbtn{
    font-size: 15px;
    width: 7%;
    height: 25px;
    border: none;
    background-color: rgb(137, 109, 250);
    margin-right: 10px;
}
.sortbtn:hover{
    background-color: rgb(122, 105, 192);
}
.delbtn{
    font-size: 15px;
    width: 7%;
    height: 25px;
    border: none;
    background-color: rgb(137, 109, 250);
    margin-right: 10px;
}
.delbtn:hover{
    background-color: rgb(122, 105, 192);
}
.checked{
    margin-right: 3px;
    width: 17px;
    height: 17px;
}
</style>