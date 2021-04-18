<template>
  <div class="home">
    <div class="container">
      <div class="header">
        <div>
          <SimpleSwitch></SimpleSwitch>
          <input
            v-model="selectedTheme"
            id="light-theme"
            type="radio"
            name="theme"
            value="light"
          />
          <label for="light-theme">light</label>
          <input
            v-model="selectedTheme"
            id="dark-theme"
            type="radio"
            name="theme"
            value="dark"
          />
          <label for="dark-theme">dark</label>
        </div>
      </div>
      <div class="left-sidebar">
        Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
        eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
        voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
        clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
        amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
        nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat,
        sed diam voluptua. At vero eos et accusam et justo duo dolores et ea
        rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem
        ipsum dolor sit amet.
      </div>
      <div class="content-1">
        Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
        eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
        voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
        clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
        amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
        nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat,
        sed diam voluptua. At vero eos et accusam et justo duo dolores et ea
        rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem
        ipsum dolor sit amet.
      </div>
      <div class="content-2">
        Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
        eirmod tempor
      </div>
      <div class="right-sidebar">Right Sidebar</div>
      <div class="footer">Footer</div>
    </div>
  </div>
</template>

<script>
import SimpleSwitch from "../components/SimpleSwitch";
export default {
  name: "Home",
  components: {
    SimpleSwitch,
  },
  data() {
    return {
      selectedTheme: "light",
    };
  },
  methods: {
    switchTheme(theme) {
      document.documentElement.setAttribute("data-theme", theme);
    },
  },
  watch: {
    selectedTheme(theme) {
      this.switchTheme(theme);
    },
  },
};
</script>

<style scoped lang="css">
.container {
  height: 100vh;
  display: grid;
  grid-template-columns: 1fr 2fr 2fr 1fr;
  grid-template-rows: auto 1fr auto;
  grid-template-areas:
    "header header header header"
    "leftSidebar content1 content2 rightSidebar"
    "footer footer footer footer";
}

.container > div {
  font-size: 2em;
}

.header {
  grid-area: header;
}
.left-sidebar {
  grid-area: leftSidebar;
  overflow: auto;
}
.right-sidebar {
  grid-area: rightSidebar;
  overflow: auto;
}
.content-1 {
  grid-area: content1;
  overflow: auto;
}
.content-2 {
  grid-area: content2;
  overflow: auto;
}
.footer {
  grid-area: footer;
}
</style>
