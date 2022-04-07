<template>
  <div class="card">
    <div class="image"><img :src="img" alt="" /></div>
    <span>{{ title }}</span>
  </div>
</template>

<script>
export default {
  name: "MyCard",
  props: {
    title: String,
    img: String,
  },
};
</script>

<style scoped lang="css">
.image {
  position: relative;
  height: 100%;
}

.image::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(
    0deg,
    rgba(0, 0, 0, 0.8102176966292135) 0%,
    rgba(0, 0, 0, 0.6) 30%,
    rgba(0, 0, 0, 0) 100%
  );
}

.card {
  background-size: cover;
  background: white;
  overflow: hidden;
  min-width: 20vw;
  border-radius: 5px;
  position: relative;
}

.card img {
  background-size: contain;
  width: 100%;
  height: 100%;
}

.card span {
  position: absolute;
  bottom: 1.5vw;
  left: 1.5vw;
  font-size: 1.5em;
  font-weight: 500;

  color: white;
}
</style>