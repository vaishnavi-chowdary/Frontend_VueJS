<template>

  <div class="phone-detail" :class="{ active: isActive }">

    <div class="phone-image-box">
      <img :src="phone.ImageURL" alt="Phone Image" class="phone-image" />
    </div>

    <div class="phone-content-box">
      <h2>{{ phone.MobileName }}</h2>

      <div class="details">
        <p><strong>Model:</strong> {{ phone.MobileModel }}</p>
        <p><strong>Price:</strong> ${{ phone.MobilePrice }}</p>
        <p><strong>Release Date:</strong> {{ phone.ReleaseDate }}</p>
        <p><strong>Network Compatibility:</strong> {{ phone.NetworkCompatibility }}</p>

        <div class="color-options">
          <strong>Colors:</strong>
          <div class="color-box" 
          v-for="(color, index) in phone.ColorOptions" :key="index" 
          :style="{backgroundColor: color }">
        </div>
        </div>

        <div class="rating">
          <strong>Rating:</strong> {{ phone.Rating }}
        </div>

        <div class="speciality">
          <strong>Speciality:</strong> {{ phone.Speciality }}
        </div>

        <a :href="phone.URL" target="_blank" class="buy-button">Buy Now</a>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SinglePhone',
  props: {
    phone: Object,
    isActive: Boolean
  },
  
  methods: {
    // Define your methods here
    handleClick() {
      console.log('Phone clicked!');
    }
  }
};
</script>

<style scoped>
.phone-detail {
  flex: 0 0 100%;
  display: none;
}

.phone-detail.active {
  display: flex;
  flex-direction: row; 
  height: 460px;
}

.phone-image-box {
  overflow: hidden;
}

.phone-image {
  width: 600px;
  height: 448px;
  border: 1px solid black;
  
}

.phone-content-box {
  
  padding: 20px;
  flex: 1;
  border: 1px solid black;
  height: 448px;
  font-size: 25px;
  background-color: rgb(177, 228, 229);
}

.details {
  margin-top: 10px;
  font-size: 16px;
  line-height: 1.6;
  
 
}

.details p {
  margin-bottom: 10px; 
  font-size: 18px;
  font-weight: 600;
  
}

.color-options {
  margin-top: 10px;
  font-size: 18px;
}

.color-box {
  width: 20px;
  height: 20px;
  border-radius: 50%; 
  margin-right: 5px;
  margin-left: 10px;
  margin-bottom: -5px;
  display: inline-block;
  border: 2px solid black;
}

.rating {
  margin-top: 10px;
  font-size: 18px;
  font-weight: 600;
}



.speciality {
  margin-top: 10px;
  font-size: 18px;
  font-weight: 600;
}

.buy-button {
  display: inline-block;
  padding: 10px 20px;
  background-color: #000000;
  color: #fff;
  font-weight: bolder;
  text-decoration: none;
  border-radius: 5px;
  margin-top: 20px;
  transition: background-color 0.3s;
}

.buy-button:hover {
  background-color: #0056b3;
}

@media (max-width: 600px) {
   

.phone-detail.active {
 
  display: inline;
  height: 460px;
}



.phone-image {
  width: 453px;
  height: 410px;
  border: 1px solid black;
  
}

.phone-content-box {
  background-color: #f9f9f9;
  padding: 10px;
  margin-top: -12px;
  font-size: 25px;
  text-align: center;
  margin-bottom: -12px;
  height: max-content;
}

.details p {
  margin-bottom: 10px; 
  font-size: larger;
}


.color-options {
  font-size: larger;

}


.rating {
  font-size: larger;
}



.speciality {
  font-size: larger;
}

.buy-button {
 font-size: larger;
}

.buy-button:hover {
  background-color: #90c0f3;
  color: black;
  font-weight: bolder;
}

}
</style>
