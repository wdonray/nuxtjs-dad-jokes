<template>
  <header class="header">
    <h1 class="title">Dad Jokes</h1>
    <ul>
      <li>
        <NuxtLink to="/">Home</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/jokes">Jokes</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/about">About</NuxtLink>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
    name: 'Appheader'
}
</script>

<style>
    .header{
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding-bottom: 1rem;
        border-bottom: 1px dotted #ccc;
        width: 100%;
    }

    .header .title {
        font-size: 3rem;
        color: #526488
    }

    .header ul {
        display: flex;
    }

    .header a {
        display: inline-block;
        background: #333;
        color: white;
        padding: 0.3rem 1rem;
        margin-right: 0.5rem;
    }
</style>