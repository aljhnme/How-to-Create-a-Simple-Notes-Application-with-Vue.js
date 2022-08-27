<template>
   <div class="ui centered card">
     <div class="content">
        <div class="header">
          {{ notesL.title }}
        </div>
        <div class="meta italic">
          {{ notesL.description }}
        </div>
        <div class='extra content'>
         <span class='right floated edit icon' v-on:click="showFedit">
           <i class='edit icon'></i>
        </span>
        <span class='right floated trash icon' v-on:click="DeleteNote(notesL)">
           <i class='trash icon'></i>
        </span>
      </div>       
     </div>
    <div class="content" v-show="showModelEdit">
      <div class='ui form'>
        <div class='field'>
          <label>Title</label>
          <input type='text' v-model="ThisEVnotesL.title">
        </div>
        <div class='field'>
          <label>Description</label>
          <input type='text' v-model="ThisEVnotesL.description">
        </div>
        <div class='ui two buttons'>
          <button class='ui basic button' v-on:click="saveEdF">
            Save
          </button>
        </div>
      </div>
    </div>     
   </div>
</template>
<script>
 export default {
   props:['notesL'],
   data(){
     return{
       showModelEdit:false,
       ThisEVnotesL:this.notesL,
     }
   },
   methods:{
    DeleteNote(notesL){
      this.$emit('DeleteN',notesL);
     },
     showFedit(){
       this.showModelEdit = true;
     },
     saveEdF(){
      this.showModelEdit = false;
     }
    }
  }
</script>
<style scoped>
  .italic {font-style: italic}
</style>
