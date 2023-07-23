<template>
  <div>
    <div class="border-bottom-1 border-300 py-1">
      <div class="container">
        <div class="flex align-content-center justify-content-between">
          <Menubar :model="menuItems" />
          <div class="flex align-items-center">
            <Button
              aria-haspopup="true"
              rounded
              aria-controls="overlay_menu"
              severity="secondary"
              text
              class="hidden lg:flex p-2 -mr-2"
              @click="toggle"
            >
              <i class="  pi pi pi-user text-2xl cursor-pointer" />
              <i class="  pi pi-angle-down text-2xl cursor-pointer" />
            </Button>
            <Menu id="overlay_menu" ref="menu" :model="loginItems" :popup="true" />

            <Button icon="pi pi-map-marker text-2xl" class="ml-3 flex lg:hidden" severity="secondary" text rounded />
            <Button icon="pi pi-eye text-2xl" class="ml-3" severity="secondary" text rounded />
            <Button
              icon="pi pi-search text-2xl"
              class="ml-3"
              severity="secondary"
              text
              rounded
              aria-label="Search"
            />
            <div class="hidden sm:flex ml-4 border-left-1 border-900 h-2rem" />
            <a href="telto:8(495)153-04-49" class="white-space-nowrap hidden sm:flex ml-4 text-red-500 font-medium text-lg">8 (495) 153-04-49</a>
          </div>
        </div>
      </div>
    </div>
    <section class="container">
      <div class="flex justify-content-center sm:justify-content-start">
        <div class="grid sm:justify-content-center my-5 flex-column sm:flex-row">
          <div class="col-12 sm:col-6 md:col-4 lg:col-3 ">
            <div class="branch">
              <img src="/img/logo.svg" alt="logo" class="logo">
            </div>
          </div>
          <div class="block sm:hidden flex justify-content-center">
            <a href="telto:8(495)153-04-49" class=" text-red-500 font-bold text-3xl" style="width: fit-content">8 (495) 153-04-49</a>
          </div>

          <div class="col-12 sm:col-6 md:col-4 lg:col-3">
            <div class="branch">
              <div class="branch__metro branch__metro--gray" />
              <div>
                <h3 class="branch__title">
                  Цветной бульвар
                </h3>
                <p class="branch__subtitle">
                  Москва, Самотечная, 5
                </p>
                <Tag value="Круглосуточно" class="text-sm font-normal p-tag-primary" />
              </div>
            </div>
          </div>
          <div class="col-12 sm:col-6 md:col-4 lg:col-3">
            <div class="branch">
              <div class="branch__metro branch__metro--red" />
              <div>
                <h3 class="branch__title">
                  Преображенская площадь
                </h3>
                <p class="branch__subtitle">
                  Преображенская площадь
                </p>
                <p class="branch__description">
                  Ежедневно c 09:00 до 21:00
                </p>
              </div>
            </div>
          </div>
          <div class="col-12 sm:col-6 md:col-4 lg:col-3">
            <div class="branch">
              <div class="branch__metro branch__metro--gray" />
              <div>
                <h3 class="branch__title">
                  Бульвар Дмитрия Донского
                </h3>
                <p class="branch__subtitle">
                  Бульвар Дмитрия Донского
                </p>
                <p class="branch__description">
                  Ежедневно c 09:00 до 21:00
                </p>
              </div>
            </div>
          </div>
          <div class="col-12 sm:col-6 md:col-4 lg:col-3">
            <div class="branch">
              <div class="branch__metro branch__metro--yellow" />
              <div>
                <h3 class="branch__title">
                  Мичуринский проспект
                </h3>
                <p class="branch__subtitle">
                  Москва, Большая Очаковская, 3
                </p>
                <p class="branch__description">
                  Ежедневно c 09:00 до 21:00
                </p>
              </div>
            </div>
          </div>
          <div class="col-12 sm:col-6 md:col-4 lg:col-3">
            <div class="branch">
              <div class="branch__metro branch__metro--blue" />
              <div>
                <h3 class="branch__title">
                  Фили
                </h3>
                <p class="branch__subtitle">
                  Москва, Береговой проезд, 7
                </p>
                <p class="branch__description">
                  Ежедневно c 09:00 до 21:00
                </p>
              </div>
            </div>
          </div>
          <div class="col-12 sm:col-6 md:col-4 lg:col-3">
            <div class="branch">
              <div class="mr-3">
                <img src="../public/img/sun.svg" alt="sun" class="w-2rem">
              </div>
              <div>
                <div class="flex align-items-center">
                  <h3 class="branch__title">
                    г. Сочи
                  </h3>
                  <Tag value="cкоро" class="text-sm font-normal p-tag-danger ml-2 -mt-4" />
                </div>

                <p class="branch__subtitle">
                  Навагинская, 7
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="banner">
      <Carousel
        :value="products"
        :num-visible="1"
        :num-scroll="1"
        circular
        :responsive-options="responsiveOptions"
        :autoplay-interval="3000"
      >
        <template #item="slotProps">
          <div class="grid">
            <div class="col-12 md:col-6">
              <div class="relative p-5 sm:p-7 md:p-8  h-full flex flex-column justify-content-center">
                <img src="/img/border-left.svg" class="animation-icon--left w-3rem sm:w-1 absolute top-0 left-0" alt="">
                <h4 class=" mb-1 text-5xl md:text-7xl text-blue-700 w-6">
                  {{ slotProps.data.title }}
                </h4>
                <h6 class="text-left mt-0 text-4xl text-red-400">
                  {{ slotProps.data.subtitle }}
                </h6>
                <a v-if="slotProps.data.link" :href="slotProps.data.link" />
                <img src="/img/border-right.svg" class="animation-icon--right w-3rem sm:w-1 absolute bottom-0 right-0" alt="">
              </div>
            </div>
            <div class="col-12 md:col-6">
              <img :src="slotProps.data.image" class="w-full h-15rem md:h-30rem object-cover" style="object-position: center" alt="">
            </div>
          </div>
        </template>
      </Carousel>
    </section>
    <section class="awards">
      <div class="container">
        <h2 class="text-700 text-2xl md:text-4xl">
          Наши награды
        </h2>
        <div class="grid">
          <div class="col-12 md:col-6 lg:col-5 xl:col-3 mb-5">
            <Card class="h-full">
              <template #header>
                <img class="w-full h-full object-cover" alt="user header" src="https://lorlor.ru/images/ci1108668v480x320s0.jpg">
              </template>
              <template #title>
                "Клиника уха, горла и носа" в ТОП-30 частных клиник Москвы
              </template>
              <template #content>
                <p>
                  Премия Продокторов по мнению пациентов.
                </p>
                <span>18.07.23</span>
              </template>
            </Card>
          </div>
          <div class="col-12 md:col-6 lg:col-5 xl:col-3 mb-5">
            <Card class="h-full">
              <template #header>
                <img class="w-full h-full object-cover" alt="user header" src="https://lorlor.ru/images/ci1104996v480x320s0.jpg">
              </template>
              <template #title>
                Наша Клиника получила "Звезду Качества" за лучшее предприятие страны 2020 года.
              </template>
              <template #content>
                <span>18.07.23</span>
              </template>
            </Card>
          </div>
        </div>
      </div>
    </section>
    <section class="news-clinic">
      <div class="container">
        <h2 class="text-700 text-2xl md:text-4xl">
          Новости клиники
        </h2>
        <div class="grid">
          <div class="col-12 sm:col-6 lg:col-4" v-for="news in newsClinic" :key="news.subtitle">
            <Card class="h-full">
              <template #header>
                <img class="w-full h-full object-cover" alt="user header" :src="news.img">
              </template>
              <template #title>
                {{ news.title }}
              </template>
              <template #content>
                <p>
                  {{news.subtitle}}
                </p>
                <span>{{news.date}}</span>
              </template>
            </Card>
          </div>
        </div>
        <div class="flex justify-content-center mt-5">
          <Button label="Все новости" outlined  class="m-auto btn-primary border-noround  font-normal" size="large"/>
        </div>
      </div>
    </section>
    <section class="video">
      <div class="container">
        <h2 class="text-700 text-2xl md:text-4xl">
          Видео
        </h2>
        <div class="grid">
          <div class="col-12 sm:col-6 lg:col-4" v-for="video in videos" :key="video.img">
            <Card class="h-full">
              <template #header>
                <img class="w-full h-full object-cover" alt="user header" :src="video.img">
              </template>
              <template #title>
                {{ video.title }}
              </template>
              <template #content>
                <p>
                  {{video.subtitle}}
                </p>
              </template>
            </Card>
          </div>
        </div>
        <div class="flex justify-content-center mt-5">
          <Button label="Все видео" outlined  class="m-auto btn-primary border-noround  font-normal" size="large"/>
        </div>
      </div>
    </section>
    <section class="video">
      <div class="container">
        <h2 class="text-700 text-2xl md:text-4xl">
          Статьи
        </h2>
        <div class="grid">
          <div class="col-12 sm:col-6 lg:col-4" v-for="article in articles" :key="article.img">
            <Card class="h-full">
              <template #header>
                <img class="w-full h-full object-cover" alt="user header" :src="article.img">
              </template>
              <template #title>
                {{ article.title }}
              </template>
              <template #content>
                <p>
                  {{article.subtitle}}
                </p>
              </template>
            </Card>
          </div>
        </div>
        <div class="flex justify-content-center mt-5">
          <Button label="Все cтатьи" outlined  class="m-auto btn-primary border-noround  font-normal" size="large"/>
        </div>
      </div>
    </section>
  </div>
