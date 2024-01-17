<template>
  <!-- component -->
  <!-- This is an example component -->
  <div class="header">
    <nav class="header_nav">
      <div class="wrapper header_container">
        <button @click="redirectToHome">
          <span class="header_name fadein-bot"> Дмитрий Кулушев</span>
        </button>
        <div class="header_icon fadein-bot">
          <a href="https://github.com/Dimacol"><img src="https://seeklogo.com/images/G/github-logo-2E3852456C-seeklogo.com.png" alt="github"></a>

        </div>
        <div id="mobile-menu-3">
          <ul>
            <li>
              <router-link to="/"
                class="fadein-bot header_text"
                aria-current="page">Главная</router-link>
            </li>
            <li>
              <router-link to="/about"
                class="fadein-bot fadein-1 header_text">Обо мне</router-link>
            </li>
            <li>
              <router-link to="/portfolio"
                class="fadein-bot fadein-2 header_text">Портфолио</router-link>
            </li>
            <li>
              <router-link to="/findMe"
                class="fadein-bot fadein-2 header_text">Контакты</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <div class="router">
      <router-view />
    </div>
  </div>
  <footer>
  <nav class="menu">
    <router-link to="/" class="menu_text">Главная</router-link>
    <router-link to="/about" class="menu_text">Обо мне</router-link>
    <router-link to="/portfolio" class="menu_text">Портфолио</router-link>
    <router-link to="/findMe" class="menu_text">Контакты</router-link>

  </nav>
</footer>
</template>

<script>
export default {
  methods: {
    redirectToHome() {
      this.$router.push('/')
    }
  },
}
</script>

<style>
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

::-webkit-scrollbar {
  width: 5px; /* for vertical scrollbar */
  height: 5px; /* for horizontal scrollbar */
}

::-webkit-scrollbar-track {
  background: hsl(120, 1%, 17%);
  border-radius: 5px;
}

::-webkit-scrollbar-thumb {
  background: #ffdb70;
  border-radius: 5px;
}

::-webkit-scrollbar-button { width: 20px; }
#mobile-menu-3{
  display: none; 
  justify-content: space-between; 
  align-items: center; 
  width: 100%; 
}
body {
  font-family: 'Poppins', sans-serif;
  background: hsl(151, 63%, 16%);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
}
ul {
  display: flex; 
  margin-top: 1rem; 
  flex-direction: column; 
  list-style-type: none; /* убрали точки */

}

nav {
  padding: 30px;
  
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  transition: color 0.3s;
}

nav a.router-link-exact-active {
  display: inline-flex;
  flex-direction: column;
  color: white;
  transition: color 0.3s;
}

nav a.router-link-exact-active::after {
  display: inline-block;
  content: "";
  margin-top: 0.08em;
  width: 100%;
  height: 4px;
  border-radius: 2px;
  background-color: #fad76f;
}

nav a.router-link-exact-active:hover {
  color: white;
}
button {
  background: none;
  border: none;
}
.header {
  display: flex; 
  position: relative; 
  flex-direction: column; 
  max-width: 100%; 
}
.header_nav {
  top: 0; 
  background: #0e3a1a;
}
.header_container {
  display: flex; 
  flex-wrap: wrap; 
  justify-content: space-between; 
  align-items: center; 
  min-height:100%;
}
.header_name {
  align-self: center; 
  font-size: 1.125rem;
  line-height: 1.75rem; 
  font-weight: 600;  
  color: #ffdb70;
  cursor: pointer;
}
.header_name:hover {
  color: white;
}
.header_icon {
  display: flex;
  width: 50px;

}
.header_text {
  display: block; 
  padding-top: 0.5rem;
  padding-bottom: 0.5rem; 
  padding-left: 0.75rem; 
  padding-right: 1rem; 
  border-bottom-width: 1px; 
  border-color: #F3F4F6; 
  color: #8d8f92;
}
.header_text:hover {
  color: #F9FAFB; 
}
img {
  width: 2.25rem;
  border-radius: 9999px; 
}
.menu {
  display: flex; 
  padding-top: 1rem;
  padding-bottom: 1rem; 
  justify-content: space-around; 
  font-size: 0.75rem;
  line-height: 1rem; 
}
.menu_text {
  color: rgb(174, 174, 174);
}
.menu_text:hover {
  color: ffff;
}
footer {
  display: block; 
  position: fixed; 
  right: 0; 
  bottom: 0; 
  left: 0; 
  border-top-left-radius: 1.5rem;
  border-top-right-radius: 1.5rem; 
  border-width: 1px; 
  --bg-opacity: 0.8; 
  /*backdrop-blur: blur(12px); 
  backdrop-opacity: opacity(0.9);*/ 
  border-color: #383838;
  background: #121212;

}

@media (min-width: 768px) {
  ul {
    margin-top: 0; 
    margin-left: 2rem; 
    flex-direction: row; 
    font-size: 0.875rem;
    line-height: 1.25rem; 
    font-weight: 500; 
  }
  .header_icon { 
    order: 2; }

  .header_text {
    padding-top: 0.5rem;
    padding-bottom: 0.5rem; 
    padding-left: 0.75rem; 
    padding-right: 1rem;  
    border-width: 0; 
  }
  .router {
    margin-top: 0px;
  }
  footer {
    display: none; 
  }
 
  #mobile-menu-3 {
    display: flex; 
    order: 1; 
    width: auto; 
 }
}
@keyframes fadeInLeft {
  0% {
    opacity: 0;
    transform: translateX(-100%);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

</style>
