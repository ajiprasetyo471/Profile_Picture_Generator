<template>
  <div class="container">
    <ProfilePicGenerator />
  </div>
</template>

<script>
import ProfilePicGenerator from './components/ProfilePicGenerator.vue';

export default {
  name: 'App',
  components: { ProfilePicGenerator },
};
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
}

.container {
  width: 100%;
  height: 100vh;
  background: #fff377;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
