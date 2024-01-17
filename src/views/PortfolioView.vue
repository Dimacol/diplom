<template>
  <div class="portfolio">
    <article data-page="about">
      <header>
        <div
          class="fadein-bot portfolio_title">
          <h4>Мои проекты</h4>
          <h4 class="title_bottom">
            все мои проекты </h4>
        </div>
      </header>
      <section>
        <div>
          <div class="portfolio_carts fade-zoom-in">
            <div v-for="item in items" :key="item.id">
              <div
                class="item-card cart ">
                <div class="cart_img">
                  <img  class="item_img" alt="HTML" loading="lazy" decoding="async" data-nimg="1"
                    :src="'/img/portfolio-' + item.imageUrl + '.png'">
                </div>
                <div class="item">
                  <div class="item_name">{{ item.name }}
                  </div>
                  <div class="item_status">
                    {{ item.status }}</div>
                  <div class="item_tech">
                    {{ item.tech }}
                  </div>
                  <div class="icons">
                    <div class="icons_pointer">
                      <a v-if="item.github !== 'null'"
                        :href="item.github" target="_blank" rel="noreferrer"
                        title="Github репозиторий" class="item_icon">
                        <svg stroke="currentColor"
                          fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round"
                          height="16" width="16" xmlns="http://www.w3.org/2000/svg">
                          <path
                            d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44
                             5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09
                              1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22">
                          </path>
                        </svg></a>
                        <a v-if="item.demo !== 'null'" :href="item.demo" target="_blank" rel="noreferrer"
                        title="Посмотреть проект" class="item_icon">
                        <svg stroke="currentColor"
                          fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round"
                          height="18" width="18" xmlns="http://www.w3.org/2000/svg">
                          <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                          <polyline points="15 3 21 3 21 9"></polyline>
                        <line x1="10" y1="14" x2="21" y2="3"></line>
                      </svg></a></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

  </article>
</div></template>
<script>
export default {
  data() {
    return {
      activeTab: 1,
      items: [
        {
          id: 1,
          name: 'Сайт-визитка',
          imageUrl: 'mysite',
          status: 'Мой личный веб-сайт, я создал этот веб-сайт, чтобы показать свой профиль, навыки и проекты.',
          tech: 'VueJS 3, CSS',
          github: 'https://github.com/Dimacol/diplom.git',
          demo: 'https://kulushevdima.netlify.app/'
        },
        {
          id: 2,
          name: 'ToDo List',
          imageUrl: 'todo',
          status: ' Приложение To-Do List — современная замена записок на холодильнике, стикерам на мониторе и блокнотам',
          tech: 'VueJS 3, CSS',
          github: 'https://github.com/Dimacol/todo-list.git',
          demo: 'null'
        },
        {
          id: 3,
          name: 'Сообщество VK',
          imageUrl: 'wedaravk',
          status: 'Введение сообщества в VK.Студия коррекционного ухода по телу и телесно-ориентированным техникам.',
          tech: 'VK admin',
          github: 'null',
          demo: 'https://vk.com/vedaranmsk'
        },
        {
          id: 4,
          name: 'Магазин одежды',
          imageUrl: 'store',
          status: 'Разработка интернет магазина одежды. Использован фреймворк Vue. Многостраничный сайт.Удобная навигация, понятная структура, очевидные и призывающие к действию кнопки покупки и корзина ',
          tech: 'VueJS 3, CSS',
          github: 'https://github.com/Dimacol/Vue7.git',
          demo: 'null'
        },
        {
          id: 5,
          name: 'Сайт Ведара',
          imageUrl: 'sitewedara',
          status: 'Разработка web-сайта SPA-салона «Ведара»,предназначенного для ознакомления потенциальных клиентов с компанией испектром предоставляемых услуг, а так же упорядочивания и ускорения деятельности администратора',
          tech: 'WordPress',
          github: 'null',
          demo: 'https://wedara.ru/'
        }
      ]
    };
  }
}
</script>


<style>
.portfolio {
  padding-top: 1.25rem;
  padding-bottom: 1.25rem; 
  padding-left: 1.25rem;
  padding-right: 1.25rem; 
  margin-left: 0.75rem;
  margin-right: 0.75rem; 
  text-align: left; 
}
.portfolio_title {
  display: flex; 
  margin-bottom: 2.5rem; 
  flex-direction: column; 
  justify-content: center; 
  align-items: center; 
  font-size: 1.5rem;
  line-height: 2rem; 
  font-weight: 700; 
  color: #ffffff; 
}
.title_bottom {
  font-size: 1rem;
  line-height: 1.5rem; 
  font-weight: 400; 
 
}
.portfolio_carts {
  display: grid; 
  padding-bottom: 8rem; 
  grid-template-columns: repeat(1, minmax(0, 1fr)); 
  gap: 1rem; 
}
.cart {
  display: flex; 
  padding-top: 1.25rem;
  padding-bottom: 1.25rem; 
  padding-left: 1.25rem;
  padding-right: 1.25rem; 
  flex-direction: column; 
  gap: 0.5rem; 
  align-items: center; 
  border-radius: 0.25rem; 
  border-radius: 0.75rem; 
  border-width: 1px; 
  background: #1e1e1f;
  border-color: #383838;
}

.icons {
  display: flex; 
  justify-content: flex-end; 
  width: 100%; 
}
.icons_pointer {
  display: flex; 
  gap: 0.5rem; 
  align-items: flex-end; 
  cursor: pointer; 
}
.item-card:hover {
  transition: transform 0.3s ease;
  transform: translateY(-8px);
}
.item { 
  display: flex; 
  flex-direction: column; 
  gap: 0.5rem; 
  align-items: center; 
  width: 100%; 
  font-size: 0.875rem;
  line-height: 1.25rem; 
}
.item_name {
  font-weight: 500;
  color:#ffffff
} 
.item_status {
  width: 100%; 
  text-align: left;
  color: #c1c1c1;
} 
.item_tech {
  margin-top: 1rem; 
  width: 100%; 
  font-size: 0.875rem;
  line-height: 1.25rem; 
  text-align: left;
  color: rgb(253 230 138); 
}
.item_icon {
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 300ms; 
}
.item_img {
  width:100%;
  border-radius: 25px;
  height: 100%;

}
svg:hover{
  stroke: #f2d786;
}
@media (min-width: 768px) { 
  .portfolio{
    padding-top: 2.5rem;
    padding-bottom: 2.5rem; 
    padding-left: 3rem;
    padding-right: 3rem; }

  .portfolio_carts{
    grid-template-columns: repeat(3, minmax(0, 1fr)); 
    gap: 0.75rem;
 }
 .cart{
    gap: 0.75rem;
 }
 .item {
  font-size: 1rem;
line-height: 1.5rem; 
}
.item_status {
  font-size: 0.75rem;
  line-height: 1rem; 
} 
}
@media (min-width: 1280px) {
  .portfolio_carts { 
    grid-template-columns: repeat(3, minmax(0, 1fr)); 
    gap: 0.75rem;
  }
  .cart {
    padding-left: 1.25rem;
    padding-right: 1.25rem; 
  } 
  .item {
    font-size: 1.125rem;
    line-height: 1.75rem;
  } 
  .item_status {
    font-size: 0.875rem;
    line-height: 1.25rem; 
  }
 }
@keyframes fadeZoomIn {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

.fade-zoom-in {
  animation: fadeZoomIn 1s ease-in-out;
}
</style>