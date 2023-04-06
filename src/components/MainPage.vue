<template>
  <v-container fluid class="app-container">
    <section class="promo">
      <div class="promo__text">
        <h1 class="promo__text-title">
          Photo of the <br />
          Day by <br />
          guangxi liu
        </h1>
        <p class="promo__text-description">
          The internet’s source of freely usable images.<br />
          Powered by creators everywhere.
        </p>
        <a href="#" class="promo__text-link">Explore All</a>
      </div>
      <v-img
        class="promo__hero-image"
        src="../../public/images/hero-image.png"
        alt="Photo"
      />
    </section>
    <section class="search" ref="search">
      <h2 class="visually-hidden">Search</h2>
      <v-text-field
        class="search__input"
        append-icon="mdi-magnify"
        label="Search for high-resolution photos"
      />
      <ul class="search__menu">
        <li v-for="(item, i) in searchMenu" :key="i">
          <button
            :class="'search__menu-btn ' + searchButtons[item]"
            @click="changeButtonState(item)"
          >
            {{ item }}
          </button>
        </li>
      </ul>
    </section>
    <section class="gallery">
      <h2 class="visually-hidden">Photo Gallery</h2>
      <article class="gallery__small-article">
        <v-img
          @click="openDialog('./images/hero-image.png')"
          src="../../public/images/hero-image.png"
          alt="Tom Öhlin photo"
        />
        <div class="gallery__small-article-content">
          <h3 class="gallery__small-article-title">Tom Öhlin</h3>
          <p class="gallery__small-article-subtitle">
            Indjinup Spa, WA, Australia (TAGS)
          </p>
          <p class="gallery__small-article-text">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam
          </p>
        </div>
        <ul class="gallery__small-article-actions">
          <li class="gallery__small-article-actions-item">
            <v-icon @click="changeColor(0, 0)">{{ icons[0][0] }}</v-icon>
          </li>
          <v-spacer />
          <li class="gallery__small-article-actions-item mr-7">
            <v-icon @click="changeColor(0, 1)">{{ icons[0][1] }}</v-icon
            >&nbsp;128
          </li>
          <li class="gallery__small-article-actions-item">
            <v-icon @click="changeColor(0, 2)">{{ icons[0][2] }}</v-icon
            >&nbsp;512
          </li>
        </ul>
      </article>

      <article class="gallery__small-article">
        <v-img
          @click="openDialog('./images/featured_meal.png')"
          src="../../public/images/featured_meal.png"
          alt="Featured meal photo"
        />
        <div class="gallery__small-article-content">
          <h3 class="gallery__small-article-title">Featured meal</h3>
          <p class="gallery__small-article-subtitle">
            Served with french fries + drink
          </p>
          <p class="gallery__small-article-text">
            Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper
            patty, Add Tender crisp patty and more.
          </p>
        </div>
        <ul class="gallery__small-article-actions">
          <li class="gallery__small-article-actions-item">
            <v-icon @click="changeColor(1, 0)">{{ icons[1][0] }}</v-icon>
          </li>
          <v-spacer />
          <li class="gallery__small-article-actions-item mr-7">
            <v-icon @click="changeColor(1, 1)">{{ icons[1][1] }}</v-icon
            >&nbsp;128
          </li>
          <li class="gallery__small-article-actions-item">
            <v-icon @click="changeColor(1, 2)">{{ icons[1][2] }}</v-icon
            >&nbsp;512
          </li>
        </ul>
      </article>
      <article class="gallery__big-article">
        <v-img
          @click="openDialog('./images/road.png')"
          class="gallery__big-article-photo"
          src="../../public/images/road.png"
          alt="Featured meal photo"
        />
        <div class="gallery__big-article-content-wrapper">
          <div class="gallery__big-article-content">
            <h3 class="gallery__big-article-title">Featured meal</h3>
            <p class="gallery__big-article-subtitle">
              Served with french fries + drink
            </p>
            <p class="gallery__big-article-text">
              Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add
              whopper patty, Add Tender crisp patty and more. Add Tender crisp
              patty and more.
            </p>
            <section
              @mousedown.left="onMouseDown"
              @mousemove="onMouseMove($event, $refs.carousel)"
              @mouseup="dragging = false"
            >
              <h2 class="visually-hidden">Additional photos</h2>
              <vue-horizontal
                class="gallery__big-article-carousel"
                ref="carousel"
                snap="none"
                :button="false"
                @scroll="onScroll"
              >
                <v-img
                  class="gallery__big-article-carousel-image"
                  v-for="i in 5"
                  :key="i"
                  src="../../public/images/hero-image.png"
                  alt="Photo"
                />
              </vue-horizontal>
            </section>

            <div class="gallery__big-article-buttons">
              <a class="gallery__big-article-order-link" href="#">Order Now</a>
              <button class="gallery__big-article-more-button">
                <v-icon>mdi-dots-horizontal</v-icon>
              </button>
            </div>
          </div>

          <ul class="gallery__big-article-actions">
            <li class="gallery__big-article-actions-item">
              <v-icon @click="changeColor(2, 0)">{{ icons[2][0] }}</v-icon>
            </li>
            <v-spacer />
            <li class="gallery__big-article-actions-item mr-7">
              <v-icon @click="changeColor(2, 1)">{{ icons[2][1] }}</v-icon
              >&nbsp;128
            </li>
            <li class="gallery__big-article-actions-item">
              <v-icon @click="changeColor(2, 2)">{{ icons[2][2] }}</v-icon
              >&nbsp;512
            </li>
          </ul>
        </div>
      </article>
      <article class="gallery__big-article">
        <v-img
          @click="openDialog('./images/road.png')"
          class="gallery__big-article-photo"
          src="../../public/images/road.png"
          alt="Featured meal photo"
        />
        <div class="gallery__big-article-content-wrapper">
          <div class="gallery__big-article-content">
            <h3 class="gallery__big-article-title">Featured meal</h3>
            <p class="gallery__big-article-subtitle">
              Served with french fries + drink
            </p>
            <p class="gallery__big-article-text">
              Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add
              whopper patty, Add Tender crisp patty and more. Add Tender crisp
              patty and more.
            </p>
            <section
              @mousedown.left="onMouseDown"
              @mousemove="onMouseMove($event, $refs.carousel2)"
              @mouseup="dragging = false"
            >
              <h2 class="visually-hidden">Additional photos</h2>
              <vue-horizontal
                class="gallery__big-article-carousel"
                ref="carousel2"
                snap="none"
                :button="false"
                @scroll="onScroll"
              >
                <v-img
                  class="gallery__big-article-carousel-image"
                  v-for="i in 5"
                  :key="i"
                  src="../../public/images/featured_meal.png"
                  alt="Photo"
                />
              </vue-horizontal>
            </section>

            <div class="gallery__big-article-buttons">
              <a class="gallery__big-article-order-link" href="#">Order Now</a>
              <button class="gallery__big-article-more-button">
                <v-icon>mdi-dots-horizontal</v-icon>
              </button>
            </div>
          </div>

          <ul class="gallery__big-article-actions">
            <li class="gallery__big-article-actions-item">
              <v-icon @click="changeColor(3, 0)">{{ icons[3][0] }}</v-icon>
            </li>
            <v-spacer />
            <li class="gallery__big-article-actions-item mr-7">
              <v-icon @click="changeColor(3, 1)">{{ icons[3][1] }}</v-icon
              >&nbsp;128
            </li>
            <li class="gallery__big-article-actions-item">
              <v-icon @click="changeColor(3, 2)">{{ icons[3][2] }}</v-icon
              >&nbsp;512
            </li>
          </ul>
        </div>
      </article>
      <article
        v-for="(photo, i) in photos"
        :key="i"
        class="gallery__small-article"
      >
        <v-img
          @click="openDialog(photo.src)"
          :src="photo.src"
          :alt="photo.alt"
        />
        <div class="gallery__small-article-content">
          <h3 class="gallery__small-article-title">Featured meal</h3>
          <p class="gallery__small-article-subtitle">
            Served with french fries + drink
          </p>
          <p class="gallery__small-article-text">
            Choice of: Coke, Fanta, Sprite, Upgrade to large fries, Add whopper
            patty, Add Tender crisp patty and more.
          </p>
        </div>
        <ul class="gallery__small-article-actions">
          <li class="gallery__small-article-actions-item">
            <v-icon @click="changeColor(i + 4, 0)">{{
              icons[i + 4][0]
            }}</v-icon>
          </li>
          <v-spacer />
          <li class="gallery__small-article-actions-item mr-7">
            <v-icon @click="changeColor(i + 4, 1)">{{ icons[i + 4][1] }}</v-icon
            >&nbsp;128
          </li>
          <li class="gallery__small-article-actions-item">
            <v-icon @click="changeColor(i + 4, 2)">{{ icons[i + 4][2] }}</v-icon
            >&nbsp;512
          </li>
        </ul>
      </article>
    </section>

    <v-dialog v-model="dialog" content-class="detail-dialog">
      <v-card>
        <header>
          <v-icon class="detail-dialog__close-icon" @click="closeDialog"
            >mdi-close</v-icon
          >
        </header>
        <v-img
          :src="dialogImage"
          alt="Photo"
          class="detail-dialog__main-photo"
        />
        <section class="detail-dialog__author-info">
          <h2 class="visually-hidden">Author info</h2>
          <v-img
            src="../../public/images/author-photo.png"
            alt="Author photo"
            class="detail-dialog__author-photo"
          />
          <span class="detail-dialog__author-account-info">
            <h3 class="detail-dialog__author-name">
              Stephanie<br />
              Hau
            </h3>
            <p class="detail-dialog__author-nickname">@stephiime</p>
          </span>
        </section>
        <section class="detail-dialog__gallery">
          <h2 class="visually-hidden">Gallery</h2>
          <v-img
            v-for="(photo, i) in dialogPhotos"
            :key="i"
            :src="photo.src"
            :alt="photo.alt"
            :class="photo.class"
          />
        </section>
        <footer>
          <v-icon class="detail-dialog__more-icon">mdi-dots-horizontal</v-icon>
        </footer>
      </v-card>
    </v-dialog>
  </v-container>
