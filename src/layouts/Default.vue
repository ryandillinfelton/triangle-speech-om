<template>
  <div class="layout">
    <header class="header">
      <nav class="nav">
        <g-link class="nav__link" to="/">Home</g-link>
        <g-link class="nav__link" to="/about/">About</g-link>
        <g-link class="nav__link" to="/about/">Contact</g-link>
      </nav>
    </header>
    <div class="content">
      <slot/>
    </div>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>
body {
  font-family: -apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
  margin:0;
  padding:0;
  line-height: 1.5;
}

.layout {
  max-width: 100vw;
  margin: 0 auto;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 3rem;
  background: black;
  color: white
}

.nav{
  display: flex;
  justify-content: space-evenly;
  width: 100vw;
}

.nav__link {
  color: white;
  font-size: 1.2rem;
}

.content {
  max-width: 80vw;
  margin: 0 auto;
}
</style>
