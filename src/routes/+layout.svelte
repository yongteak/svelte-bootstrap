<script>
  import "../app.pcss";
</script>

<header class="fixed top-0 left-0 w-full flex justify-center items-center bg-gray-800 text-white h-12">
  <nav>
    <ul class="flex space-x-4">
      <li><a href="/">Home</a></li>
      <li><a href="/main">Main</a></li>
      <li><a href="/new">New</a></li>
      <li><a href="/comment">Comment</a></li>
    </ul>
  </nav>
</header>

<main class="mt-12 p-4">
  <slot />
</main>

<footer class="fixed bottom-0 left-0 w-full bg-gray-800 text-white text-center p-4">
  © 2023 Your Company
</footer>