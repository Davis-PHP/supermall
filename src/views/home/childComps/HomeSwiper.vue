<template>
  <div>
    <swiper>
      <swiper-item v-for="item in banner">
        <a :href="item.link">
          <img :src="item.image" :alt="item.title" @load="imgLoad">
        </a>
      </swiper-item>
    </swiper>
  </div>
</template>

<script>
  import {Swiper, SwiperItem} from 'components/common/swiper'

  export default {
    name: "HomeSwiper",
    props: {
      banner: {
        type: Array,
        default() {
          return []
        }
      }
    },
    data() {
      return {
        isLoad: false
      }
    },
    components: {
      Swiper,
      SwiperItem
    },
    methods: {
      imgLoad() {
        if (!this.isLoad) {
          this.$emit('swiperImgLoad');
          this.isLoad = true;
        }
      }
    }
  }
</script>

<style scoped>

</style>
