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
            <img
              class="mfp-iframe"
              :src="`/img/quadri/4.jpg`"
              frameborder="0"
              allowfullscreen=""
            />
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
  name: "VideoPopup",
  props: {
    close: { type: Function },
    videoId: { type: String },
  },
};
</script>
