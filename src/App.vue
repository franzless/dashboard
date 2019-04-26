<template>
  <v-app>
    <toolbar/>    
      <router-view/>
   
  </v-app>
</template>

<script>
import toolbar from '@/components/Core/toolbar'
export default {
  components:{toolbar} ,
  name: 'App',
  data () {
    return {
      //
    }
  }
}
</script>
