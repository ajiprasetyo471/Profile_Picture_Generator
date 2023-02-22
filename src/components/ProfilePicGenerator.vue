<template>
  <div class="card-container">
    <input
      type="text"
      class="input-name"
      v-model="name"
      placeholder="Ketik nama Anda..."
      v-on:keyup.enter="getProfilePicture"
      onke
    />
    <button @click="getProfilePicture" class="create-pic">
      Buat Profil Picture!
    </button>
    <img
      v-if="profilePic !== url && this.name !== ''"
      :src="profilePic"
      class="profile-pic"
    />
  </div>
</template>

<script>
export default {
  name: 'ProfilePicGenerator',
  data() {
    return {
      url: 'https://robohash.org/',
      name: '',
      profilePic: '',
    };
  },
  methods: {
    async getProfilePicture() {
      try {
        this.profilePic = `${this.url}${this.name}.png`;
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.card-container {
  width: 40vw;
  height: 80vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 15px;
  background: #e0ffff;

  .input-name {
    margin-top: 30px;
    width: 20vw;
    padding: 10px;
    font-size: 14px;
    border-radius: 5px;
    border: 1.5px solid #d2dfe3;
    color: #ac9e8f;
  }

  .input-name:focus {
    outline: none;
  }

  .create-pic {
    background: #28a745;
    color: #fff;
    border: none;
    padding: 10px;
    font-weight: 500;
    font-size: 14px;
    border-radius: 5px;
    width: 10vw;
  }

  .create-pic:active {
    outline: 4px solid #84d3a2;
  }

  .profile-pic {
    margin-top: 10px;
    width: 20vw;
    background: #fff;
    border-radius: 50%;
    border: 2px solid #eee;
  }
}
</style>
