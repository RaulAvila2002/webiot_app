<template>
  <footer class="footer">
    <div class="container-fluid">
      <ul class="nav">
        <li class="nav-item">
          <a
            href="https://webiot.com.ar"
            target="_blank"
            rel="noopener"
            class="nav-link"
          >
            webiot.com.ar
          </a>
        </li>
        <li class="nav-item">
          <a
            href="https://webiot.com.ar"
            target="_blank"
            rel="noopener"
            class="nav-link"
          >
            About Us
          </a>
        </li>
        <li class="nav-item">
          <a
            href="https://webiot.com.ar"
            target="_blank"
            rel="noopener"
            class="nav-link"
          >
            Blog
          </a>
        </li>
      </ul>
      <div class="copyright">
        &copy; {{ year }}, made  by
        
        <a
          href="https://webiot.com.ar"
          target="_blank"
          rel="noopener"
          >WebIOT</a
        >
        for a better web.
      </div>
    </div>
  </footer>
</template>
<script>
export default {
  data() {
    return {
      year: new Date().getFullYear()
    };
  }
};
</script>
<style></style>
