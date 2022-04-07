<template>
  <nav>
    <a class="logo" href="/"></a>
    <!-- <MenuLink url="/" text="Accueil" />
    <MenuLink url="/" text="Séries" />
    <MenuLink url="/" text="Films" />
    <MenuLink url="/" text="Nouveautés les plus reardées" />
    <MenuLink url="/" text="Ma liste" /> -->
  </nav>
</template>

<script>
// import MenuLink from "./MenuLink.vue";

export default {
  name: "MenuPage",
  // components: {
  //   MenuLink,
  // },
};
</script>

<style scoped>
    nav{
      z-index: 1;
        position: absolute;
        top: 1em;
        left: 1em;
        display: flex;
        align-items: center;
        gap: 1em;
        height: 4em;
    }

    .logo{
      width: 9em;
      height: 3em;
      background-image: url("../assets/netflux.png");
      background-size: cover;
    }
</style>