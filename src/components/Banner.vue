<template>
  <div class="banner">
    <div class="image"><img :src="banner" alt="" /></div>

    <div class="banner-desc">
      <h1>{{ title }}</h1>
      <h2>{{ rank }} / 10</h2>
      <p>{{ synopsis }}</p>
      <div class="buttons">
        <button class="white">Play</button>
        <button class="gray"> More infos</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BannerPage",
  props: {
    banner: String,
    title: String,
    rank: Number,
    synopsis: String,
  },
};
</script>

<style scoped lang="css">
h1,
h2 {
  margin: 0;
}

h1 {
    font-size: 3em;
}

.banner {
  width: 100%;
  position: relative;
  margin-bottom: -10vw;
  text-align: left;
  background-image: url();
}

.banner img {
  width: 100%;
  position: relative;
}

.image::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(circle, rgba(0,0,0,0) 0%, rgba(0,0,0,0.4141502808988764) 32%, rgba(0,0,0,0.8102176966292135) 100%);
}
.banner-desc {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  width: 40%;
  left: 1em;
  top: 0;
  bottom: 25%;
  color: rgb(255, 255, 255);
  padding: 1em;
  border-radius: 50px;
}

.banner-desc h1 {
  border-radius: 50px;
}

.banner-desc p {
  text-align: left;
}

.buttons {
  display: flex;
  gap: 10px;
}

.buttons button {
  transition: all 0.2s;
  width: 30%;
  height: 40px;
  font-size: 1em;
  font-weight: 600;
  border: none;
  border-radius: 5px;
}

.white {
  background-color: white;
  color: black;
}

.white:hover {
  background-color: rgb(202, 202, 202);
}

.gray {
  background-color: gray;
  color: white;
}

.gray:hover {
  background-color: rgba(128, 128, 128, 0.616);
}
</style>