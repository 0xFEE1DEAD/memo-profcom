<template>
<div :class="{'mobile-menu': true, 'mobile-menu-open': mobileMenu}">
  <div>
    <div v-for="(el, i) in links" class="mobile-menu-element" :key="i">
      <a @click="closeMobileMenu" :href="'#' + el['src']">{{el['name']}}</a>
    </div>
  </div>
</div>
<div :class="{'main-container': true, 'main-container-mobile': mobileMenu}">
  <div :class="{'menu': true, 'menu-mobile-on': mobileMenu}">
    <div class="menu-block-logo">
      <div>
        <span>памятка</span>
        <span style="position: relative">
          <img class="menu-block-logo-bki" src="./assets/images/bki.png">
        </span>
      </div>
      <div>
        <span>для первокурсников</span>
      </div>
    </div>
    <div class="menu-hrefs">
      <span v-for="(el, i) in links" :class="{'menu-hrefs-element-margin': i > 0}" :key="i">
        <a :href="'#' + el['src']">{{el['name']}}</a>
      </span>
    </div>

    <div class="menu-button">
      <burger-btn :status="mobileMenu" ref="b-btn" @toggle="menuToggle"></burger-btn>
    </div>
  </div>

  <div class="poster">
    <img class="poster-image" src="./assets/images/poster.png">
  </div>

  <information-block>
    <template v-slot:header>
      <a :name="links[0]['src']"></a>{{links[0]['name']}}
    </template>

    <div class="contacts-wrap-first">
      <contact-block avatar_src="dekan.jpg">
        <template v-slot:fullname>
          Карнаухова Вера Канстантиновна
        </template>
        <template v-slot:position>
          декан
        </template>
        <template v-slot:contacts>
          <a href="tel:8395212355">8 (395) 21-23-55</a>, <a class="blue-href" href="mailto:dekanat@isu.ru">dekanat@isu.ru</a>
        </template>
      </contact-block>

      <contact-block>
        <template v-slot:fullname>
          СЕЛЕЗНЕВА ТАИСИЯ СЕРГЕЕВНА
        </template>
        <template v-slot:position>
          заместитель декана по воспитательной работе
        </template>
        <template v-slot:contacts>
          <a class="blue-href" href="https://vk.com/univer1945">vk.com/univer1945</a>
        </template>
      </contact-block>

      <div class="contacts-divider"></div>

      <contact-block>
        <template v-slot:fullname>
          КРАСОВСКАЯ АНГЕЛИНА
        </template>
        <template v-slot:position>
          председатель профбюро
        </template>
        <template v-slot:contacts>
          <a href="tel:89041550352">8 (9041) 55-03-52</a>, <a class="blue-href" href="https://vk.com/linkras">vk.com/linkras</a>
        </template>
      </contact-block>
    </div>

    <div class="instagram-group">
      <div class="instagram-subgroup">
        <instagram-block>
          <a href="https://www.instagram.com/irkutskuniversity/">
            игу
          </a>
        </instagram-block>
        <div></div>
        <instagram-block>
          <a href="https://www.instagram.com/fbki_isu/">
            фбки
          </a>
        </instagram-block>
      </div>
      <div class="instagram-subgroup" style="margin-left: 20px">
        <instagram-block>
          <a href="https://www.instagram.com/proffbki/">
            профбюро фбки
          </a>
        </instagram-block>
        <div></div>
        <instagram-block>
          <a href="https://www.instagram.com/my_isu_/">
            профком игу
          </a>
        </instagram-block>
      </div>
    </div>
  </information-block>

  <information-block :dashed='false'>
    <template v-slot:header>
      <a :name="links[1]['src']"></a>{{links[1]['name']}}
    </template>

    <div class="micro-blocks-wrap">
      <micro-contact-block>
        <template v-slot:title>
          УПРАВЛЕНИЕ ПЕРСОНАЛОМ
        </template>
        <div class="contacts-wrap">
          <contact-block :small="true">
            <template v-slot:fullname>
                Родионова Светлана
            </template>
            <template v-slot:position>
              <a href="https://vk.com/chsvetta">vk.com/chsvetta</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
          <contact-block :small="true">
            <template v-slot:fullname>
                Суркова Алина
            </template>
            <template v-slot:position>
              <a href="https://vk.com/alinasurkova38">vk.com/alinasurkova38</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
        </div>
      </micro-contact-block>   

      <micro-contact-block>
        <template v-slot:title>
          РЕКЛАМА
        </template>
        <div class="contacts-wrap">
          <contact-block :small="true">
            <template v-slot:fullname>
                Гарбуз Никита
            </template>
            <template v-slot:position>
                <a href="https://vk.com/the_artez">vk.com/the_artez</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
          <contact-block :small="true">
            <template v-slot:fullname>
                Тимофеева Дарья
            </template>
            <template v-slot:position>
              <a href="https://vk.com/kefirchick1">vk.com/kefirchick1</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
        </div>
      </micro-contact-block>

      <micro-contact-block>
        <template v-slot:title>
          ПРИКЛАДНАЯ ИНФОРМАТИКА
          <div style="width: 100%; font-size: 16px; text-align:center">разработка ПО</div>
        </template>
        <div class="contacts-wrap">
          <contact-block :small="true">
            <template v-slot:fullname>
                Лубсанов Антон
            </template>
            <template v-slot:position>
                <a href="https://vk.com/bleach_ant">vk.com/bleach_ant</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
          <contact-block :small="true">
            <template v-slot:fullname>
                Спиридонов Антон
            </template>
            <template v-slot:position>
                <a href="https://vk.com/sp_anton">vk.com/sp_anton</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
        </div>
      </micro-contact-block>

      <micro-contact-block>
        <template v-slot:title>
          ПРИКЛАДНАЯ ИНФОРМАТИКА
          <div style="width: 100%; font-size: 16px; text-align:center">в дизайне, в управлении</div>
        </template>
        <div class="contacts-wrap">
          <contact-block :small="true">
            <template v-slot:fullname>
                Абсалямова Аделина
            </template>
            <template v-slot:position>
                <a href="https://vk.com/delll_a">vk.com/delll_a</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
          <contact-block :small="true">
            <template v-slot:fullname>
                Спиридонов Антон
            </template>
            <template v-slot:position>
                <a href="https://vk.com/sp_anton">vk.com/sp_anton</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
        </div>
      </micro-contact-block>

      <micro-contact-block>
        <template v-slot:title>
          СЕРВИС
        </template>
        <div class="contacts-wrap">
          <contact-block :small="true">
            <template v-slot:fullname>
              Ангажанова Виктория
            </template>
            <template v-slot:position>
              <a href="https://vk.com/angazhanova">vk.com/angazhanova</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
          <contact-block :small="true">
            <template v-slot:fullname>
              Доржиева Светлана
            </template>
            <template v-slot:position>
              <a href="https://vk.com/svetka_ddd">vk.com/svetka_ddd</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
          <contact-block :small="true">
            <template v-slot:fullname>
                Нурметова Нурият
            </template>
            <template v-slot:position>
              <a href="https://vk.com/nnurmetova">vk.com/nnurmetova</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
        </div>
      </micro-contact-block>

      <micro-contact-block>
        <template v-slot:title>
          ТУРИЗМ
        </template>
        <div class="contacts-wrap">
          <contact-block :small="true">
            <template v-slot:fullname>
              Крижевец Александра
            </template>
            <template v-slot:position>
              <a href="https://vk.com/ak18536">vk.com/ak18536</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
          <contact-block :small="true">
            <template v-slot:fullname>
              Новгородцев Дмитрий
            </template>
            <template v-slot:position>
              <a href="https://vk.com/ditronic">vk.com/ditronic</a>
            </template>
            <template v-slot:contacts></template>
          </contact-block>
        </div>
      </micro-contact-block>
    </div>
  </information-block>

  <information-block :dashed="false">
    <template v-slot:header>
      <a :name="links[2]['src']"></a>{{links[2]['name']}}
    </template>
    <div class="curators-body">
      <div class="curators-body-col">
        <div class="simple-block">
          <div class="simple-block-title">
            УПРАВЛЕНИЕ ПЕРСОНАЛОМ
          </div>
          <div class="simple-block-string">
            Волохова Елена Александровна
          </div>
        </div>

        <div class="simple-block">
          <div class="simple-block-title">
            ПРИКЛАДНАЯ ИНФОРМАТИКА
          </div>
          <div class="simple-block-string">
            Зорина Галина Александровна
          </div>
          <div class="simple-block-string">
            Сокольская Мария Александровна
          </div>
          <div class="simple-block-string">
            Инешина Ольга Андревна
          </div>
          <div class="simple-block-string">
            Угорская Яна Алексеевна
          </div>
        </div>
        <div class="simple-block">
          <div class="simple-block-title">
            ТУРИЗМ
          </div>
          <div class="simple-block-string">
            Иванов Иван Иванович
          </div>
        </div>
      </div>
      <div class="curators-body-col">
        <div class="simple-block">
          <div class="simple-block-title">
            РЕКЛАМА
          </div>
          <div class="simple-block-string">
            Подкаменная Елизавета Васильевна
          </div>
          <div class="simple-block-string">
            Иовлева Юлия Сергеевна
          </div>
        </div>
        <div class="simple-block">
          <div class="simple-block-title">
            Сервис
          </div>
          <div class="simple-block-string">
            Иванов Иван Иванович
          </div>
        </div>
      </div>
    </div>
  </information-block>

  <information-block style="margin-top: -60px">
    <template v-slot:header>
      <a name="for-students"></a>
      <a :name="links[3]['src']"></a>{{links[3]['name']}}
    </template>
    <div class="for-students-wrap">
      <div>
        <div class="simple-block">
          <div class="simple-block-title">
            По вопросам справок обращаться на почту:
          </div>
          <div class="simple-block-string">
            <a class="blue-href" href="mailto:uvarovskaya.dekanat@mail.ru">uvarovskaya.dekanat@mail.ru</a>
          </div>
        </div>
        <div class="simple-block">
          <div class="simple-block-title">
            по остальным вопросам:
          </div>
          <div class="simple-block-string">
            <a class="blue-href" href="mailto:service@sr.isu.ru">service@sr.isu.ru</a>
          </div>
        </div>
        <div class="simple-block">
          <div class="simple-block-title">
            по вопросам оплаты/квитанции на почту:
          </div>
          <div class="simple-block-string">
            <a class="blue-href" href="mailto:service@sr.isu.ru">service@sr.isu.ru</a>
          </div>
        </div>
      </div>

      <div>
        <div class="simple-block">
          <div class="simple-block-title">
            срочные вопросы по телефону
          </div>
          <div class="simple-block-string">
            <a class="blue-href" href="tel:426417">42-64-17</a>
          </div>
        </div>
        <div class="simple-block">
          <div class="simple-block-title">
            работает горячая линия:
          </div>
          <div class="simple-block-string">
            <a class="blue-href" href="tel:89641167226">89641167226</a>
          </div>
        </div>
        <div class="simple-block">
          <div class="simple-block-title">
            по коротким и важным вопросам:
          </div>
          <div class="simple-block-string">
            <a class="blue-href" href="https://t-do.ru/FBKI_dekanat">@FBKI_dekanat (телеграм)</a>
          </div>
        </div>
      </div>
    </div>
  </information-block>

  <information-block :dashed="false">
    <template v-slot:header>
      <a :name="links[4]['src']"></a>{{links[4]['name']}}
    </template>
    <div style="width: 100%; margin-top: -30px;">
      <hull-map></hull-map>
    </div>
  </information-block>

  <information-block :dashed="false">
    <template v-slot:header>
      Расположение
    </template>
    <div style="height: 300px; width: 100%; margin-top: -30px">
      <l-map :locationString="locationString" style="border-radius: 10px;"></l-map>
    </div>
  </information-block>
