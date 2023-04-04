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
      <img
        class="promo__hero-image"
        src="../../public/images/hero-image.png"
        alt="Photo"
      />
    </section>
    <section class="search">
      <h2 class="visually-hidden">Search</h2>
      <v-text-field
        class="search__input"
        append-icon="mdi-magnify"
        label="Search for high-resolution photos"
      />
      <ul class="search__menu">
        <li>
          <button class="search__menu-btn">Trending</button>
        </li>
        <li>
          <button class="search__menu-btn">Nature</button>
        </li>
        <li>
          <button class="search__menu-btn">Travel</button>
        </li>
        <li>
          <button class="search__menu-btn">Animals</button>
        </li>
        <li>
          <button class="search__menu-btn">Food</button>
        </li>
        <li>
          <button class="search__menu-btn">Health</button>
        </li>
        <li>
          <button class="search__menu-btn">Technology</button>
        </li>
        <li>
          <button class="search__menu-btn">Events</button>
        </li>
      </ul>
    </section>
    <section class="gallery">
      <h2 class="visually-hidden">Photo Gallery</h2>
      <article class="gallery__small-article">
        <img src="../../public/images/hero-image.png" alt="Tom Öhlin photo" />
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
            <v-icon>mdi-bookmark-outline</v-icon>
          </li>
          <v-spacer />
          <li class="gallery__small-article-actions-item mr-7">
            <v-icon>mdi-heart-outline</v-icon>&nbsp;128
          </li>
          <li class="gallery__small-article-actions-item">
            <v-icon>mdi-comment-outline</v-icon>&nbsp;512
          </li>
        </ul>
      </article>

      <article class="gallery__small-article">
        <img
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
            <v-icon>mdi-bookmark-outline</v-icon>
          </li>
          <v-spacer />
          <li class="gallery__small-article-actions-item mr-7">
            <v-icon>mdi-heart-outline</v-icon>&nbsp;128
          </li>
          <li class="gallery__small-article-actions-item">
            <v-icon>mdi-comment-outline</v-icon>&nbsp;512
          </li>
        </ul>
      </article>
      <article class="gallery__big-article">
        <img
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
              <v-icon>mdi-bookmark-outline</v-icon>
            </li>
            <v-spacer />
            <li class="gallery__big-article-actions-item mr-7">
              <v-icon>mdi-heart-outline</v-icon>&nbsp;128
            </li>
            <li class="gallery__big-article-actions-item">
              <v-icon>mdi-comment-outline</v-icon>&nbsp;512
            </li>
          </ul>
        </div>
      </article>
      <article class="gallery__big-article">
        <img
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
              <v-icon>mdi-bookmark-outline</v-icon>
            </li>
            <v-spacer />
            <li class="gallery__big-article-actions-item mr-7">
              <v-icon>mdi-heart-outline</v-icon>&nbsp;128
            </li>
            <li class="gallery__big-article-actions-item">
              <v-icon>mdi-comment-outline</v-icon>&nbsp;512
            </li>
          </ul>
        </div>
      </article>
      <article class="gallery__small-article">
        <img
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
            <v-icon>mdi-bookmark-outline</v-icon>
          </li>
          <v-spacer />
          <li class="gallery__small-article-actions-item mr-7">
            <v-icon>mdi-heart-outline</v-icon>&nbsp;128
          </li>
          <li class="gallery__small-article-actions-item">
            <v-icon>mdi-comment-outline</v-icon>&nbsp;512
          </li>
        </ul>
      </article>
      <article class="gallery__small-article">
        <img
          src="../../public/images/hero-image.png"
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
            <v-icon>mdi-bookmark-outline</v-icon>
          </li>
          <v-spacer />
          <li class="gallery__small-article-actions-item mr-7">
            <v-icon>mdi-heart-outline</v-icon>&nbsp;128
          </li>
          <li class="gallery__small-article-actions-item">
            <v-icon>mdi-comment-outline</v-icon>&nbsp;512
          </li>
        </ul>
      </article>
      <article class="gallery__small-article">
        <img
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
            <v-icon>mdi-bookmark-outline</v-icon>
          </li>
          <v-spacer />
          <li class="gallery__small-article-actions-item mr-7">
            <v-icon>mdi-heart-outline</v-icon>&nbsp;128
          </li>
          <li class="gallery__small-article-actions-item">
            <v-icon>mdi-comment-outline</v-icon>&nbsp;512
          </li>
        </ul>
      </article>
      <article class="gallery__small-article">
        <img
          src="../../public/images/hero-image.png"
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
            <v-icon>mdi-bookmark-outline</v-icon>
          </li>
          <v-spacer />
          <li class="gallery__small-article-actions-item mr-7">
            <v-icon>mdi-heart-outline</v-icon>&nbsp;128
          </li>
          <li class="gallery__small-article-actions-item">
            <v-icon>mdi-comment-outline</v-icon>&nbsp;512
          </li>
        </ul>
      </article>
      <article class="gallery__small-article">
        <img
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
            <v-icon>mdi-bookmark-outline</v-icon>
          </li>
          <v-spacer />
          <li class="gallery__small-article-actions-item mr-7">
            <v-icon>mdi-heart-outline</v-icon>&nbsp;128
          </li>
          <li class="gallery__small-article-actions-item">
            <v-icon>mdi-comment-outline</v-icon>&nbsp;512
          </li>
        </ul>
      </article>
      <article class="gallery__small-article">
        <img
          src="../../public/images/hero-image.png"
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
            <v-icon>mdi-bookmark-outline</v-icon>
          </li>
          <v-spacer />
          <li class="gallery__small-article-actions-item mr-7">
            <v-icon>mdi-heart-outline</v-icon>&nbsp;128
          </li>
          <li class="gallery__small-article-actions-item">
            <v-icon>mdi-comment-outline</v-icon>&nbsp;512
          </li>
        </ul>
      </article>
    </section>
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
  },
};
</script>

<style></style>
