<template>
  <div>
    <header class="col-12 menu p-0 dcenter">
      <div class="col-8">
        <span class="text-black font-weight-bold text-uppercase">{{title}}</span>
      </div>
      <div class="col-4">
        <ul class="m-0 dcenter justify-content-around font-weight-light">
          <li>
            <i class="fas fa-home"></i> <router-link class="text-decoration-none" to="/">Home</router-link>
          </li>
          <li>
            <i class="fas fa-tags"></i> <router-link class="text-decoration-none" to="/articles">Articles</router-link>
          </li>
          <li>
            <i class="fas fa-sign-in-alt"></i> <router-link class="text-decoration-none" to="/login">Login</router-link>
          </li>
          <li>
            <i class="fas fa-address-card"></i> <router-link class="text-decoration-none" to="/register">Register</router-link>
          </li>
        </ul>
      </div>
    </header>
    <main class="container-fluid">
      <router-view :title="title"></router-view>
    </main>
    <footer class="col-12 bg-secondary py-4 text-center text-white">
      Todos los derechos reservados | {{title}} 2020
    </footer>
  </div>
</template>

<script>
export default {
  data(){
    return{
      title: 'Practices makes perfect!'
    }
  }
}
</script>

<style>
  body,
  html{
    background-color: #2a2a2a;
  }
  .router-link-exact-active{
    color: red !important;
  }


  /* SHORTCUTS */
  .dcenter{
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    align-items: center;
  }
  
  .menu{
    background-color: #f2f2f2;
    height: 8vh;
  }
  .menu li{
    font-size: 16px;
    list-style: none;
  }
  .menu i,
  .menu a{
    color: #a1a4a8;
  }
  
</style>