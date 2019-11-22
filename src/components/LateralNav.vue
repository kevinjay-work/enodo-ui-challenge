<template>
  <div>
     
    <div class="lateral" v-for="(value, x) in options" :key="x" :class="value.selected ? 'selected' : ''">
      <span v-html="value.icon"></span> {{value.name}}
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class NavBar extends Vue {
    @Prop()
    private options!: object[]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.lateral{
  padding-left:10px;
  padding-top:10px;
  font-weight:550;
  height:40px;
}

.lateral:hover{
  background-color:#384B61;
  height:40px;
  color:white;
  font-weight:300;
  padding-top:10px
}
span{
  color:green;
  padding-right:8px;
}

</style>