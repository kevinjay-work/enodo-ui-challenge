<template>
  <div class="propt-summery">
    <!--<div class="image">
      <img src="https://maps.googleapis.com/maps/api/streetview?size=400x200&pitch=10&fov=180&location=320%20N%20Canal%20St,%20Chicago,%20IL%2060606&key=AIzaSyApsGVNO-Ms2sIJM4PtmwC5VfeutsZSExo"></br>
        <!-- Name: {{property.name}} 
       Street Address: {{property.address}}  </br>
        # Units: {{property.numberUnits ? property.numberUnits : '240'}} /
        Type: {{property.propetyType ? property.propetyType : 'Garden'}} /
        Year Build: {{property.yearBuild ? property.yearBuild : '2020'}}</br>
        AVM: {{property.avm ? property.avm : '--'}}
    </div>
        <LateralNav :options="propertySections" />  -->
  
  <div class="card" >
    <img class="card-img-top" src="https://maps.googleapis.com/maps/api/streetview?size=400x200&pitch=10&fov=180&location=320%20N%20Canal%20St,%20Chicago,%20IL%2060606&key=AIzaSyApsGVNO-Ms2sIJM4PtmwC5VfeutsZSExo" alt="Card image" style="width:100%">
  <div class="card-body">
    <h4 class="card-title">{{property.address}} </h4>
    <p class="card-text">{{property.numberUnits ? property.numberUnits : '240'}} Units / {{property.propetyType ? property.propetyType : 'Garden'}} /
        {{property.yearBuild ? property.yearBuild : '2020'}}</p>
    <p class="card-title avm">AVM: ${{property.avm ? property.avm : '--'}}</p>
  </div>
    <LateralNav :options="propertySections" />
  </div>
  </div>
  
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'
import LateralNav from './LateralNav.vue'


@Component({
  components: {
    LateralNav
  }
})
export default class NavBar extends Vue {
    @Prop()
    private property!: object

    private propertySections: object[] = [
      {name: 'Comparables', icon: '<span class="glyphicon glyphicon-equalizer"></span>', selected: false},
      {name: 'Operating Expenses', icon: '<span class="glyphicon glyphicon-usd"></span>', selected: true},
      {name: 'Rent roll / Unit Mix', icon: '<span class="glyphicon glyphicon-th"></span>', selected: false},
      {name: 'Amenities', icon: '<span class="glyphicon glyphicon-star-empty"></span>', selected: false},
      {name: 'Market', icon: '<span class="glyphicon glyphicon-map-marker"></span>', selected: false}
    ]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.propt-summery{
  background-color:white;
  width:20%;
  float: left;
  // margin:30px 0px 0px 100px;
}
.card-title
{
  font-weight:bold;
}
.avm{
  color:green;
}
.card-text, .card-title{
  padding-left:15px
}
</style>