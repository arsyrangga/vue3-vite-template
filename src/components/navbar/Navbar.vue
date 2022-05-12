<template>
  <div class="navbar flex w-full items-center px-6 py-2 shadow-md">
    <div class="flex w-3/5 h-full flex items-center">
      <img
        src="https://picsum.photos/seed/492/930"
        class="rounded-full cursor-pointer"
      />
      <h1 class="ml-3 text-lg for-pc">Rangga Arsy Prawira</h1>
      <h1 class="ml-3 text-lg for-mobile">Rangga Arsy</h1>
    </div>
    <div class="flex w-2/5 justify-around">
      <p class="for-pc"><router-link to="/">Home</router-link></p>
      <p class="for-pc"><router-link to="/about">About</router-link></p>
      <p class="for-pc"><router-link to="/profile">Profile</router-link></p>
      <p class="for-pc"><router-link to="/contact">Contact</router-link></p>
    </div>
  </div>
</template>

<style scoped>
@import "./Navbar.css";
</style>
