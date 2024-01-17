<template>
    <div class="main-container">
      <h1 class="contacts">Контакты</h1>
      <div class="find-me-container">
        <img class="img_me"
          ref="img"
          src="img/my.png"
          alt="Portrait photo of Ayushman"

        />
        <div class="icons">
          <FindMeIcons
            class="email"
            title="email"
            content="dmitrijkulushev@mail.com"
          />
          <FindMeIcons
            title="github"
            content="Dimacol"
            link="https://github.com/Dimacol"
          />
          <FindMeIcons
            title="instagram"
            content="dima"
            link="http://instagram.com/dima"
          />
          <FindMeIcons
            title="vk"
            content="VK"
            link="https://vk.com/id447409318"
          />
          <FindMeIcons
            title="whatsapp"
            content="WhatsApp"
            link="https://wa.me/792222090000"
          />
          <FindMeIcons
            title="telergam"
            content="Telegram"
            link="https://t.me/+79296290520"
          />
          
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import FindMeIcons from "../components/FindMeIcons";
  export default {
    name: "FindMe",
    components: {
      FindMeIcons,
    },
    methods: {
    
    },
  };
  </script>
  
  <style scoped>
  .main-container {
    padding-bottom: 0em;
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
  }
  .contacts {
    margin-top: 1em;
    text-align: center;
    color: #ffffff;
  }
  .img_me {
    border: 1px solid rgb(231, 250, 85);
    border-radius: 20%;
    width: clamp(200px, 20vw, 20vw);
  }
  .find-me-container {
    margin-top: 3em;
    width: 80vw;
    display: flex;
    flex-flow: row wrap;
    justify-content: space-around;
    align-items: center;
  }
  .icons {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2em;
  }
  
  @media (max-width: 700px) {
    img {
      margin-bottom: 2em;
    }
    .icons {
      display: grid;
      grid-template-columns: 1fr;
      gap: 1.2em;
    }
  }
  </style>