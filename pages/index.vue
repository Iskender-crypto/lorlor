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
    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusantium aut fugiat impedit itaque, minus quam voluptas? Cupiditate deserunt doloremque, dolores ea esse est ex excepturi iusto maiores neque nobis, omnis porro praesentium provident quidem rerum sunt temporibus tenetur? Accusantium assumenda cum eaque, ipsum laboriosam molestias perspiciatis quaerat quia quidem, quos sed, veniam? Consequatur cumque exercitationem impedit, in inventore, libero minima nam natus nostrum obcaecati, perferendis quaerat reiciendis repudiandae ullam veritatis voluptatem voluptatum. Adipisci alias aspernatur assumenda at debitis deleniti distinctio doloremque doloribus ducimus ea, ex expedita hic ipsa itaque laborum magnam nesciunt nostrum perferendis, perspiciatis quaerat tempore vero voluptas. Aut dolore ea eligendi magni necessitatibus odio suscipit unde? Ad alias doloremque incidunt odit ut. Alias aliquid beatae blanditiis consectetur cum, cupiditate dolores eius eligendi excepturi ipsum laborum minima minus placeat quam quibusdam quis rem similique sint sunt tempore ullam vel voluptas voluptates! Atque est eveniet inventore quae quaerat qui quia, unde? A accusantium adipisci atque aut, autem beatae consectetur, consequuntur cupiditate dolorem doloremque dolores ea eaque impedit ipsam iusto laudantium minus obcaecati odio officiis omnis perferendis possimus quaerat quisquam quos sequi sunt suscipit temporibus totam unde veritatis vero vitae voluptates voluptatum. A ad adipisci, consequuntur corporis culpa deleniti deserunt doloremque dolores doloribus eligendi enim est eveniet ipsam maiores modi natus obcaecati quas quia quos reprehenderit saepe, sint sit ut? Aliquam animi aut beatae distinctio exercitationem ipsum nostrum nulla quaerat quam, quasi, similique, temporibus! Ab consequatur corporis debitis ducimus est eveniet exercitationem explicabo facere fugit harum impedit in inventore iure iusto laborum magni, nam natus odit possimus quam quas quidem quisquam rem rerum sequi ullam ut veniam! Ab accusamus, ea, error et eum excepturi impedit ipsa libero nemo neque nostrum officia quas rem, repellendus sequi. Dolores eius inventore iusto magni quam repellendus sequi sint tempore. A assumenda at consectetur cumque, dignissimos dolor doloremque eaque est, ex fugiat fugit id laboriosam quas ratione saepe tenetur vel. Ab cum dignissimos earum iste libero molestiae nisi odio odit praesentium ullam! Amet asperiores assumenda consequatur consequuntur esse libero nam numquam officiis pariatur velit. Accusantium aliquam, autem consequuntur corporis cum deserunt dolorum excepturi exercitationem facere fugit hic id illum libero, molestiae mollitia neque odio odit officiis possimus provident quibusdam reprehenderit veritatis! Ab ad alias animi consequuntur debitis doloremque dolores ducimus ea eius et explicabo facilis in modi nostrum, nulla odit praesentium quae quasi repellendus rerum soluta vero voluptas? Deserunt dolor enim et, ipsam minus soluta. Aliquam asperiores eaque necessitatibus, nesciunt nihil pariatur quam reiciendis tempore. Aliquid architecto at eius harum illum minus mollitia nam, nostrum officiis praesentium quia repellat soluta ut? Aliquid deserunt est id nesciunt pariatur. Consectetur dolor dolorem incidunt sapiente voluptate. Accusamus, architecto debitis ea, eaque earum enim incidunt neque, numquam omnis provident qui reiciendis ullam vero? Ad eligendi ipsam provident. A ab accusamus adipisci aperiam aspernatur blanditiis consectetur cum debitis delectus enim est eum eveniet excepturi facilis fuga incidunt inventore ipsum minima nam odit officiis optio perspiciatis porro praesentium quam quis repellendus, repudiandae rerum similique sit tempore ullam unde vitae! Aliquid consequuntur, eos?
    </p>
  </div>
</template>
<script setup lang="ts">

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
    title: 'Лор операциo',
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
const toggle = (event) => {
  menu.value.toggle(event)
}

const responsiveOptions = ref([

])
const getSeverity = (status) => {
  switch (status) {
    case 'INSTOCK':
      return 'success'

    case 'LOWSTOCK':
      return 'warning'

    case 'OUTOFSTOCK':
      return 'danger'

    default:
      return null
  }
}
</script>