</div>

<div :class="{'footer': true, 'element-del': mobileMenu}">
  <div class="footer-location">
    <div>
      адрес
    </div>
    <div style="width: 300px">
      {{locationString}}
    </div>
  </div>
  <div class="footer-author">
    <div><a href="https://www.instagram.com/dilstey/">design by dilstey</a></div>
    <div><a href="https://github.com/0xFEE1DEAD">0xfee1dead</a></div>
  </div>
</div>
</template>

<script>
import informationBlock from './components/informationBlock.vue'
import contactBlock from './components/contactBlock.vue'
import instagramBlock from './components/instagramBlock.vue'
import microContactBlock from './components/microContactBlock.vue'
import LMap from './components/map.vue'
import hullMap from './components/hullMap.vue'
import burgerBtn from './components/burgerButton.vue'

export default {
  name: 'App',
  components: {
    informationBlock,
    contactBlock,
    instagramBlock,
    microContactBlock,
    LMap,
    hullMap,
    burgerBtn
  },
  data() {
    return {
      locationString: '664033, г. Иркутск, ул. Лермонтова, 126, VI корпус ИГУ',
      mobileMenu: false,
      links: [
        {
          'name': 'контакты',
          'src': 'contacts'
        },
        {
          'name': 'профшефы',
          'src': 'prof-chefs'
        },
        {
          'name': 'кураторы',
          'src': 'curators'
        },
        {
          'name': 'для студентов',
          'src': 'for-students'
        },
        {
          'name': 'карта корпуса',
          'src': 'hull-map'
        },
      ]
    }
  },
  methods: {
    menuToggle(menuStatus) {
      console.log(menuStatus)
      this.mobileMenu = menuStatus
    },
    closeMobileMenu() {
      this.mobileMenu = false
    }
  }
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }

  @font-face {
    font-family: 'Bebas Neue';
    src: local('Bebas Neue Thin'), local('BebasNeue-Thin'), url('./assets/fonts/bebasneuethin.woff2') format('woff2'), url('./assets/fonts/bebasneuethin.woff') format('woff'), url('./assets/fonts/bebasneuethin.ttf') format('truetype');
    font-weight: 100;
    font-style: normal;
  }
  @font-face {
      font-family: 'Bebas Neue';
      src: local('Bebas Neue Light'), local('BebasNeue-Light'), url('./assets/fonts/bebasneuelight.woff2') format('woff2'), url('./assets/fonts/bebasneuelight.woff') format('woff'), url('./assets/fonts/bebasneuelight.ttf') format('truetype');
      font-weight: 200;
      font-style: normal;
  }
  @font-face {
      font-family: 'Bebas Neue';
      src: local('Bebas Neue Book'), local('BebasNeueBook'), url('./assets/fonts/bebasneuebook.woff2') format('woff2'), url('./assets/fonts/bebasneuebook.woff') format('woff'), url('./assets/fonts/bebasneuebook.ttf') format('truetype');
      font-weight: 300;
      font-style: normal;
  }
  @font-face {
      font-family: 'Bebas Neue';
      src: local('Bebas Neue Regular'), local('BebasNeueRegular'), url('./assets/fonts/bebasneueregular.woff2') format('woff2'), url('./assets/fonts/bebasneueregular.woff') format('woff'), url('./assets/fonts/bebasneueregular.ttf') format('truetype');
      font-weight: 400;
      font-style: normal;
  }
  @font-face {
      font-family: 'Bebas Neue';
      src: local('Bebas Neue Bold'), local('BebasNeueBold'), url('./assets/fonts/bebasneuebold.woff2') format('woff2'), url('./assets/fonts/bebasneuebold.woff') format('woff'), url('./assets/fonts/bebasneuebold.ttf') format('truetype');
      font-weight: 700;
      font-style: normal;
  }

  .mobile-menu {
    overflow: auto;
    width:100%;
    height:100%;
    position: fixed;
    left: 0;
    right: 0;
    top: 0; 
    bottom: 0;
    font-family: 'Bebas Neue';
    font-weight: 400;
    font-size: 24px;
    text-align: center;
    background: white;
    display: none;
    z-index: 999;
  }

  .curators-body-col {
    display: block;
  }

  .contacts-wrap-first {
    display: contents;
  }

  .contacts-wrap {
    display: grid;
  }

  .menu-mobile-on {
    margin-top: 0 !important;
  }

  .main-container-mobile {
    height: 100vh;
    overflow: hidden;
  }

  .mobile-menu-element {
    padding: 10px;
  }

  .mobile-menu-open {
    align-items: center;
    justify-content: center;
    display: flex;
  }

  .element-del {
    display: none;
  }

  a {
    text-decoration: none;
    color: inherit;
  }

  .blue-href {
    color: rgb(40, 163, 205);
  }

  .head_background {
    margin: 0;
    position: absolute;
    z-index: -99999999;
  }

  .menu {
    font-family: 'Bebas Neue';
    font-weight: 400;
    font-size: 38px;
    max-width: 1000px;
    margin: auto;
    margin-top: 100px;
    text-transform: uppercase;
    align-items: center;
    display: flex;
    justify-content: space-between;
  }

  .menu-block-logo {
    display: inline-block;
    width: 266px;
  }

  .menu-block-logo-bki {
    width: auto;
    height: 108px;
    position: absolute;
    top: -33px;
    left: 30px;
  }

  .menu-hrefs {
    display: inline-block;
    margin-left: auto;
    font-family: 'Bebas Neue';
    font-weight: 400;
    font-size: 20px;
    display: block;
  }

  .menu-hrefs-element-margin {
    margin-left: 40px;
  }

  .poster {
    max-width: 1000px;
    margin: auto;
    margin-top: 40px;
  }

  .poster-image {
    width: 100%;
    height: auto;
    margin: auto;
  }

  .instagram-group {
    width: 400px;
    display: flex;
    flex-wrap: wrap;
  }

  .micro-blocks-wrap {
    margin-top: -100px;
    display: flex;
    flex-wrap: wrap;
    justify-content: inherit;
  }
  .simple-block {
    margin-bottom: 30px;
    padding: 5px;
    min-width: 300px;
  }
  .simple-block-title {
    font-family: 'Bebas Neue'; 
    font-weight: 400; 
    font-size: 28px;
  }
  .simple-block-string {
    font-family: 'Bebas Neue'; 
    font-weight: 400; 
    font-size: 23px;
  }
  .for-students-wrap {
    display: flex; 
    flex-wrap: wrap; 
    justify-content: inherit;
    width: 100%;
  }
  .footer {
    position: relative;
    width: 100%;
    height: 200px;
    background: rgb(15, 13, 13);
  }
  .footer-location {
    max-width: 1000px;
    margin: auto;
    color: white;
    font-family: 'Bebas Neue';
    font-weight: 400;
    font-size: 22px;
    padding-top: 40px;
    opacity: .85;
  }
  .footer-author {
    width: 100%; 
    color: #bbb; 
    text-align:center; 
    font-family: 'Bebas Neue'; 
    position: absolute; 
    bottom: 20px
  }

  .contacts-divider {
    height: 40px; 
    width: 100%;
    display: block;
  }

  .main-container {
    width: 100%;
    padding-left: 0px;
    padding-right: 0px;
    box-sizing: border-box;
    overflow-x: hidden;
  }

  .instagram-subgroup {
    display: block;
  }

  .curators-body {
    display: flex;
    justify-content: space-between;
    width: 100%;
    margin: auto;
  }

  .menu-button {
    display: none;
  }

  @media (max-width: 1000px) {
    .contacts-wrap-first {
      display: grid;
    }
    .main-container {
      padding-left: 10px;
      padding-right: 10px;
    }
    .menu {
      font-size: 32px;
    }
    .menu-block-logo-bki {
      width: auto;
      height: 80px;
      position: absolute;
      top: -23px;
      left: 15px;
    }
    .menu-hrefs-element-margin {
      margin-left: 25px;
    }
    .instagram-group {
      display: flex;
    }
    .contacts-divider {
      display: none;
    }
    .instagram-subgroup {
      display: contents;
    }
    .curators-body {
      display: flex;
      justify-content: space-between;
      width: 100%;
      margin: auto;
    }
    .footer-location {
      margin-left: 20px;
    }
  }

  @media (max-width: 810px) {
    .curators-body {
      justify-content: center;
      flex-wrap: wrap;
      margin-top: -60px;
    }
    .curators-body-col {
      display: contents;
    }
    .simple-block {
      text-align: center;
    }
    .menu {
      margin-top: 30px;
    }
    .menu-hrefs {
      display: none;
    }
    .menu-button {
      display: block;
    }
  }
</style>
