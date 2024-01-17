<template>
  <main
    class="top">
    <div class="space-y-2 text-center md:text-left px-10">
      <p class="fadein-up" style="color:#fde68a">Привет, меня зовут</p>
      <h1 class="top_name fadein-up">Кулушев Дмитрий</h1>
      <div class="py-2">
        <h1
          class="top_typing fadein-up"
          ref="typewriter">
          <span class="wrap">{{ txt }}</span>
        </h1>
      </div>
      <p class="top_text fade-in-from-left">Привет это мой сайт - визитка <span class="wave">👋🏼</span></p>
      <br>
      <p class="top_text fade-in-from-left"> Возраст : 35 лет</p>
      <p class="top_text fade-in-from-left"> Город : Москва</p>
      <p class="top_text fade-in-from-left"> Образование: высшее</p>
    </div>
    <div class="top_img fadein-right">
      <img alt="avatar" fetchpriority="high" width="150" height="150" decoding="async" data-nimg="1"
        class="avatar pict" src="https://stihi.ru/pics/2020/09/04/2245.jpg">
    </div>
  </main>
  
</template>

<script>
export default {
  name: 'HomeView',
  data() {
    return {
      toRotate: ["Разработчик сайтов", "Маркетолог", "Студент GeekBrains", "Директолог"],
      period: 2000,
      txt: '',
      loopNum: 0,
      isDeleting: false,
    };
  },
  mounted() {
    this.$nextTick(() => {
      this.tick();
    });
  },
  methods: {
    tick() {
      let typewriter = this.$refs.typewriter;

      if (!typewriter) {
        return;
      }

      let i = this.loopNum % this.toRotate.length;
      let fullTxt = this.toRotate[i];

      this.txt = this.isDeleting ? fullTxt.substring(0, this.txt.length - 1) : fullTxt.substring(0, this.txt.length + 1);
      typewriter.innerHTML = `<span class="wrap">${this.txt}</span>`;

      let that = this;
      let delta = 200 - Math.random() * 100;

      if (this.isDeleting) {
        delta /= 2;
      }

      if (!this.isDeleting && this.txt === fullTxt) {
        delta = this.period;
        this.isDeleting = true;
      } else if (this.isDeleting && this.txt === '') {
        this.isDeleting = false;
        this.loopNum++;
        delta = 500;
      }

      setTimeout(() => {
        that.tick();
      }, delta);
    },
  }
}
</script>

<style>
body {
  overflow-y: scroll;
  overflow-x: hidden;
}
.top {
  display: flex; 
  padding-top:50px;
  flex-direction: column-reverse; 
  gap: 2rem; 
  align-items: center; 
}
.top_text {
  padding-right: 1rem; 
  color: #fff; 

}
.top_img {
  display: flex; 
  justify-content: center; 
  
}
.avatar{
  border-radius: 9999px; 
  border-width: 4px; 
  border: 0.2rem solid  #F59E0B ;
  width: 65%; 
}
.top_name {
  font-size: 2.25rem;
  line-height: 2.5rem; 
  font-weight: 700; 
  color: #ffffff;
}
.top_typing {
  font-size: 1.25rem;
  line-height: 1.75rem; 
  font-weight: 600; 
  color: transparent; 
  background-clip: text; 
  background-image:radial-gradient(circle, #ffffff, #F59E0B);; 
  background-color: #F59E0B; 
}

.typewrite>.wrap {
  border-right: 0.08em solid #fff;
}

.wave {
  animation-name: wave-animation;
  animation-duration: 2.5s;
  animation-iteration-count: infinite;
  transform-origin: 70% 70%;
  display: inline-block
}
@media (min-width: 768px) {
  .top {
    margin-top: 0.25rem; 
    flex-direction: row; 
    gap: 4rem; 
    justify-content: center; }
  .top_img {
    justify-content: flex-start;}
  .top_name {
    font-size: 3rem;
    line-height: 1; }
  .top_typing {
    font-size: 1.5rem;
    line-height: 2rem;
  }
  .avatar{
  height: auto; }
 }

@keyframes wave-animation {
  0% {
    transform: rotate(0deg)
  }

  10% {
    transform: rotate(14deg)
  }

  20% {
    transform: rotate(-8deg)
  }

  30% {
    transform: rotate(14deg)
  }

  40% {
    transform: rotate(-4deg)
  }

  50% {
    transform: rotate(10deg)
  }

  60% {
    transform: rotate(0deg)
  }

  to {
    transform: rotate(0deg)
  }
}

.pict {
  box-shadow: 0px 0px 73px -9px rgba(255,219,112,0.44);
  -webkit-box-shadow: 0px 0px 73px -9px rgba(255,219,112,0.44);
  -moz-box-shadow: 0px 0px 73px -9px rgba(255,219,112,0.44);
}

.fadein-up {
  opacity: 0;
  animation-name: fadeInUp;
  animation-duration: 0.5s;
  animation-fill-mode: forwards;
  animation-delay: 500ms;
}


@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translate3d(0, 100%, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}

.fade-in-from-left {
  opacity: 0;
  animation: fadeInLeft 0.5s ease-out forwards;
  animation-delay: 500ms;
}

@keyframes fadeInLeft {
  0% {
    opacity: 0;
    transform: translateX(-100%);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

.fadein-right {
  opacity: 0;
  animation: fadeInRight 0.5s ease-out forwards;
  animation-delay: 500ms;
}

@keyframes fadeInRight {
  0% {
    opacity: 0;
    transform: translateX(100%);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

.fadein-bot {
  opacity: 0;
  animation: fadeInBot 0.5s forwards;
}

@keyframes fadeInBot {
  from {
    opacity: 0;
    transform: translate3d(0, -100%, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}

.fadein-1 {
  animation-delay: 200ms;
}
.fadein-2 {
  animation-delay: 400ms;
}
.fadein-3 {
  animation-delay: 600ms;
}
.fade-500 {
  animation-delay: 500ms;
}
</style>
