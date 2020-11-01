<template>
  <footer class="footer">
    <p class="content">Created By Donray Williams</p>
    <a target="_blank" href="https://www.donrayxwilliams.com">My Website</a>
  </footer>
</template>

<script>
export default {
  name: 'Appfooter',
}
</script>

<style>
.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px dotted #ccc;
  width: 100%;
}

.footer .content {
  font-size: 0.8rem;
  color: #526488;
}

.footer a {
  display: inline-block;
  background: #333;
  color: white;
  padding: 0.3rem 1rem;
  margin-right: 0.5rem;
}
</style>