<template>
  <CreateNote v-on:SeDataToCnote="CreateNote"/>
  <ListNote v-bind:notesd="notes"/>
</template>

<script>
import CreateNote from './components/create-notes.vue';
import ListNote from './components/ListNotes.vue';

export default {
  name: 'App',
  components:{
    CreateNote,
    ListNote,
  },
  data(){
    return{
       notes:[
        {
           title:"My friend",
           description:"Visiting my friend who came from travel",
        },{
           title:"Play",
           description:"Playing football with my favorite team",
        },{
           title:"carry out tasks",
           description:"Do the things on your to-do list at the weekend'",
        }],
     }
  },
  methods:{
    CreateNote(note){
      this.notes.push(note);
      alert("Note added");
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
