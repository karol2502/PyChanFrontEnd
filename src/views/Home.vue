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
      <a href="https://discord.com/api/oauth2/authorize?client_id=531953165008896046&permissions=2148006976&scope=bot" target="_blank" class="neon-button">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        Dodaj na serwer
      </a>
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

<style lang="scss" scoped>
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

  .button {
    margin: 20px;
  }

  a {
    position: relative;
    display: inline-block;
    padding: 15px 30px;
    color: #2196f3;
    text-transform: uppercase;
    letter-spacing: 4px;
    text-decoration: none;
    font-size: 24px;
    overflow: hidden;
    transition: 0.25s;
  }

  a:hover {
    color: #255784;
    background: #2196f3;
    box-shadow: 0 0 10px #2196f3, 0 0 40px #2196f3, 0 0 80px #2196f3;
    transition-delay: 0.5s;
  }

  a span {
    position: absolute;
    display: block;
  }

  a span:nth-child(1) {
    top: 0;
    left: -100%;
    width: 100%;
    height: 2px;
    background: linear-gradient(90deg, transparent, #2196f3);
  }

  a:hover span:nth-child(1) {
    left: 100%;
    transition: 0.5s;
  }

  a span:nth-child(3) {
    bottom: 0;
    right: -100%;
    width: 100%;
    height: 2px;
    background: linear-gradient(270deg, transparent, #2196f3);
  }

  a:hover span:nth-child(3) {
    right: 100%;
    transition: 0.5s;
    transition-delay: 0.25s;
  }

  a span:nth-child(2) {
    top: -100%;
    right: 0;
    width: 2px;
    height: 100%;
    background: linear-gradient(180deg, transparent, #2196f3);
  }

  a:hover span:nth-child(2) {
    top: 100%;
    transition: 0.5s;
    transition-delay: 0.125s;
  }

  a span:nth-child(4) {
    bottom: -100%;
    left: 0;
    width: 2px;
    height: 100%;
    background: linear-gradient(360deg, transparent, #2196f3);
  }

  a:hover span:nth-child(4) {
    bottom: 100%;
    transition: 0.5s;
    transition-delay: 0.30s;
  }

</style>
