<template>
  <header class="flex" :class="{ 'dark-mode': isDarkMode, 'light-mode': !isDarkMode }">
    <div class="branding" style="margin-bottom: 14px; background-color: white">
      <img src="@/assets/profile.png" alt="profile" draggable="true" />
    </div>
    <div class="branding flex">
      <img src="@/assets/file-invoice-dollar-solid.png" alt="menu" draggable="true" />
    </div>

    <img
      v-if="isDarkMode"
      src="@/assets/moon.svg"
      style="margin-top: 10em; padding-left: 20%;"
      width="70"
      height="30"
      @click="toggleDarkMode"
    />


    <img
      v-else
      src="@/assets/moon.svg"
      style="margin-top: 10em; padding-left: 20%;color:"
      width="70"
      height="30"

      @click="toggleDarkMode"
    />
    <div class="branding"  style="margin-top: 15em; background-color: white">
      <img src="@/assets/profile.png" alt="profile" draggable="true" />
    </div>
  </header>
</template>

<script>
export default {
  name: 'Navigation',

  data() {
    return {
      isDarkMode: false // Set this to true if you want to start with dark mode by default
    };
  },
  methods: {
    toggleDarkMode() {
      this.isDarkMode = !this.isDarkMode;
      // You can also save the user's preference in local storage or a cookie to remember their choice across sessions.
    }
  }
};
</script>

<style lang="scss" scoped>
.dark-mode {
  background-color: black;
  color: white;
}

/* Light mode styles */
.light-mode {
  background-color: white;
  color: black;
}
header {
  z-index: 99;
  flex-direction: row;
  background-color: #1e2139;
  @media (min-width: 900px) {
    min-width: 90px;
    min-height: 100%;
    flex-direction: column;
    border-radius: 0 20px 20px 0;
  }
}

.branding {
  border-radius: 0 20px 20px 0;
  background-color: #7c5dfa;
  justify-content: center;
  padding: 24px;
  @media (min-width: 900px) {
    width: 100%;
  }

  img {
    width: auto;
    height: 30px;
  }
}
</style>
