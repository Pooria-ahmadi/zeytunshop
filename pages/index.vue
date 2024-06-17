<template>
  <div class="font-family">
    <div class="slideshow-container m-auto is-hidden-desktop">

      <div v-for="(slide, index) in slides" :key="index" class="mySlides" v-show="index === currentSlide">
        <img :src="slide.image" alt="زیتون شاپ" class="width-shadow-slider">
        <div class="Caption-text has-text-white has-text-weight-bold is-size-5 p-5 has-text-centered">{{ slide.caption }}
        </div>
      </div>
      <a class="next has-text-white has-text-weight-bold is-size-6" @click="prevSlide">&#10094;</a>
      <a class="prev has-text-white has-text-weight-bold is-size-6" @click="nextSlide">&#10095;</a>
    </div>

    <div class="has-text-centered mt-4 is-hidden-desktop">
      <span v-for="(dot, index) in slides" :key="index" class="dot" :class="{ 'active': index === currentSlide }"
        @click="changeSlide(index)"></span>
    </div>
    <img src="background-option.jpg" alt="" style="width: 100%;" class="is-hidden-mobile">
    <div class="option-position is-hidden-mobile">
      <div class="columns mx-6 mb-0 is-justify-content-center is-multiline">
        <div class="column is-3-desktop">
          <NuxtLink to="/Article">
            <div class="position-image-suggested">
              <div class="image-box">
                <img src="7.jpg" class="shadow">
              </div>
              <p class="title-on-picture-suggested has-text-weight-bold has-text-white has-text-centered">
                زیتون اصیل خارجی و خوش طعم لوراس
              </p>
            </div>
          </NuxtLink>
        </div>
        <div class="column is-5-desktop">
          <a href="#">
            <div class="position-image-suggested">
              <div class="image-box">
                <img src="1.jpg" class="shadow">
              </div>
              <p class="title-on-picture-suggested has-text-weight-bold has-text-white has-text-centered">
                روغن زیتون سرخ کردنی ایتالیا
              </p>
            </div>
          </a>
          <div class="columns mt-0">
            <div class="column">
              <a href="#">
                <div class="position-image-suggested">
                  <div class="image-box">
                    <img src="2.jpg" class="shadow">
                  </div>
                  <p class="title-on-picture-suggested has-text-weight-bold has-text-white has-text-centered">
                    زیتون اصیل خارجی
                    خوش طعم لوراس
                  </p>
                </div>
              </a>
            </div>
            <div class="column">
              <a href="#">
                <div class="position-image-suggested">
                  <div class="image-box">
                    <img src="10.jpg" class="shadow">
                  </div>
                  <p class="title-on-picture-suggested has-text-weight-bold has-text-white has-text-centered">
                    زیتون سیاه خوش
                    طعم لوراس و ...
                  </p>
                </div>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="columns mt-6 mx-4">
      <div class="column">
        <div class="menu-divisions pr-4">
          <p class="has-text-weight-bold ">
            پربازدید ترین ها
          </p>
        </div>
        <div class="columns is-centered mt-2">
          <div class="column is-three-quarters">
            <a href="#">
              <div class="position-image-suggested">
                <div class="image-box">
                  <img src="10.jpg" class="shadow">
                </div>
                <p class="title-on-picture-popular is-size-5 has-text-white has-text-weight-bold has-text-centered">
                  زیتون سبز اصیل ترکیه
                </p>
              </div>
            </a>
          </div>
        </div>
        <div class="columns is-centered">
          <div class="column is-three-quarters">
            <a href="#">
              <div class="position-image-suggested">
                <div class="image-box">
                  <img src="6.jpg" class="shadow">
                </div>
                <p class="title-on-picture-popular is-size-5 has-text-white has-text-weight-bold has-text-centered">
                  روغن زیتون ایتالیا
                </p>
              </div>
            </a>
          </div>
        </div>
        <div class="columns is-centered">
          <div class="column is-three-quarters">
            <a href="#">
              <div class="position-image-suggested">
                <div class="image-box">
                  <img src="2.jpg" class="shadow">
                </div>
                <p class="title-on-picture-popular is-size-5 has-text-white has-text-weight-bold has-text-centered">
                  زیتون شکسته لوراس
                </p>
              </div>
            </a>
          </div>
        </div>
        <div class="menu-divisions pr-4">
          <p class="has-text-weight-bold ">
            جدیدترین ها
          </p>
        </div>
        <div class="columns is-centered mt-2">
          <div class="column is-three-quarters">
            <a href="#">
              <div class="position-image-suggested">
                <div class="image-box">
                  <img src="1.jpg" class="shadow">
                </div>
                <p class="title-on-picture-popular is-size-5 has-text-white has-text-weight-bold has-text-centered">
                  زیتون شکسته ایکرام
                </p>
              </div>
            </a>
          </div>
        </div>
        <div class="columns is-centered mt-2">
          <div class="column is-three-quarters">
            <a href="#">
              <div class="position-image-suggested">
                <div class="image-box">
                  <img src="19.jpg" class="shadow">
                </div>
                <p class="title-on-picture-popular is-size-5 has-text-white has-text-weight-bold has-text-centered">
                  زیتون بی هسته ایکرام
                </p>
              </div>
            </a>
          </div>
        </div>
      </div>
      <div class="column has-background-light is-three-fifths">
        <div class="menu-divisions pr-4 mr-5 my-6">
          <p class="has-text-weight-bold is-size-5">
            آخرین مطلب
          </p>
        </div>
        <div class="columns is-centered is-mobile">
          <div class="column">
            <p class="has-text-weight-bold">
              بهترین روغن زیتون ایتالیا
            </p>
            <p class="line-height-description mt-5 is-hidden-mobile">
              روغن زیتون ایتالیکو محصول ایتالیا است که با بهترین روش تولید می شوند و...
            </p>
          </div>
          <div class="column has-text-centered">
            <img src="5.jpg" alt="">
          </div>
        </div>
        <hr class="has-background-grey-lighter">
        <div class="columns is-centered is-mobile">
          <div class="column">
            <p class="has-text-weight-bold">
              اصیل ترین سرکه ایتالیا
            </p>
            <p class="line-height-description mt-5 is-hidden-mobile">
              سرکه لوگلیو که یکی از بهترین سرکه های تولید شده توسط کشور ایتالیا است...
            </p>
          </div>
          <div class="column has-text-centered">
            <img src="17.jpg" alt="">
          </div>
        </div>
        <hr class="has-background-grey-lighter">
        <div class="columns is-centered is-mobile">
          <div class="column">
            <p class="has-text-weight-bold">
              زیتون های بدون هسته لوراس با طعم های مختلف
            </p>
            <p class="line-height-description mt-5 is-hidden-mobile">
              زیتون های دانه درشت با طعم های مختلف که توسط شرکت لوراس تولید می شوند...
            </p>
          </div>
          <div class="column has-text-centered">
            <img src="18.jpg" alt="">
          </div>
        </div>
        <hr class="has-background-grey-lighter">
        <div class="columns is-centered is-mobile">
          <div class="column">
            <p class="has-text-weight-bold">
              زیتون های کبابی لوراس بهترین زیتون های ترکیه
            </p>
            <p class="line-height-description mt-5 is-hidden-mobile">
              زیتون های کبابی لوراس یکی از بهترین زیتون کبابی ها اصیل کشور ترکیه محسوب می شود...
            </p>
          </div>
          <div class="column has-text-centered">
            <img src="13.jpg" alt="">
          </div>
        </div>
      </div>
    </div>

  </div>
</template>
<script>
export default {
  data() {
    return {
      currentSlide: 0,
      slides: [
        { image: '1.jpg', caption: 'زیتون شاپ مرجع زیتون های اصیل' },
        { image: '2.jpg', },
        { image: '3.jpg', },

      ],
      info: null,
    };
  },
  mounted() {
    this.showSlides();
  },

  methods: {
    showSlides() {
      setInterval(() => {
        this.currentSlide = (this.currentSlide + 1) % this.slides.length;
      }, 5000);
    },
    changeSlide(index) {
      this.currentSlide = index;
    },
    prevSlide() {
      this.currentSlide = (this.currentSlide - 1 + this.slides.length) % this.slides.length;
    },
    nextSlide() {
      this.currentSlide = (this.currentSlide + 1) % this.slides.length;
    }
  }
}
</script>
