<template>
  <div
    class="top_about">
    <article data-page="about">

      <header>
        <div class="about_title line fadein-bot">
          Обо мне &nbsp;
        </div>
      </header>

      <section
        class="about_content">
        <div class="content_left">
          <img class="about_foto fadein-up"
            src="img/my.png" alt="Foto">
        </div>
        <div class="content_right">
          <p class="about_text fadein-left fadeins-1">
            &nbsp; &nbsp; &nbsp; Всем привет! Меня зовут Дмитрий Кулушев. Я Frontent-разработчик из г.Москва. <br>
             Опыт работы в разработке более 2 лет.<br> 
             Занимаюсь разработкой сайтов на WordPress, Tilda и их продвижением, кроме того веду каналы на Telegram, сообщества Instagram и VK.
          </p>
          <p class="about_text fadeins-2">
            &nbsp; &nbsp; &nbsp; Моя работа заключается в том, чтобы создать ваш веб-сайт таким,
             чтобы он был функциональным и удобным для пользователя, но при этом привлекательным.
             Кроме того, я привожу индивидуальный подход к вашему продукту и гарантирую,
              что веб-сайт привлечет внимание и будет прост в использовании. 
          </p>
        
        </div>
      

      </section>  
    </article>
  </div>

  <div class="about_skills">
    <article data-page="about">
      <header>
        <div class="about_header line fadein-bot">
          &nbsp; Что я могу
        </div>
      </header>
      <section>
        <div>
          <ul>
            <li>
              <button class="about_button"
                :class="{ 'button_text': activeTab === 1 }" @click="activeTab = 1">Навыки</button>
            </li>
            <li>
              <button class="about_button"
                :class="{ 'button_text': activeTab === 2 }" @click="activeTab = 2">Инструменты</button>
            </li>
          </ul>
        </div>
        <div v-show="activeTab === 1">
          <div class="about_tech">
            <div v-for="item in tech" :key="item.id">
              <div
                class="about_item">
                <div class="item_img">
                  <img alt="HTML" loading="lazy" width="32" height="32" decoding="async" data-nimg="1"
                    class="tech_img "
                    :src="item.imageUrl" style="color: transparent;">
                </div>
                <div class="tech_name">
                  <div class="tech_item">{{ item.name }}
                  </div>
                  <div
                    class="tech_status">
                    {{ item.status }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div v-show="activeTab === 2">
          <div class="tables">
            <div v-for="item in tools" :key="item.id">
              <div class="about_item">
                <div class="tables_img">
                  <img alt="HTML" loading="lazy" width="32" height="32" decoding="async" data-nimg="1"
                    class="img-tech skill_img  "
                    :src="item.imageUrl" style="color: transparent;">
                </div>
                <div class="skill">
                  <div class="skill_name">{{ item.name }}
                  </div>
                  <div
                    class="skill_status">
                    {{ item.status }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </article>
  </div>
</template>
<script>
export default {
  data() {
    return {
      activeTab: 1,
      tech: [
        {
          id: 1,
          name: 'HTML',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/1051/1051277.png',
          status: 'Разработчик'
        },
        {
          id: 2,
          name: 'CSS',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/732/732190.png',
          status: 'Разработчик'
        },
        {
          id: 3,
          name: 'PHP',
          imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-php-2038871-1720084.png',
          status: 'Разработчик'
        },
        {
          id: 4,
          name: 'Javascript',
          imageUrl: 'https://cdn.icon-icons.com/icons2/2415/PNG/512/javascript_original_logo_icon_146455.png',
          status: 'Разработчик'
        },
        {
          id: 5,
          name: 'WordPress',
          imageUrl:'https://cdn.icon-icons.com/icons2/555/PNG/512/wordpress_icon-icons.com_53600.png',
          status: 'Разработчик'
        },
        {
          id: 6,
          name: 'Telegram',
          imageUrl: 'https://cdn.icon-icons.com/icons2/3053/PNG/512/telegram_macos_bigsur_icon_189662.png',
          status: 'Админ'
        },
        {
          id: 7,
          name: 'VueJS',
          imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-vue-282497.png?f=webp',
          status: 'Разработчик'
        },
        {
          id: 8,
          name: 'Tilda',
          imageUrl: 'https://cdn.icon-icons.com/icons2/2429/PNG/512/tilda_logo_icon_147224.png',
          status: 'Разработчик'
        },
        {
          id: 9,
          name: 'NodeJS',
          imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-node-js-1174925.png',
          status: 'Разработчик'
        },
        {
          id: 10,
          name: 'Instagram',
          imageUrl: 'https://cdn.icon-icons.com/icons2/1584/PNG/512/3721672-instagram_108066.png',
          status: 'Админ'
        },
        {
          id: 11,
          name: 'VK',
          imageUrl: 'https://cdn.icon-icons.com/icons2/2037/PNG/512/media_social_vk_vkontakte_icon_124252.png',
          status: 'Админ, Таргетолог'
        },
        {
          id: 12,
          name: 'Яндекс Директ',
          imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Yandex_Direct_icon.svg/40px-Yandex_Direct_icon.svg.png?20220314220458',
          status: 'Директолог'
        }
      ],
      tools: [
        {
          id: 1,
          name: 'Git',
          imageUrl: 'https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png',
          status: 'Контроль версий'
        },
        {
          id: 2,
          name: 'GitHub',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/25/25231.png',
          status: 'Хостинг'
        },
        {
          id: 3,
          name: 'VS Code',
          imageUrl: 'https://raw.githubusercontent.com/dhanishgajjar/vscode-icons/master/png/default_dark.png',
          status: 'Редактор кода'
        },
        {
          id: 4,
          name: 'MySQL',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/5968/5968313.png',
          status: 'База данных'
        },
      ]
    };
  }
}
</script>


<style>
li {
  margin-right: 0.5rem; 
}
ul {
  display: flex; 
  margin-bottom: 1.25rem; 
  flex-wrap: wrap; 
  font-size: 0.875rem;
  line-height: 1.25rem; 
  font-weight: 500; 
  text-align: center; 
  color: #ffffff;
}
.top_about {
  padding-top: 50%;
  padding-bottom: 2rem; 
  padding-left: 1.25rem;
  padding-right: 1.25rem; 
  margin-left: 0.75rem;
  margin-right: 0.75rem; 
  margin-bottom: 1.25rem; 
  border-radius: 1.5rem; 
  border-width: 1px; 
  text-align: left; 
  color: rgb(255 251 235);
  border-color: #383838;
}
.about_title {
  display: flex; 
  margin-bottom: 1.25rem; 
  align-items: center; 
  font-size: 1.5rem;
  line-height: 2rem; 
  font-weight: 700; 
  color: #ffffff; 
}
.line {
  display: flex;
  align-items: center; 
  width:100%;
  height:1px; 
  background: #fff;
  align-content: flex-end;
  flex-wrap: wrap;

}
.about_aos {
  width: 8rem; 
  height: 1px;
}
.about_content {
  display: flex; 
  flex-direction: column; 
  gap: 1rem; 
  font-size: 0.875rem;
  line-height: 1.25rem; 
  text-align: justify; 
}
.content_left {
  display: flex; 
  justify-content: center; 
}
.about_header {
  display: flex; 
  align-items: center; 
  margin-bottom: 1.25rem; 
  font-size: 1.5rem;
  line-height: 2rem; 
  font-weight: 700; 
  color: #ffffff; 
}
.about_heading {
  width: 2.5rem; 
  height: 1px;
  background-color: rgb(253 230 138);
}
.about_tech {
  display: grid; 
  padding-bottom: 8rem; 
  grid-template-columns: repeat(2, minmax(0, 1fr)); 
  gap: 1rem; 
}
.about_item {
  display: flex; 
  padding-top: 0.5rem;
  padding-bottom: 0.5rem; 
  padding-left: 0.5rem;
  padding-right: 0.5rem; 
  gap: 0.5rem; 
  align-items: center; 
  border: 2px solid #F59E0B;
  border-radius: 0.25rem; 
  border-width: 1px; 
  cursor: pointer; 
}
.about_item:hover {
  transform: scale(1.1); /* увеличение секции*/

}
.item_img {
  padding: 0; 
  justify-content: center; 
  align-items: center; 
  width: 3rem; 
  height: 3rem; 
}
.tech_img {
  height: 65%;
  
  width: 3rem; 
}
.tech_item {
  font-weight: 500; 
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 300ms; 
  transition-duration: 300ms; 
  --transform-translate-y: 0; 
  }
.tech_name {
  display: flex; 
  align-items: center; 
  font-size: 0.875rem;
  line-height: 1.25rem;
  color:#ffffff;
}
.tech_status {
  position: absolute; 

  margin-top: 2rem;  
  font-size: 10px;
  color: rgb(253 230 138);

}
.skill {
  display: flex; 
  align-items: center; 
  font-size: 0.875rem;
  line-height: 1.25rem;
}
.skill_status {
  position: absolute; 
  margin-top: 2rem; 

  font-size: 10px;
  color: rgb(253 230 138);
}
.skill_name {
  font-weight: 500; 
  color:#ffffff;
}
.tables {
  display: grid;
  padding-bottom: 8rem; 
  grid-template-columns: repeat(2, minmax(0, 1fr)); 
  gap: 1rem; 
}
.tables_img {
  display: flex; 
  padding: 0; 
  justify-content: center; 
  align-items: center; 
  width: 3rem; 
  height: 3rem; 
}
.tables_cart {
  display: flex; 
  padding-top: 0.5rem;
  padding-bottom: 0.5rem; 
  padding-left: 0.5rem;
  padding-right: 0.5rem; 
  gap: 0.5rem; 
  align-items: center; 
  border-radius: 0.25rem; 
  border-width: 1px; 
  cursor: pointer; 
}
.tables_cart:hover {
  opacity: 0.1; 
 }
.button_text {
  font-size: 1.2rem;
  border: 2px solid #F59E0B;

}
.button_text:hover {
  color: #ffffff;
}
.button_text:focus {
  color:#f8d56e;
  
}

.skill_img {
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 300ms; 
  transition-duration: 300ms; 
  height: 65%;
  width: 65%;
  filter:drop-shadow(0 20px 13px rgba(0, 0, 0, 0.03)) drop-shadow(0 8px 5px rgba(0, 0, 0, 0.08));;
}
.about_text {
  margin-bottom: 0.75rem; 
  
}
.about_foto {
  margin-bottom: 0.75rem; 
  border-radius: 99999px; 
  width: 60%; 
  border: 1px solid #f8d56e;
}
.about_connection {
  display: flex; 
  margin-bottom: 0.75rem; 
  justify-content: center;
}
.about_skills{
  padding-top: 1.25rem;
  padding-bottom: 1.25rem; 
  padding-left: 1.25rem;
  padding-right: 1.25rem; 
  margin-left: 0.75rem;
  margin-right: 0.75rem; 
  text-align: left;
}
.about_button{/*  кнопки навыки умения*/ 
  display: inline-block; 
  padding-top: 0.75rem;
  padding-bottom: 0.75rem; 
  padding-left: 1rem;
  padding-right: 1rem; 
  border-radius: 0.5rem; 
  cursor: pointer;
  font-weight: 600;
  font-size: 1.2rem;
  color: #9f9482;
 
}
.about_button:hover {
  color: rgb(255, 255, 255);
  background-color: #9f9482;

 }
.fadein-left {
  opacity: 0;
  animation: fadeInLeft 0.5s ease-out forwards;
}

@media (min-width: 768px){
  .top_about{
    padding-top: 2.5rem;
    padding-bottom: 2.5rem; 
    padding-left: 3rem;
    padding-right: 3rem;  
  }
  .about_aos {
    width: 24rem; 
  }
  .about_content {
    flex-direction: row; 
    gap: 2rem; 
    align-items: center; 
    font-size: 1.125rem;
    line-height: 1.75rem; 
  }
  .about_connection{
    gap: 2rem;
  }
  .content_right {
    width: 58.333333%; 
  }
  .about_text {
    margin-bottom: 1.75rem;  
  }
  .about_skills {
    padding-top: 2.5rem;
    padding-bottom: 2.5rem; 
    padding-left: 3rem;
    padding-right: 3rem; 
  }
  .about_heading {
    width: 5rem; 
  }
  .about_tech {
    grid-template-columns: repeat(3, minmax(0, 1fr)); 
    gap: 2rem; 
  }
  .about_item {
    gap: 0.75rem;
  }

  .tech_name {
    font-size: 1rem;
    line-height: 1.5rem;
  }
  .tech_status {
    font-size: 0.75rem;
    line-height: 1rem; 
  }
  .skill_status{
    font-size: 0.75rem;
    line-height: 1rem; 
  }
  .skill {
    font-size: 1rem;
    line-height: 1.5rem; 
  }
  .tables {
    grid-template-columns: repeat(3, minmax(0, 1fr)); 
    gap: 2rem; 
  }
  .tables_cart {
    gap: 0.75rem; 
  }
}
@media (min-width: 1024px) {
  .skill_status {
    font-size: 0.875rem;
    line-height: 1.25rem; 
  }
  .skill_img{
    height: 85%;
    width: 85%;
  }
  .skill {
    font-size: 1.125rem;
    line-height: 1.75rem;  
  }
  .tables_img {
    padding: 0.5rem; 
    width: 4rem; 
    height: 4rem; 
  }
  .tables_cart{
    padding-left: 0.75rem;
    padding-right: 0.75rem;
  } 
  .about_item {
    padding-left: 0.75rem; /* 12px */
    padding-right: 0.75rem; 
  }
  .item_img {
    padding: 0.5rem; 
    width: 4rem; 
    height: 4rem; 
  }
  .tech_img {
    height: 85%;
    width: 85%;
  }
  .tech_name {
    font-size: 1.125rem;
    line-height: 1.75rem; 
  }
  .tech_status {
    font-size: 0.875rem;
    line-height: 1.25rem; 
  }

}
@media (min-width: 1280px) {
  .about_tech {
    grid-template-columns: repeat(4, minmax(0, 1fr)); 
    gap: 2.5rem;} 
 }
@keyframes fadeInLeft {
  0% {
    opacity: 0;
    transform: translateX(100%);
  }

  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

.fadeins-1 {
  animation-delay: 500ms;
}

.fadeins-2 {
  animation-delay: 800ms;
}

</style>
