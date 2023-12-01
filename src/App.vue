<template>
  <div>
    <div class="map__and__links">
      <Floor1 />
      <Img />
      <AppartmensView/>
    </div>
    <Search style="margin-top: 140px;"/>
  </div>
</template>

<script>

import Floor1 from './components/FloorView.vue';
import Img from './components/ImgView.vue';
import AppartmensView from './components/AppartmensView.vue';
import Search from './components/SearchView.vue';

export default {
  name: 'App',
  components: {
    Floor1,
    Img,
    AppartmensView,
    Search,
    
  }
}
</script>

<style>
.map__and__links{
  display: flex;
  justify-content: space-around;
  align-items: center;
}
</style>
