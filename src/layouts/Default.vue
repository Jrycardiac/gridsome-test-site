<template>
  <div class="layout">
    <header class="header" id="hea">
      <strong>
        <g-link to="/">{{ $static.metadata.siteName }}</g-link>
      </strong>
      <!-- Main container -->
      <nav class="level">
        <!-- Left side -->
        <div class="level-left">
          <div class="level-item"></div>
        </div>

        <!-- Right side -->
        <div class="level-right">
          <p class="level-item">
            <g-link to="/about/">关于</g-link>
          </p>
        </div>
      </nav>
    </header>

    <transition name="fade" appear>
      <main>
        <slot />        
      </main>
    </transition>
    
    <footer class="footer" id="foo">
      <div class="content has-text-centered">
        <p>
          使用<a href="https://gridsome.org">gridsome</a>框架，样式为<a href="https://buefy.org">buefy</a>
          <br />
          源码遵循<a href="http://opensource.org/licenses/mit-license.php">MIT协议</a>
          <br />
          <br />
          <strong>创新实践网站小组</strong>
          <a>用❤创造</a>
        </p>
      </div>
    </footer>
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
  font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
}

.layout {
  max-width: 1280px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.header#hea {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
  height: 80px;
}

.footer#foo {
    background-color: #fafafa;
    padding: 1.5rem 1.5rem 1.5rem;
}

.nav__link {
  margin-left: 20px;
}

.fade-enter-active {
  transition: opacity 1s;
}

.fade-enter {
  opacity: 0;
}
</style>
