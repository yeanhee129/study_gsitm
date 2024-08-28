<template>
    <div class="detail_box">
        <div v-for="counsel in CounselData" :key="counsel">
            <p v-if="cus_id==counsel.cus_id">
              {{ counsel.date + ' ' + counsel.time + ' ' + counsel.content }}
            </p>
        </div>
    </div>
</template>

<script>
import CounselData from '../assets/counsel.js';

export default {
    name : 'ConselVue',

    data() {
      return {
        CounselData: CounselData,
      }
    },

    props : {
        cus_id : Number,
    },
}
</script>

<style>

</style>