</template>
<script setup lang="ts">

import { ref } from 'vue'

const menuItems = ref([
  {
    label: 'Главная'
  },
  {
    label: 'Детский лор'
  },
  {
    label: 'Лор-врачи'
  },
  {
    label: 'Лор-операции'
  },
  {
    label: 'Услуги'
  },
  {
    label: 'Цены'
  },
  {
    label: 'Пациенту',
    items: [
      { lable: 'Онлайн-консультация', icon: 'pi pi-fw pi-file' },
      { lable: 'Тест слуха онлайн' },
      { lable: 'Вызов врача на дом' },
      { lable: 'Вызов медсестры на дом' },
      { lable: 'Акции' },
      { lable: 'Отзывы' },
      { lable: 'Второе мнение' },
      { lable: 'Вопрос-ответ' },
      { lable: 'Бесплатное лечение' },
      { lable: 'Прием по ДМС' },
      { lable: 'Налоговый вычет' },
      { lable: 'Статьи' },
      { lable: 'Контроль качества' },
      { lable: 'Рассрочка' },
      { lable: 'Подготовка к операции' },
      { lable: 'Партнеры' }
    ]
  },
  {
    label: 'Контакты'
  }
])
const loginItems = ref([
  {
    label: 'Войти в личный кабинет'
  },
  {
    label: 'Зарегистрироваться'
  }
])
const menu = ref()
const products = ref([
  {
    title: 'Поможем услышать мир',
    subtitle: 'Лучшие лор хирурги',
    link: 'Узнайне подробнее >>',
    image: '/img/bg1.jpg'
  },
  {
    title: 'Лор операция',
    subtitle: 'Лучшие лор хирурги',
    link: 'Узнайне подробнее >>',
    image: '/img/bg2.jpg'
  }, {
    title: 'Лор операция',
    subtitle: 'Лучшие лор хирурги',
    link: 'Узнайне подробнее >>',
    image: '/img/bg1.jpg'
  }, {
    title: 'Лор операция',
    subtitle: 'Лучшие лор хирурги',
    link: 'Узнайне подробнее >>',
    image: '/img/bg2.jpg'
  }
])
const videos = ref([
  {
    title: 'Букет на завтрак: чем полезен салат из роз?',
    subtitle: 'Наш врач-эндокринолог, диетолог Севастьянова Наталья готовит салат из лепестков роз в прямом эфире.',
    img: 'https://lorlor.ru/images/ci1155057v480x320s0.jpg'
  },
  {
    title: 'Исследование слуха методом КСВП под наркозом',
    img: 'https://lorlor.ru/images/ci1144151v480x320s0.jpg'
  },
  {
    title: 'Аденоиды: лечить или удалять?',
    img: 'https://lorlor.ru/images/ci1143865v480x320s0.jpg'
  },
  {
    title: 'Как побороть нафтизиновую зависимость?',
    subtitle: 'Какое обследование показано при периодически возникающих головокружениях?',
    img: 'https://lorlor.ru/images/ci1143777v480x320s0.jpg'
  },
  {
    title: 'Доктор Никонов ждет вас и готов помочь!',
    subtitle: 'Развенчиваем основные вопросы, которые могут мешать принятию решения.',
    img: 'https://lorlor.ru/images/ci1143532v480x320s0.jpg'
  }, {
    title: 'Антивозрастные стратегии на страже здоровья и красоты. Пошаговые инструкции.',
    subtitle: 'Вебинар от врача-диетолога, эндокринолога Севастьяновой Натальи Владимировны.',
    img: 'https://lorlor.ru/images/ci1141764v480x320s0.jpg'
  }, {
    title: 'Что такое аденоиды, почему они воспаляются и как проводится аденотомия',
    img: 'https://lorlor.ru/images/ci1141284v480x320s0.jpg'
  }, {
    title: 'Все о гайморотомии',
    img: 'https://lorlor.ru/images/ci1141283v480x320s0.jpg'
  }, {
    title: 'Тонзилэктомия',
    img: 'https://lorlor.ru/images/ci1119605v480x320s0.jpg'
  }
])
const newsClinic = ref([
  {
    title: 'Капли VS спрей',
    subtitle: 'Что подойдет именно вам? Рассказывает отоларинголог клиники - Анатолий Якушев.',
    img: 'https://lorlor.ru/images/ci1156347v480x320s0.jpg'
  },
  {
    title: 'Для чего необходимо слухопротезирование?',
    subtitle: 'Как проходит процедура в нашей клинике? Смотрите в новом ролике.',
    img: 'https://lorlor.ru/images/ci1156345v480x320s0.jpg'
  },
  {
    title: 'Ребенок боится врачей?',
    subtitle: 'Что с этим делать - рассказывает на видео наш оториноларинголог Рагим Садыхов.',
    img: 'https://lorlor.ru/images/ci1156336v480x320s0.jpg'
  },
  {
    title: 'Эпизодически кружится голова?',
    subtitle: 'Какое обследование показано при периодически возникающих головокружениях?',
    img: 'https://lorlor.ru/images/ci1156318v480x320s0.jpg'
  },
  {
    title: 'С нами легко, даже если вы приехали оперироваться из другой страны!',
    subtitle: 'Развенчиваем основные вопросы, которые могут мешать принятию решения.',
    img: 'https://lorlor.ru/images/ci1156306v480x320s0.jpg'
  }, {
    title: 'Не чистите уши при детях!',
    subtitle: 'И другие способы, как НЕ надо чистить уши. Рассказывает на видео эксперт клиники Якушев Анатолий Андреевич.',
    img: 'https://lorlor.ru/images/ci1156278v480x320s0.jpg'
  }, {
    title: 'Когда необходимо делать пункцию?',
    subtitle: 'Об этом рассказал Акопян Карен - отоларинголог клиники.',
    img: '\thttps://lorlor.ru/images/ci1156277v480x320s0.jpg'
  }, {
    title: 'Открытие филиала "Клиники уха, горла и носа" в Сочи состоится 31 июля',
    subtitle: 'Мы открываем новый филиал в городе Сочи.',
    img: 'https://lorlor.ru/images/ci1156221v480x320s0.jpg'
  }, {
    title: 'Капли VS спрей',
    subtitle: 'Что подойдет именно вам? Рассказывает отоларинголог клиники - Анатолий Якушев.',
    img: 'https://lorlor.ru/images/ci1156148v480x320s0.jpg'
  }
])
const articles = ref([
  {
    title: 'Аденоиды - все о заболевании',
    subtitle: 'Что такое аденоиды, причины, симптомы, степени гипертрофии, методы диагностики и лечения аденоидов.',
    img: 'https://lorlor.ru/images/ci1155716v480x320s0.jpg'
  },
  {
    title: 'Синдром пустого носа',
    subtitle: 'Все о губительном для качества жизни заболевании.',
    img: 'https://lorlor.ru/images/ci1143680v480x320s0.jpg'
  },
  {
    title: 'Фурункул наружного слухового прохода',
    subtitle: 'Фурункул уха - болезненное воспаление волосяного мешочка слухового канала. Симптомы, анатомия и лечение.',
    img: 'https://lorlor.ru/images/ci1143420v480x320s0.jpg'
  },
  {
    title: 'Тиннитус (звон в ушах): все о беспокоящем симптоме',
    subtitle: 'Глубинные причины возникновения в связи с анатомией человека, влияние на психику, грамотный подход к лечению.',
    img: 'https://lorlor.ru/images/ci1142781v480x320s0.jpg'
  },
  {
    title: 'Фармакотерапия никотиновой зависимости',
    subtitle: 'Препараты для лечения табачной зависимости.',
    img: 'https://lorlor.ru/images/ci1141955v480x320s0.jpg'
  }, {
    title: 'Спирометрия - что это и зачем она нужна?',
    subtitle: 'Спирометрия - базисный метод функциональной диагностики внешнего дыхания.',
    img: 'https://lorlor.ru/images/ci1141311v480x320s0.jpg'
  }, {
    title: 'Слизь в горле или синдром постназального затекания',
    subtitle: 'В этой статье объясняются симптомы и причины слизи в носоглотке, а также способы диагностики и лечения.',
    img: 'https://lorlor.ru/images/ci1141194v480x320s0.jpg'
  }, {
    title: 'Экссудативный средний отит у детей. Симптомы, причины и лечение',
    subtitle: 'Негнойное заболевание среднего уха, при котором в среднем ухе происходит накопление патологической жидкости.',
    img: 'https://lorlor.ru/images/ci1106513v480x320s0.jpg'
  }, {
    title: 'Синдром Маршалла (PFAPA синдром)',
    subtitle: 'Что такое синдром Маршалла, клиническая картина, симптомы, лечение.',
    img: 'https://lorlor.ru/images/ci1105933v480x320s0.jpg'
  }
])
const toggle = (event) => {
  menu.value.toggle(event)
}

const responsiveOptions = ref([

])
</script>
