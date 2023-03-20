<script>
import draggable from "vuedraggable";

export default {
  name: 'App',
  components: {
    draggable
  },
  data(){
    return{
      newTask:"",
      arrBacklog:[
        {name: "Code Sign Up Page"},
        {name: "Test Dashboard"},
        {name: "Style Registration"},
        {name: "Help with Design"},
      ],
      arrInProgress:[],
      arrTested:[],
      arrDone:[]
    }
  
  },
  methods:{
    add(){
      if(this.newTask){
        this.arrBacklog.push({name: this.newTask});
        this.newTask="";
      }
    }
  }
}

</script>

<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col form-inline">
        <b-form-input v-model="newTask" placeholder="Enter Task" @keyup.enter="add"></b-form-input>
      </div>
    </div>
<div class="row">
  <div class="col md-3">
    <div class="p-2 alert alert-secondary">
      <h3>Backlog</h3>
      <draggable class="list-group" :list="arrBacklog" group="tasks">
        <div class="list-group-item" v-for="element in arrBacklog" :key="element.name">
        {{ element.name }}
        </div>
      </draggable>
    </div>
  </div>
</div>

  </div>
</template>

<style scoped>



</style>
