<template>
  <p class="folder">{{ name }}</p>
  <template v-for="folder in folders">
    <FolderView
      :name="folder.name"
      :folders="folder.folders"
      :files="folder.files"
    />
  </template>
  <template v-for="file in files">
    <FileView :name="file.name" />
  </template>
</template>

<script>
import FileView from "./FileView";
export default {
  name: "FolderView",
  components: { FileView },
  props: {
    name: String,
    folders: Array,
    files: Array,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.folder {
  position: relative;
  color: white;
  cursor: pointer;
  background-color: #808080;
  padding: 10px 20px;
  padding-left: 30px;
  width: 200px;
  border-radius: 5px;
}
.folder:hover {
  opacity: 0.9;
  transform: scale(1.03);
}
.folder::before {
  content: "";
  position: absolute;
  left: 9px;
  top: 13px;
  width: 15px;
  height: 15px;
  display: inline;
  background-image: url("./folder.png");
  background-position: center center;
  background-size: cover;
}
</style>
