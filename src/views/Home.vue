<template>
  <div class="wrapper">
    <div id="logo">
      <img src="../assets/logo.png" alt="PyChan" />
    </div>
    <div class="about">
      <p id="name">
        PyChan
      </p>
      <p id="description">
        Dołącz do użytkowników korzystających z jednego z najlepszych naukowych botów Discord
      </p>
    </div>
    <div class="button">
      <a href="#" class="neon-button">Neon</a>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Home',
    created(){
      document.title = "PyChan";
    },
    components: {
    },
  }
</script>

<style scoped>
  .wrapper {
    display: flex;
    width: 100%;
    height: 100%;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    }

  #logo img{
    width: 50%;
    height: auto;
  }

  .description {
    width: 70%;
  }

  #name {
    font-size: 6vmin;
  }
  #description {
    font-size: 3vmin;
  }
</style>
