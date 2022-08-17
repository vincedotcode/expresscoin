<style scoped>
img{
  animation: rotation 3s infinite linear;
}

.rotate {
  animation: rotation 3s infinite linear;
}


@keyframes rotation {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(359deg);
  }
}
</style>


<template>
  <router-link to="/Dashboard">
  <div class="splash w-full h-screen bg-indigo-300 flex justify-center items-center">
    <div class="w-fit mx-auto p-4">
      <img src="../assets/icon.png" alt="splash" class="splash mx-auto w-64 rotate">
      <h1 class="text-indigo-600 text-5xl text-center">Express<span class="text-7xl font-extrabold">Coin</span></h1>
      <p class="text-indigo-500 text-center font-medium pt-5">Click To Engage</p>
    </div>
    
  </div>
  </router-link>
</template>

<script>
export default {
  name: 'Splash',
}
</script>


