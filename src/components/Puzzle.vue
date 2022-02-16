<template>
    <div class="grid">
      <draggable
        :list="images"
        :disabled="!enabled"
        class="list-group"
        ghost-class="ghost"
        :move="checkMove"
        @start="dragging = true"
        @end="dragging = false"
      >
        <img
          class="list-group-item"
          v-for="image in images"
          :key="image.url"
          :src="image.url"
        >
      </draggable>
  </div>
</template>

<script>

import draggable from "vuedraggable";
export default {
  name: "simple",
  display: "Simple",
  order: 0,
  components: {
    draggable
  },
  data() {
    return {
      enabled: true,
      images: [
        { url: require('../assets/img/11.png') },
        { url: require('../assets/img/16.png') },
        { url: require('../assets/img/20.png') },
        { url: require('../assets/img/8.png') },
        { url: require('../assets/img/2.png') },
        { url: require('../assets/img/14.png') },
        { url: require('../assets/img/23.png') },
        { url: require('../assets/img/6.png') },
        { url: require('../assets/img/19.png') },
        { url: require('../assets/img/10.png') },
        { url: require('../assets/img/22.png') },
        { url: require('../assets/img/25.png') },
        { url: require('../assets/img/4.png') },
        { url: require('../assets/img/9.png') },
        { url: require('../assets/img/18.png') },
        { url: require('../assets/img/15.png') },
        { url: require('../assets/img/1.png') },
        { url: require('../assets/img/7.png') },
        { url: require('../assets/img/17.png') },
        { url: require('../assets/img/3.png') },
        { url: require('../assets/img/24.png') },
        { url: require('../assets/img/12.png') },
        { url: require('../assets/img/21.png') },
        { url: require('../assets/img/5.png') },
        { url: require('../assets/img/13.png') }
      ],
      dragging: false
    };
  },
  computed: {
    draggingInfo() {
      return this.dragging ? "under drag" : "";
    }
  },
  methods: {
    checkMove: function(e) {
      window.console.log("Future index: " + e.draggedContext.futureIndex);
    }
  }
};
</script>

<style>

.grid {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.list-group {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(5, 1fr);
  column-gap: 1px;
  row-gap: 1px;
  width: 40rem;
}

.list-group-item {
  width: 8rem;
}

.ghost {
  opacity: 0.5;
  background: #c8ebfb;
}

img {
  width: 8rem;
  height: auto;
}
</style>