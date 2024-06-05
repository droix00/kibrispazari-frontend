<template>
  <div>
    <Header/>
    <content/>
    
  </div>
</template>
<script>
import Header from '~/pages/Header.vue'; 
import content from '~/pages/content.vue'; // Header bileşenini içeri aktar

export default {
  components: {
    Header, content // Header bileşenini kullanılabilir hale getir
  }
}
</script>

<style scoped>
/* Index sayfasına özgü stiller buraya gelir */
</style>
