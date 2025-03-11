<template>
  <div class="kura_tm_section" id="portfolio">
    <div class="kura_tm_news">
      <div class="container">
        <div class="kura_tm_main_title">
          <span>Portfolio</span>
          <h3>Selected Works</h3>
        </div>
        <div
          class="news_list wow fadeInUp"
          data-wow-duration=".7s"
        >
          <swiper :options="swiperOptions" ref="mySwiper">
            <swiper-slide
              v-for="image in images"
              :key="image.src"
              class="swiper-slide"
            >
            <div class="list_inner">
                <div class="image">
                  <img src="img/portfolio/410-460.jpg" alt="" />
                  <div class="main image_" :data-img-url="image.src"></div>
                </div>
                <div class="overlay"></div>
                <img class="svg" src="img/svg/right-arrow.svg" alt="" />
                <div class="details">
                  <span class="date">September 02, 2021</span>
                  <h3 class="span">VS Code Gets New JavaScript Debugger</h3>
                </div>
                <a class="kura_tm_full_link_ kura_tm_full_link" href="#"></a>
                <div class="news_hidden_details">
                  <div class="news_popup_informations">
                    <div class="description">
                      <p>
                        Kura is a leading web design agency with an
                        award-winning design team that creates innovative,
                        effective websites that capture your brand, improve your
                        conversion rates, and maximize your revenue to help grow
                        your business and achieve your goals.
                      </p>
                      <p>
                        In today’s digital world, your website is the first
                        interaction consumers have with your business. That's
                        why almost 95 percent of a user’s first impression
                        relates to web design. It’s also why web design services
                        can have an immense impact on your company’s bottom
                        line.
                      </p>
                      <p>
                        That’s why more companies are not only reevaluating
                        their website’s design but also partnering with Kura,
                        the web design agency that’s driven more than $2.4
                        billion in revenue for its clients. With over 50 web
                        design awards under our belt, we're confident we can
                        design a custom website that drives sales for your
                        unique business.
                      </p>
                    </div>
                  </div>
                </div>
              </div>
              <!-- <div class="list_inner">
                <div class="image">
                  <img src="/img/portfolio/410-460.jpg" alt="" />
                  <div class="main" :data-img-url="'' + image.src" />
                  <div class="overlay"></div>
                  <img class="svg" src="/img/svg/right-arrow.svg" alt="" />
                  <div class="details">
                    <h3>{{ image.title }}</h3>
                    <span>{{ image.sub }}</span>
                  </div>
                </div>
                <a
                  class="kura_tm_full_link popup-vimeo"
                  @click="onClick(image.src)"
                ></a>
              </div> -->
            </swiper-slide>
          </swiper>
          <div class="kura_tm_swiper_progress fill" slot="navigation">
            <div class="my_pagination_in">
              <span class="current"></span>
              <!-- <span class="pagination_progress"
                ><span class="all"><span></span></span
              ></span> -->
              <span class="total"></span>
            </div>
            <div class="my_navigation">
              <ul>
                <li>
                  <a class="my_prev" href="#"
                    ><img class="svg" src="/img/svg/right-arrow.svg" alt=""
                  /></a>
                </li>
                <li>
                  <a class="my_next" href="#"
                    ><img class="svg" src="/img/svg/right-arrow.svg" alt=""
                  /></a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
    <ImagePopup v-if="modal" :close="closeModal" :videoId="videoId" />
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import ImagePopup from "./ImagePopup.vue";
// import Modal from "./Modal.vue";
export default {
  name: "Portfolio",
  components: {
    Swiper,
    SwiperSlide,
    ImagePopup,
  },
  data() {
    return {
      swiperOptions: {
        slidesPerView: 3,
        spaceBetween: 30,
        loop: true,
        pagination: false,
        navigation: {
          prevEl: ".my_prev",
          nextEl: ".my_next",
        },
        breakpoints: {
          320: {
            slidesPerView: 1,
            spaceBetween: 20,
          },
          640: {
            slidesPerView: 1,
            spaceBetween: 20,
          },
          768: {
            slidesPerView: 2,
            spaceBetween: 30,
          },
          1024: {
            slidesPerView: 3,
            spaceBetween: 40,
          },
        },
        // Some Swiper option/callback...
      },
      images: [
        {
          src: "/quadri/1.jpg",
          thumbnail: "/quadri/1.jpg",
          title: "Titolo opera 1",
          sub: "Secondo titolo / Descrizione",
          videoId: "kSJYu4njW8s",
        },
        {
          src: "/quadri/2.jpg",
          thumbnail: "/quadri/2.jpg",
          title: "Titolo opera 2",
          sub: "Secondo titolo / Descrizione",
          videoId: "7e90gBu4pas",
        },

        {
          src: "/quadri/3.jpg",
          thumbnail: "/quadri/3.jpg",
          title: "Titolo opera 3",
          sub: "Secondo titolo / Descrizione",
          videoId: "KklbdVboeB4",
        },
        {
          src: "/quadri/4.jpg",
          thumbnail: "/quadri/4.jpg",
          title: "Titolo opera 4",
          sub: "Secondo titolo / Descrizione",
          videoId: "7e90gBu4pas",
        },
        {
          src: "/quadri/5.jpg",
          thumbnail: "/quadri/5.jpg",
          title: "Titolo opera 5",
          sub: "Secondo titolo / Descrizione",
          videoId: "KklbdVboeB4",
        },
        {
          src: "/quadri/6.jpeg",
          thumbnail: "/quadri/6.jpeg",
          title: "Titolo opera 6",
          sub: "Secondo titolo / Descrizione",
          videoId: "kSJYu4njW8s",
        },
      ],
      modal: false,
      videoId: null,
    };
  },
  computed: {
    swiper() {
      return this.$refs.mySwiper.$swiper;
    },
  },
  mounted() {
    // console.log("Current Swiper instance object", this.swiper);
    this.swiper.slideTo(3, 1000, false);
  },
  methods: {
    closeModal() {
      this.modal = false;
    },
    onClick(videoId) {
      this.videoId = videoId;
      this.modal = true;
    },
  },
};
</script>
