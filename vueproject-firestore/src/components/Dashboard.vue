<template>
  <div id="dashboard">
     <ul class="collection with-header">
       <li class="collection-header">
         <h4>Employees</h4>
       </li>
<li v-for="employee in employees" v-bind:key="employee.id" class="collection-item">
  <div class="chip">{{employee.dept}}:{{employee.employee_id}}</div>{{employee.name}}
  <router-link class="secondary-content" v-bind:to="{name: 'view-employee', params: {employee_id: employee.employee_id}}"><i class="fa fa-eye"></i></router-link>
</li>
     </ul>
      <div class="fixed-action-btn">
        <router-link to="/new" class="btn-floating yellow">
        <i class="fa fa-plus"></i>
        </router-link>
      </div>
  </div>
  
</template>

<script>
import db from './firebaseInit'
export default {
  name: 'dashboard',
  data (){
      return{
    employees:[]
      }
  },
  created (){
    db.collection('employes')
    .get()
    .then(querySnapshot =>{
      querySnapshot.forEach(doc =>{     
        const data = {
          'id': doc.id,
          'employee_id':doc.data().employe_id,
          'name': doc.data().name,
          'position': doc.data().position,
          'dept': doc.data().dept
        }
        this.employees.push(data)
      })
    })
  }
}
</script>
