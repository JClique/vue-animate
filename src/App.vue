<template>
  <div id="app">
    <div class="header fadeIn">
      <Navbar />
    </div>
    <transition name="router-content">
      <router-view/>
    </transition>
  </div>
</template>


<script>
import Navbar from '@/components/Navbar.vue'

export default {
	components: {
		Navbar
	},
  mounted() {
    function fadeIn(element) {
      let op = 0.1;
      let timer = setInterval(function() {
        if (op >= 1) {
          clearInterval(timer);
        }
        element.style.opacity = op;
        element.style.filter = 'alpha(opacity=' + op * 100 + ")";
        op += op * 0.1;
      }, 15);
    }

    let fadeIns = document.querySelectorAll('.fadeIn');
    for (const elm of fadeIns) {
      fadeIn(elm)
    }
  },
}

</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Lato&family=Nunito&display=swap');

:root {
  --gray: #7C7C79;
  --yale: #274C77;
  --frost: #6096BA;
  --baby: #A3CEF1;
  --white: #F3F5F7;
}

#app {
  margin: 0;
  padding: 0;
}

body {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: 'Lato', sans-serif;
  background-color: var(--white);
}

h1, h2, h3, h4, h5, h6 {
  font-family: 'Nunito', sans-serif;
}

a {
  text-decoration: none;
}

.header {
  width: 100%;
  height: 60vh;
  position: absolute;
  background-color: var(--yale);
  top: 0;
}

.header-content {
  width: 100%;
  height: 0vh;
  position: absolute;
  top: 0;
  z-index: -1;
}

.fadeIn {
  opacity: 0;
}

.page {
  position: fixed;
  width: 100%;
  margin: 8rem auto;
  color: var(--white);
}

.content {
  max-width: 800px;
  margin: auto;
}

.content img {
  height: 400px;
  float: right;
}


.router-content-enter-active {
  animation: coming 1s;
  animation-delay: .5s;
  opacity: 0;
}

.router-content-leave-active {
  animation: going 1s;
}

@keyframes going {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-50px);
    opacity: 0;
  }
}

@keyframes coming {
  from {
    transform: translateX(-50px);
    opacity: 0;
  }
  to {
    transform: translateX(0px);
    opacity: 1;
  }
}


</style>
