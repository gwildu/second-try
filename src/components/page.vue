<template>
  <div>
    <img
      @click="imageClicked"
      src="//static.digitecgalaxus.ch/Files/6/9/5/6/2/5/2/galaxy-s7_gallery_left_black.png?fit=inside%7C343:832&output-format=progressive-jpeg" />
    <ImageGallery
      :imageUrls="imageUrls"
      :isOpen="isGalleryOpen"
      @closed="galleryClosed"
    />
  </div>
</template>

<script>
  import ImageGallery from './image-gallery'

  export default {
    name: "page",
    data() {
      return {
        isGalleryOpen: false,
        imageUrls: {
          highres: [
            "//static.digitecgalaxus.ch/Files/6/9/5/6/2/5/2/galaxy-s7_gallery_left_black.png?fit=inside%7C343:832&output-format=progressive-jpeg",
            "//static.digitecgalaxus.ch/Files/6/9/5/6/2/5/3/galaxy-s7_gallery_left-side_black.png?fit=inside%7C46:807&output-format=progressive-jpeg",
            "//static.digitecgalaxus.ch/Files/6/9/5/6/2/5/4/galaxy-s7_gallery_back_black.png?fit=inside%7C395:796&output-format=progressive-jpeg",
            "//static.digitecgalaxus.ch/Files/6/9/5/6/2/5/1/galaxy-s7_gallery_right-side_black.png?fit=inside%7C46:808&output-format=progressive-jpeg"
          ],
          thumbnails: [
            "//static.digitecgalaxus.ch/Files/6/9/5/6/2/5/2/galaxy-s7_gallery_left_black.png?fit=inside%7C144:96&output-format=progressive-jpeg",
            "//static.digitecgalaxus.ch/Files/6/9/5/6/2/5/3/galaxy-s7_gallery_left-side_black.png?fit=inside%7C144:96&output-format=progressive-jpeg",
            "//static.digitecgalaxus.ch/Files/6/9/5/6/2/5/4/galaxy-s7_gallery_back_black.png?fit=inside%7C144:96&output-format=progressive-jpeg",
            "//static.digitecgalaxus.ch/Files/6/9/5/6/2/5/1/galaxy-s7_gallery_right-side_black.png?fit=inside%7C144:96&output-format=progressive-jpeg"
          ]
        }
      }
    },
    components: {
      ImageGallery
    },
    methods: {
      imageClicked () {
        this.isGalleryOpen = true;
      },
      galleryClosed (e) {
        this.isGalleryOpen = false;
      }
    }
  }
</script>

<style scoped>

</style>
