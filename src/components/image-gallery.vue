<template>
  <div v-if="isOpen" class="backdrop" @click="closeHandler">
    <div class="imageGallery">
      <div class="close" @click.stop="closeHandler">
        &cross;
      </div>
      <div class="bigImage">
        <img :src="imageUrls.highres[activeImage]"/>
      </div>
      <ul class="thumbnails">
        <li
          class="item"
          v-for="(thumbnailUrl, index) in imageUrls.thumbnails"
          @click.stop="activeImage = index"
        >
          <img :src="thumbnailUrl">
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {
    name: "HelloWorld",
    props: ['imageUrls', 'isOpen'],
    data () {
      return {
        activeImage: 0
      };
    },
    methods: {
      closeHandler() {
        console.log('close')
        this.$emit('closed')
      }
    }
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .imageGallery {
    position: fixed;
    top: 5%;
    height: 90vh;
    width: 90vw;
    max-width: 960px;
    overflow: auto;
    left: 45vw;
    margin-left: -25vw;
    background-color: white;
    padding-top: 2vh;
  }
  .item {
    padding: 20px 20px 0 20px;
    cursor: pointer;
  }
  .thumbnails {
    display: flex;
    list-style-type: none;
    padding: 0;
    position: absolute;
    bottom: 0;
    height: 20vh;
    img {
      height: 100%;
    }
  }
  .bigImage {
    height: 70vh;
    img {
      height: 100%;
    }
  }
  .close {
    position: absolute;
    right: 0;
    top: 0;
    padding: 10px 20px;
    cursor: pointer;
  }
  .backdrop {
    position: fixed;
    width: 100vw;
    height: 100vh;
    top: 0;
    left: 0;
    margin: 0;
    padding: 0;
    background-color: rgba(0, 0, 0, .5);
  }
</style>
