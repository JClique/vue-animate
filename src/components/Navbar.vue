<template lang="html">
  <ul class="navbar fadeIn">
    <li><h1>Vue Animate</h1></li>
    <li><router-link to="/">Home</router-link></li>
    <li><router-link to="/about">About</router-link></li>
  </ul>
</template>

<script>
export default {
  name: 'Navbar',
}
</script>

<style lang="css" scoped>
ul.navbar {
  display: flex;
  justify-content: flex-end;

  list-style: none;
  font-family: 'Nunito', sans-serif;

  border-bottom: 1px solid var(--white);
  margin: 0;
  padding: 2rem;

  background-color: var(--yale);
  box-shadow: 0 5px 5px rgba(0,0,0, .1);
  z-index: 5;
}

ul.navbar a {
  padding: .5rem 1rem;
  margin-left: 1rem;
  border-radius: 3px;
  color: var(--white);
  transition: .7s;
}

ul.navbar a:hover {
  background-color: var(--white);
  color: var(--yale)
}

ul.navbar li:first-child {
  position: absolute;
  left: 3rem;
}

ul.navbar h1 {
  margin: 0;
  line-height: 1;
  color: var(--white);
}
</style>
