<template>
  <div class="container">
    <header class="header">
      <img
        src="/menu_24dp_E8EAED_FILL0_wght400_GRAD0_opsz24.svg"
        alt="Иконка меню"
        class="icon"
        @click="toggleMenu"
      />
      <ul v-if="showMenu" class="dropdown-menu">
        <li @click="handleMenuClick('Элемент 1')">тра</li>
      </ul>
      <ul v-if="showMenu" class="dropdown-menu">
        <li @click="handleMenuClick('Элемент 2')">ля</li>
      </ul>
      <ul v-if="showMenu" class="dropdown-menu">
        <li @click="handleMenuClick('Элемент 3')">ля</li>
      </ul>

      <img
        class="logo"
        :class="{ hidden: showMenu || showInput }"
        src="/logonews.png"
      />
      <img
        src="/search_24dp_E8EAED_FILL0_wght400_GRAD0_opsz24.svg"
        @click="
          showInput = true;
          showMenu = false;
        "
        alt="Иконка поиска"
        class="icon"
      />
      <input
        class="input_search"
        type="text"
        v-if="showInput"
        v-model="inputValue"
        @blur="showInput = false"
        placeholder="кто ищет тот найдет, но не здеся..("
      />
    </header>
    <hr />
    <div class="main">
      <h3 class="section-title">Latest news</h3>
      <div class="news-item">
        <h4 class="news-title">Sample News Title</h4>
        <p class="news-description">
          This is a short description of the news content to show layout
          styling.
        </p>
      </div>
      <div class="news-item">
        <h4 class="news-title">Another News Title</h4>
        <p class="news-description">
          Another piece of news content goes here to fill up the main section.
        </p>
      </div>
      <div class="news-item">
        <h4 class="news-title">Another News Title</h4>
        <p class="news-description">
          Another piece of news content goes here to fill up the main section.
        </p>
      </div>
    </div>
    <footer class="footer">
      <div class="footer-content">
        <p>© 2024 AndyNewsCorporation Все права защищены.</p>
        <nav class="footer-links">
          <div class="contacts">
            <p>If you have wishes and recommendations - write to us</p>
            <a class="insta_img" href="https://www.instagram.com/andybaltenko/"
              ><img src="icons8-instagram.svg" alt=""
            /></a>
            <a class="telega_img" href="https://t.me/andybaltenko"
              ><img src="icons8-telegram.svg" alt=""
            /></a>
          </div>
        </nav>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showInput: false,
      showMenu: false,
      inputValue: "",
    };
  },

  methods: {
    toggleMenu() {
      // Переключаем видимость меню и скрываем поле ввода
      this.showMenu = !this.showMenu;
      this.showInput = false;
    },
    handleMenuClick(item) {
      // Обработка клика по элементу меню
      console.log(`Выбрано: ${item}`);
      this.showMenu = false; // Скрыть меню после выбора
    },
  },
};
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-bottom: 10px;
  position: relative;
}

hr {
  display: block;
  width: 100%;
  height: 2px;
  background-color: #fff8ca;
  border: none;
  animation: borderExpand 0.8s ease-out forwards;
}

.logo {
  width: 70px;
  height: auto;
}

.icon {
  width: 24px;
  height: 24px;
  cursor: pointer;
  filter: invert(80%);
  margin-left: 3px;
  margin-right: 5px;
}

.main {
  margin-top: 20px;
}

.section-title {
  font-size: 1.3em;
  color: #d9d9d9;
  margin-bottom: 15px;
}

.news-item {
  background-color: #3d3d3d;
  padding: 15px;
  border-radius: 8px;
  margin-bottom: 15px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}

.news-title {
  font-size: 1em;
  color: #eaeaea;
  margin-bottom: 5px;
}

.news-description {
  font-size: 0.9em;
  color: #bfbfbf;
  line-height: 1.4;
}

.input_search {
  width: calc(100% - 20px); /* Adjust width to fit within container padding */
  padding: 10px;
  font-size: 16px;
  color: #e0e0e0; /* Lighter text color for better contrast */
  background-color: #3d3d3d; /* Match background with news-item sections */
  border: 1px solid #555; /* Subtle border color */
  border-radius: 4px;
  outline: none;
  transition: border-color 0.3s ease, background-color 0.3s ease;
}

.dropdown-menu {
  display: flex;

  align-items: flex-start;
  list-style: none;

  background-color: #2c2c2c;
  border: 1px solid #3d3d3d;

  border-radius: 10px;
}

.dropdown-menu li {
  padding: 10px 15px;
  font-size: 14px;
  color: #e0e0e0;
  cursor: pointer;
  text-align: left;
  width: 100%;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

.dropdown-menu li:hover {
  background-color: #444444;
}

.hidden {
  display: none;
}

.footer {
  background-color: #2c2c2c;
  color: #e0e0e0;
  padding: 20px;
  border-top: 1px solid #3d3d3d;
  text-align: center;
  margin-top: 20px;
  border-radius: 0 0 10px 10px;
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
}

.footer p {
  font-size: 0.9em;
  margin-bottom: 10px;
  color: #bfbfbf;
}

.footer-links {
  display: flex;
  justify-content: center;
  gap: 15px;
}

.footer-links a {
  color: #fff8ca;
  text-decoration: none;
  font-size: 0.9em;
  transition: color 0.3s ease;
}

.footer-links a:hover {
  color: #e0e0e0;
}

.footer-links img {
  height: 100%;
  width: 100%;
}

.contacts {
  display: flex;
  align-items: center;
  margin-top: 10px;
}

.insta_img {
  width: 30px;
  height: auto;
  margin: 10px;
}
.telega_img {
  width: 30px;
  height: auto;
}
</style>