</template>

<script>
import VueHorizontal from "vue-horizontal";

export default {
  name: "MainPage",
  components: { VueHorizontal },
  data() {
    return {
      left: 0,
      originX: 0,
      originLeft: 0,
      dragging: false,
      dialog: false,
      dialogImage: "",
      photos: [
        { src: "./images/featured_meal.png", alt: "Featured meal photo" },
        { src: "./images/hero-image.png", alt: "Featured meal photo" },
        { src: "./images/featured_meal.png", alt: "Featured meal photo" },
        { src: "./images/hero-image.png", alt: "Featured meal photo" },
        { src: "./images/featured_meal.png", alt: "Featured meal photo" },
        { src: "./images/hero-image.png", alt: "Featured meal photo" },
      ],
      dialogPhotos: [
        {
          src: "./images/boat.png",
          alt: "Boat",
          class: "detail-dialog__gallery-image-big",
        },
        {
          src: "./images/ocean.png",
          alt: "Ocean",
          class: "detail-dialog__gallery-image",
        },
        {
          src: "./images/beach.png",
          alt: "Beach",
          class: "detail-dialog__gallery-image",
        },
        {
          src: "./images/boat.png",
          alt: "Boat",
          class: "detail-dialog__gallery-image-big",
        },
        {
          src: "./images/ocean.png",
          alt: "Ocean",
          class: "detail-dialog__gallery-image",
        },
        {
          src: "./images/beach.png",
          alt: "Beach",
          class: "detail-dialog__gallery-image",
        },
        {
          src: "./images/boat.png",
          alt: "Boat",
          class: "detail-dialog__gallery-image-big",
        },
        {
          src: "./images/ocean.png",
          alt: "Ocean",
          class: "detail-dialog__gallery-image",
        },
        {
          src: "./images/beach.png",
          alt: "Beach",
          class: "detail-dialog__gallery-image",
        },
        {
          src: "./images/boat.png",
          alt: "Boat",
          class: "detail-dialog__gallery-image-big",
        },
        {
          src: "./images/ocean.png",
          alt: "Ocean",
          class: "detail-dialog__gallery-image",
        },
        {
          src: "./images/beach.png",
          alt: "Beach",
          class: "detail-dialog__gallery-image",
        },
      ],
      searchMenu: [
        "Trending",
        "Nature",
        "Travel",
        "Animals",
        "Food",
        "Health",
        "Technology",
        "Events",
      ],
      searchButtons: {
        Trending: "",
        Nature: "",
        Travel: "",
        Animals: "",
        Food: "",
        Health: "",
        Technology: "",
        Events: "",
      },
      icons: [
        ["mdi-bookmark-outline", "mdi-heart-outline", "mdi-comment-outline"],
        ["mdi-bookmark-outline", "mdi-heart-outline", "mdi-comment-outline"],
        ["mdi-bookmark-outline", "mdi-heart-outline", "mdi-comment-outline"],
        ["mdi-bookmark-outline", "mdi-heart-outline", "mdi-comment-outline"],
        ["mdi-bookmark-outline", "mdi-heart-outline", "mdi-comment-outline"],
        ["mdi-bookmark-outline", "mdi-heart-outline", "mdi-comment-outline"],
        ["mdi-bookmark-outline", "mdi-heart-outline", "mdi-comment-outline"],
        ["mdi-bookmark-outline", "mdi-heart-outline", "mdi-comment-outline"],
        ["mdi-bookmark-outline", "mdi-heart-outline", "mdi-comment-outline"],
        ["mdi-bookmark-outline", "mdi-heart-outline", "mdi-comment-outline"],
      ],
    };
  },
  methods: {
    onScroll({ left }) {
      this.left = left;
    },
    onMouseDown(event) {
      this.dragging = true;
      this.originX = event.pageX;
      this.originLeft = this.left;
    },
    onMouseMove(event, element) {
      if (this.dragging) {
        const offset = event.pageX - this.originX;
        const left = this.originLeft - offset;
        element.scrollToLeft(left, "auto");
      }
    },
    openDialog(photo) {
      this.dialogImage = photo;
      this.dialog = true;
    },
    closeDialog() {
      this.dialog = false;
      this.dialogImage = "";
    },
    goToSearchBlock() {
      let element = this.$refs["search"];
      let top = element.offsetTop;
      window.scrollTo(0, top);
    },
    changeButtonState(item) {
      if (this.searchButtons[item] === "selected") {
        this.searchButtons[item] = "";
      } else {
        this.searchButtons[item] = "selected";
      }
    },
    changeColor(elemIndex, iconIndex) {
      if (this.icons[elemIndex][iconIndex].includes("-outline")) {
        this.$set(
          this.icons[elemIndex],
          iconIndex,
          this.icons[elemIndex][iconIndex].replace("-outline", "")
        );
      } else {
        this.$set(
          this.icons[elemIndex],
          iconIndex,
          this.icons[elemIndex][iconIndex] + "-outline"
        );
      }
    },
  },
  props: {
    goToSearch: Boolean,
  },
  watch: {
    goToSearch(newVal) {
      if (newVal) {
        this.goToSearchBlock();
        this.$emit("clearProps");
      }
    },
  },
};
</script>

<style></style>
