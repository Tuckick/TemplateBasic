<template>
  <div class="page-wrapper">
    <div class="website">
      <div class="title">
        <h2>Website</h2>
      </div>
      <div class="framework">
        <div class="expand">
          <h3>Official Website</h3>
          <div class="desc ml-2">
            We use highest technology for best quality,
          </div>
          <div class="desc ml-2">
            Customer can chose our template, also can custom by your needed.
          </div>
        </div>
        <div class="list ml-2 mt-2">
          <img src="@/assets/icons/brand/node.png" alt="node" height="50px" />
          <img src="@/assets/icons/brand/vue.png" alt="vue" height="50px" />
          <img
            src="@/assets/icons/brand/tailwind.png"
            alt="tailwind"
            height="50px"
          />
        </div>
      </div>
      <div class="framework mt-6">
        <div class="expand">
          <h3>Information Website</h3>
          <div class="desc ml-2">Easy to control and deploy.</div>
        </div>
        <div class="list ml-2 mt-2">
          <img
            src="@/assets/icons/brand/wordpress.png"
            alt="wordpress"
            height="50px"
          />
          <img
            src="@/assets/icons/brand/google_sites.png"
            alt="google_sites"
            height="50px"
          />
        </div>
      </div>
    </div>
    <div class="iot mb-10">
      <div class="title">
        <h2>IOT</h2>
      </div>
      <div class="framework">
        <div class="expand">
          <h3>Arduino, ESP8266, ESP32, Raspberry Pi</h3>
          <div class="desc ml-2">
            Create and Design IOT Project for your needed.
          </div>
          <div class="desc ml-2">
            <strong>Hardware</strong><span> - Electrical circuit</span>
          </div>
          <div class="desc ml-2">
            <strong>Software</strong><span> - Code control</span>
          </div>
        </div>
        <div class="list ml-2 mt-2">
          <img
            src="@/assets/icons/brand/arduino.png"
            alt="arduino"
            height="50px"
          />
          <img src="@/assets/icons/brand/esp.png" alt="esp" height="50px" />
          <img
            src="@/assets/icons/brand/raspberry_pi.png"
            alt="raspberry_pi"
            height="50px"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineOptions({
  name: "service-page",
});
</script>

<style lang="scss" scoped>
.page-wrapper {
  background-color: #fcfbf5;
  background: linear-gradient(to right, #fcfbf5, #ddeefa, #bde0fe);
  margin: 72px 0px 0px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  .website {
    background-image: url("@/assets/icons/card/devices.svg");
    background-color: #6caeed;
    color: #fcfbf5;
  }
  .iot {
    background-image: url("@/assets/icons/card/home_iot_device.svg");
    background-color: #80cff0;
    color: #ddeefa;
  }

  .website,
  .iot {
    min-height: 400px;
    margin: 40px 20px 0px;
    padding: 16px;
    border-radius: 16px;
    background-position: right;
    background-size: contain;
    background-blend-mode: soft-light;

    .title {
      margin-bottom: 8px;
    }
    .framework {
      display: flex;
      gap: 8px;
      flex-direction: column;

      .list {
        display: flex;
        gap: 16px;
        align-items: center;
        flex-wrap: wrap;
      }
    }
  }
}
</style>