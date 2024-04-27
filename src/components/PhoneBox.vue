<template>
  <div class="phone-container">
    <div class="phone-list">
      <SinglePhone v-for="(phone, index) in phones" 
      :key="index" 
      :phone="phone" 
      :isActive="index === currentIndex" />
    </div>
    <button @click="scrollLeft" class="nav-btn left">&#10094;</button>
    <button @click="scrollRight" class="nav-btn right">&#10095;</button>
  </div>
</template>

<script>
import SinglePhone from './SinglePhone.vue';

export default {
  name: 'PhoneBox',
  props: {
    phones: Array
  },
  data() {
    return {
      currentIndex: 0
    };
  },
  methods: {
    scrollLeft() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
      }
    },
    scrollRight() {
      if (this.currentIndex < this.phones.length - 1) {
        this.currentIndex++;
      }
    }
  },
  components: {
    SinglePhone 
  }
};
</script>

<style scoped>
.phone-container {
  position: relative;
  overflow: hidden;
  margin-left: 40px;
  border: 1px solid #ccc;
  border-radius: 5px;
  height: 450px;
  width: 1200px;
}

.phone-list {
  display: grid;
  overflow-x: hidden; 
  scroll-snap-type: x mandatory;
}

.nav-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(13, 141, 163, 0.8);
  font-weight: bolder;
  font-size: larger;
  padding: 10px;
  cursor: pointer;
  border: none;
  z-index: 1;
}

.left {
  left: 10px;
}

.right {
  right: 10px;
}
@media (max-width: 600px) {
  .phone-container {
    height: auto; 
    flex-direction: column;
    width: 455px;
  }

}
</style>
