<template>
  <div class="header-nav">
    
    
    <div class="navbar-header">
      <p class="navbar-brand">Property Analysis</p>
    </div>
    <ul class="nav navbar-nav">
      <li class="active"><a href="#">{{property.address}}</a></li>
    </ul>
    <ul class="nav navbar-nav button">
      <li><button class='btn btn-default share'>Share</button></li>
      <li><button class='btn btn-success'>Export</button></li>
    </ul>
  
    <!--<div>
      Property Analysis
    </div>
    <div>
      {{property.name ? property.name : property.address}}
    </div>
    <button type="button">Share</button>
    <button type="button">Export</button>-->
    <div class="clear"></div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class SecondNavBar extends Vue {
    @Prop()
    private property!: object
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header-nav{
  background-color:white !important;
  padding:0px 30px 0px 10px;
  height:55px;
  margin-top: -20px;
}
.share{
  margin-right:10px;
  border:1px solid green;
  color:green;
}
.button{
 float:right;
  margin-top:10px;
}
</style>