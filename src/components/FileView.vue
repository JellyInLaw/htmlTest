<template>
  <p class="file">{{ name }}</p>
</template>

<script>
export default {
  name: "FileView",
  props: {
    name: String,
  },
};
</script>

<style scoped lang="scss">
.file {
  color: #2f4f4f;
  cursor: pointer;
  background-color: #fffacd;
  width: 150px;
  padding: 5px 15px;
  padding-left: 30px;
  border-radius: 5px;
  margin-left: 40px;
  position: relative;
}
.file:hover {
  background-color: #f0e68c;
}
.file::before {
  content: "";
  position: absolute;
  left: 7px;
  top: 9px;
  width: 15px;
  height: 15px;
  display: inline;
  background-image: url("./document.png");
  background-position: center center;
  background-size: cover;
}
</style>
