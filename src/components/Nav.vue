<script setup>

</script>

<template>
  <div id="nav">
    <ul>
      <li><RouterLink to="/" active-class="active">Home</RouterLink></li>
      <li><RouterLink to="/about" active-class="active">About</RouterLink></li>
    </ul>
  </div>
</template>

<style scoped>
#nav {
  width: 100%;
  float: left;
  margin: 0 0 1em 0;
  background-color: #f2f2f2;
}

#nav ul {
  list-style: none;
  width: 800px;
  margin: 0 auto;
  padding: 0;
}

#nav li {
  float: left;
}

#nav li a {
  display: block;
  padding: 10px 15px;
  text-decoration: none;
}

#nav li a:hover {
  color: #fff;
  background-color: #3b3b3b;
  transition: 0.3s;
}

.active {
  font-weight: bold;
  color: darkviolet;
}

</style>