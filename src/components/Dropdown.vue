<template>
  <div class="menu-item" @click="isOpen = !isOpen">
    <a href="#">
      {{ title }}
    </a>
    <svg viewBox="0 0 320 512">
      <path
        d="M41 288h238c21.4 0 32.1 25.9 17 41L177 448c-9.4 9.4-24.6 9.4-33.9 0L24 329c-15.1-15.1-4.4-41 17-41z"
        fill="#fff"
      ></path>
    </svg>
    <transition name="fade">
      <div class="sub-menu" v-if="isOpen">
        <div v-for="(item, index) in items" :key="index" class="menu-item">
          <a :href="item.link">
            {{ item.title }}
          </a>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  props: ["title", "items"],
  setup() {
    const isOpen = ref(false);

    return {
      isOpen,
    };
  },
};
</script>

<style>
nav .menu-item svg {
  position: relative;
  width: 10px;
  left: 8px;
  top: -4px;
}

nav .menu-item .sub-menu {
  position: absolute;
  background-color: #222;
  top: calc(100% + 18px);
  left: 50%;
  transform: translateX(-50%);
  width: max-content;
  border-radius: 0 0 16px 16px;
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.5s ease-out;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>