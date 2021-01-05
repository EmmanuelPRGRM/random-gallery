<template>
  <div id="title">
    <Gallery/>
  </div>
</template>

<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/1.0.18/vue.min.js"></script>
<script>
import Gallery from './components/Gallery';

export default
{
  name: 'app',
  components: { Gallery },
}
 new Vue({
  el: "#app",
  data: {
    images: [
      'https://picsum.photos/id/1003/200/300',
      'https://picsum.photos/id/1011/200/300',
      'https://picsum.photos/id/1020/200/300'
    ],
    selectedImage: null
  },
  methods: {
    randomItem (items) {
      return items[Math.floor(Math.random()*items.length)];
    }
  },
  created() {
    this.selectedImage = this.randomItem(this.images)
  }
})
</script>

<style>
#app {
  background: #fff;
  border-radius: 4px;
  padding: 20px;
  transition: all 0.2s;
}

li {
  margin: 8px 0;
}

h2 {
  font-weight: bold;
  margin-bottom: 15px;
}

del {
  color: rgba(0, 0, 0, 0.3);
}
</style>
