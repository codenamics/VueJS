<template>
  <div id="new-employee">
      <h3>new</h3>
      <div class="row">
        <form @submit.prevent="saveEmployee" class="col s12">
<div class="row">
  <div class="input-field col s12">
    <input type="text" v-model="employee_id">
    <label>ID</label>
  </div>
</div>
<div class="row">
  <div class="input-field col s12">
    <input type="text" v-model="name">
    <label>name</label>
  </div>
</div>
<div class="row">
  <div class="input-field col s12">
    <input type="text" v-model="dept">
    <label>dept</label>
  </div>
</div>
<div class="row">
  <div class="input-field col s12">
    <input type="text" v-model="position">
    <label>pos</label>
  </div>
</div>
<button type="submit" class="btn">sub</button>
<router-link to="/">back</router-link>
        </form>
      </div>
  </div>
</template>

<script>
import db from './firebaseInit'
export default {
  name: 'new-employee',
  data (){
      return{
         employee_id:null,
          name: null,
          position: null,
          dept: null
      }
  },
methods:{
  saveEmployee(){
    db.collection('employes').add({
          employe_id: this.employee_id,
          name: this.name,
          position: this.position,
          dept: this.dept
    })
    .then(docRef => {
      this.$router.push('/')
    })
  }
}
}
</script>