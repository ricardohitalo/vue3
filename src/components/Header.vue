<template>
  <header>
    <nav class="container">
      <a href='https://pt.pngtree.com/so/homem-clipart'><img id="logo" src="./../img/programer-icon.png" alt=""></a>
      <img v-on:click="openMenu" id="menu-button" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/56d77da3c4779f8f200b84bde0676f2c74e5b606/assets/images/menu.svg" alt="">
      <div id="menu-overlay" v-if="menuActive"></div>

      <div id="menu-items" :class="{active:menuActive}">
        <img v-on:click="closeMenu" id="menu-logo" src="https://avatars.githubusercontent.com/u/59849225?v=4" alt="">
        <ul>
          <li><a href="https://github.com/ricardohitalo/">GitHub</a></li>
          <li><a href="#">LinkedIn</a></li>
          <li><a href="#">Email</a></li>
          <li><a href="#">Telefone</a></li>
        </ul>
      </div>

    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      menuActive: false,

    }
  },
  methods: {
    openMenu: function() {
      this.menuActive = true;
    },
    closeMenu: function() {
      this.menuActive = false;
    }
  }
}
</script>

<style scoped>
  header {
    background-color: var(--color-background-nav);
    width:100%;
    height: 60px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  #logo {
    height: 55px;
  }

  nav {
    display: flex;
    justify-content: space-between;
  }

  #menu-button {
    width: 30px;
  }

  #menu-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 40%;
    height: 100vh;
    background-color: #000;
    opacity: 0.6;
  }

  #menu-logo {
    border-radius: 100%;
    height: 60px;
  }

  #menu-items {
    position: fixed;
    top: 0;
    right: 0;
    background-color: var(--color-background-nav);
    width: 60%;
    height: 100vh;
    flex-direction: column;
    align-items: center;
    display: none;

  }

  #menu-items.active {
    display: flex;
  }
  
  ul {
  list-style: none;
}  

  ul li {
    margin: 20px 0;
  }

  ul li a {
    color: var(--color-text-light);
  }

</style>