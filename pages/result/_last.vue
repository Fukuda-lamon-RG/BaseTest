<template>
<div class="container">
  <div class="row">
    <div class="text-center col">
       {{ $route.params.id }}点！
        <p>「Yes」で+1「No」で+0</p>
    </div>
  </div>
    <div v-if="resultsNum == 0">
      <p>ズバリあなたはリザードン</p>
      <Result1 />
    </div>
    <div v-else-if="resultsNum>=1 && resultsNum<=3">
      <p>ズバリあなたカメックス</p>
       <Result2 />
    </div>
    <div v-else-if="resultsNum>=4 && resultsNum<=5">
      <p>ズバリあなたはフシギバナ</p>
      <Result3 />
    </div>
  <div class="row">
    <div class="text-center col">
      <nuxt-link to="/">Topへ戻る</nuxt-link>
    </div>
  </div>
</div>
</template>

<script lang="ts">
import Vue from 'vue'
import Result1 from '../../components/results/Result1.vue';
import Result2 from '../../components/results/Result2.vue';
import Result3 from '../../components/results/Result3.vue';

export default Vue.extend({
components: {
  Result1,
  Result2,
  Result3,
},
  data() {
    return {
      resultsNum: Number(this.$route.params.id),
    }
  },
  computed: {

  }
})
</script>

<style scoped>

</style>



