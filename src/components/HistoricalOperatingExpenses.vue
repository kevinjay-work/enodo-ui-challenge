<template>
  <!--<div>
    <table>
      <tr>
        <th></th>
        <th v-for="header in headers" :key="header">{{header}}</th> 
      </tr>
      <tr v-for="(row, i) in items" :key="i">
        <td>{{row.name}}</td>
        <td v-for="(value, x) in row.values" :key="x">{{value}}</td> 
      </tr>
    </table>
    </div>-->

<div class="property-table">
  <table class="table table-hover">
    <thead>
      <tr>
        <th>Historical Operating Expenses</th>
      </tr>
      <tr>
      </tr>
    </thead>
    <tbody>
     <tr>
        <th>-</th>
        <th v-for="header in headers" :key="header">{{header}}</th> 
      </tr>
      <tr v-for="(row, i) in items" :key="i">
        <td>{{row.name}}</td>
        <td v-for="(value, x) in row.values" :key="x">{{value}}</td> 
      </tr>
    </tbody>
  </table>
</div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class NavBar extends Vue {
    @Prop()
    private headers!: string[]

    @Prop()
    private items!: object[]

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.property-table{
  background-color: #384b61;
  padding-left: 10px !important;
  width:95%;
  display: block;
  border: 0.1px solid grey;
  margin-bottom: 41px;
/*   margin-top: -60px;
  margin-left:-40px; */
  
}
table {
  margin: 0px; 
}
</style>