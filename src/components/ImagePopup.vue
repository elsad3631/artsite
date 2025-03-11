<template>
    <div>
      <div
        class="mfp-bg mfp-fade mfp-ready"
        style="overflow: hidden"
        @click="close"
      ></div>
      <div class="mfp-wrap mfp-close-btn-in mfp-auto-cursor mfp-fade mfp-ready">
        <div class="mfp-container mfp-iframe-holder">
          <div class="mfp-content">
            <div class="mfp-iframe-scaler">
              <button
                title="Close (Esc)"
                @click="close"
                type="button"
                class="mfp-close"
              >
                ×</button
              >
              <div class="image">
                  <img :src="imageUrl" alt="" />
                  <div class="main image_" :data-img-url="imageUrl"></div>
                </div>
              <!-- <img class="image image_" src="/img/quadri/4.jpg" alt="" /> -->
              <!-- <img src="/quadri/4.jpg" /> -->
              <!-- <iframe
                class="mfp-iframe"
                :src="`//www.youtube.com/embed/${videoId}?autoplay=1`"
                frameborder="0"
                allowfullscreen=""
              ></iframe> -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "ImagePopup",
    props: {
      close: { type: Function },
      imageUrl: { type: String },
    },
  };
  </script>
  