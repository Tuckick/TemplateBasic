<template>
  <div class="page-wrapper">
    <div class="banner">
      <img src="@/assets/banner.png" alt="Banner" />
    </div>
    <div class="welcome-container">
      <div class="about-business">
        <h3>We are the leader in technology.</h3>
        <p>
          The world of technology never stops evolving. But we will catch up. So
          that you receive the highest quality and most modern products.
        </p>
        <div class="action">
          <div class="add-line" @click="sendLineMessage">Add Line</div>
          <div class="call-phone" @click="makeCall">
            <img src="@/assets/icons/call.svg" alt="call" />
            <span> +1234567890 </span>
          </div>
        </div>
      </div>
      <v-divider class="divider"></v-divider>
      <div class="expand-business">
        All our services Operated by a team of specialists with knowledge and
        abilities Therefore, you can be confident that the work pieces that we
        deliver to you must definitely be of high quality. Moreover, we will
        never abandon you. Always ready to take care and give advice after
        service. Just let us take care of you. We will do it sincerely and
        honestly like a best friend.
      </div>
    </div>
    <div class="strong-container">
      <div class="main-container">
        <div
          v-for="main in strongList"
          :key="main.id"
          class="main-card"
          :class="{ 'main-card-active': main.id == currentMainStrong }"
          @click="handleClickMainStrong(main.id)"
        >
          <div class="icon">
            <img
              v-if="main.id == 'website'"
              src="@/assets/icons/card/website.svg"
              alt="website"
            />
            <img
              v-if="main.id == 'iot'"
              src="@/assets/icons/card/iot.svg"
              alt="iot"
            />
            <img
              v-if="main.id == 'consultation'"
              src="@/assets/icons/card/consultation.svg"
              alt="consultation"
            />
          </div>
          <div class="title">{{ main.name }}</div>
        </div>
      </div>
      <div class="sub-container">
        <div v-for="(sub, i) in subStrong" :key="i" class="sub-card">
          <div class="title">{{ sub.title }}</div>
          <div class="desc">{{ sub.desc }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from "vue";

defineOptions({
  name: "home-page",
});

let intervalId;

const strongList = ref([
  {
    id: "website",
    name: "Website",
    items: [
      {
        title: "High quality",
        desc: "Spead and quality are the most important things that we focus on.",
      },
      { title: "UX/UI friendly", desc: "Simple and easy to use." },
      {
        title: "Modern",
        desc: "We always keep up with the latest technology and modern design",
      },
    ],
  },
  {
    id: "iot",
    name: "iot",
    items: [
      {
        title: "Posibility",
        desc: "Everything is possible in the reality with IOT.",
      },
      { title: "Professional", desc: "Choose the right equipment" },
      {
        title: "Reasonable price",
        desc: "The budget doesn't escalate.",
      },
    ],
  },
  {
    id: "consultation",
    name: "Consultation",
    items: [
      {
        title: "Sincere",
        desc: "Give advice to the best of your ability, without holding back. And take care until completed",
      },
      {
        title: "Free",
        desc: "Want to do it but don't have the knowledge. Come consult us. Free of charge",
      },
    ],
  },
]);

const currentMainStrong = ref(strongList.value[0].id);

const updateCurrentMainStrong = () => {
  const currentIndex = strongList.value.findIndex(
    (item) => item.id === currentMainStrong.value
  );
  const nextIndex = (currentIndex + 1) % strongList.value.length;
  currentMainStrong.value = strongList.value[nextIndex].id;
};

onMounted(() => {
  intervalId = setInterval(updateCurrentMainStrong, 5000);
});

onUnmounted(() => {
  clearInterval(intervalId);
});

const subStrong = computed(() => {
  var result = strongList.value.find(
    (item) => item.id == currentMainStrong.value
  );
  if (result) {
    return result.items;
  } else {
    return [];
  }
});

const handleClickMainStrong = (id) => {
  console.log(id);
  currentMainStrong.value = id;
};

const makeCall = () => {
  window.location.href = "tel:+1234567890";
};
const sendLineMessage = () => {
  window.location.href = "https://line.me/R/ti/p/%40yourlineid"; // Replace with your LINE ID
};
</script>
<style lang="scss" scoped>
.banner {
  margin: -20px;
  img {
    width: 100%;
    height: auto;
  }
}
.welcome-container {
  background-image: url("@/assets/icons/bg/bg_group.svg");
  background-size: contain;
  background-position-x: right;
  background-blend-mode: multiply;

  background-color: #6caeed;
  color: #fcfbf5;
  margin: 40px -20px;
  padding: 30px 100px;
  box-shadow: 0px 0px 19px 20px #6caeed;

  display: flex;
  justify-content: center;
  gap: 16px;

  .about-business,
  .expand-business {
    flex: 1;
    h3 {
      font-size: 28px;
      line-height: 1;
      margin-bottom: 8px;
    }
    p {
      color: #ddeefa;
    }

    .action {
      display: flex;
      gap: 16px;
      margin-top: 16px;
      align-items: center;

      .add-line {
        cursor: pointer;
        padding: 8px 24px;
        color: #fefefe;
        border-radius: 36px;
        background-color: #ede0fe;
        &:hover {
          opacity: 0.8;
        }
      }
      .call-phone {
        cursor: pointer;
        padding: 8px 16px;
        color: #ede0fe;
        border-radius: 8px;
        display: flex;
        gap: 4px;
        align-items: center;
      }
    }
  }
  .divider {
    display: none;
    @media screen and (max-width: 576px) {
      display: block;
    }
  }

  @media screen and (max-width: 768px) {
    padding: 20px;
  }
  @media screen and (max-width: 576px) {
    flex-direction: column;
  }
}

.strong-container {
  margin: 72px auto;
  display: flex;
  flex-direction: column;
  gap: 20px;

  .main-container {
    display: flex;
    gap: 8px;
    justify-content: center;
    .main-card {
      cursor: pointer;
      width: 110px;
      height: 100%;
      display: flex;
      align-items: center;
      flex-direction: column;
      gap: 4px;
      border: 1px solid;
      padding: 16px;
      border-radius: 6px;
      color: #6caeed;
      font-weight: 500;

      .icon {
        width: 40px;
        height: 40px;
        border-radius: 99%;
        border: 2px solid;
        display: flex;
        align-items: center;
        justify-content: center;
        img {
          width: 30px;
          height: 30px;
        }
      }
      &-active {
        background-color: #bde0fe;
      }
    }
  }
  .sub-container {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
    .sub-card {
      flex: 1;
      min-width: 220px;
      cursor: pointer;
      display: flex;
      align-items: flex-start;
      flex-direction: column;
      gap: 8px;
      border: 1px solid;
      padding: 16px;
      border-radius: 6px;
      color: #fcfbf5;
      background-color: #bde0fe;
      font-weight: 500;

      .title {
        font-size: 18px;
        font-weight: 700;
      }
    }
  }
}
</style>