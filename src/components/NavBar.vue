<template>
  <div>
  <nav class="navbar">
  <div class="container-fluid">
    <div class="navbar-header">
      <a class="navbar-brand" href="#"><img src="../assets/logo.png" style="width:60px;height:45px;margin-top:-10px"/></a>
    </div>
    <ul class="nav navbar-nav">
      <li v-for="item in menuItems" :key="item.name" :class="item.active ? 'active' : ''" class="active"><a href="#">{{item.name}}</a></li>
      <li><a href="#">Go To Platform</a></li>
      <li><a href="#">{{userInitials}}</a></li>
    </ul>
  </div>
</nav>
  <!--  <div>
      <a v-for="item in menuItems" :key="item.name" :class="item.active ? 'active' : ''">{{item.name}}</a>
    </div>
    <div>
      <a>Go To Platform</a>
    </div>
    <div>
      <a>{{userInitials}}</a>
    </div>-->
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class NavBar extends Vue {
    @Prop()
    private userInitials!: string

    @Prop()
    private menuItems!: object[]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.navbar{
  background-color:#384B61;
  height:70px !important;
  padding:10px;
}

.navbar-nav{
  float:right;
}
a{
  color:white;
}
a:hover
{
  color:black;
}
</style>