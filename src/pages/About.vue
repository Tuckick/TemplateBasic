<template>
  <div class="page-wrapper">
    <div class="mission">
      <div class="content-section">
        <h3 class="title">Our Mission</h3>
        <div class="content">
          <strong class="main"
            >A partner is not just a business partner.</strong
          >
          <p class="desc">
            Our services Don't just a job. But you must be a partner in helping
            your customers achieve the success they want. all your travels We
            will help support you and take care of you until you reach your
            goals.
          </p>
        </div>
      </div>
      <div class="img-section">
        <img src="@/assets/mission.png" alt="mission" />
      </div>
    </div>
    <div class="story">
      <h3 class="title">Our Story</h3>
      <div class="story-detail">
        <div class="img-section">
          <img src="@/assets/story.jpg" alt="story" />
        </div>
        <div class="content-section">
          From study innovation creation, Got the opportunity to work as a
          programmer. It makes me even more fascinated with technology and
          inventions. Therefore, they want to use this knowledge and
          understanding to create their own business. So you can be sure that
          You don't hire people who only care about work. But you will work with
          people who are ready to learn. and bring the best to you
        </div>
      </div>
    </div>
    <div class="founder">
      <h3 class="title">Founder</h3>
      <div class="founder-detail">
        <div>
          <div class="founder-name">Nuttaya Pensrisirikul</div>
          <div class="founder-assay">
            "We will do our best. As worthy of being trusted by you"
          </div>
        </div>
        <img src="@/assets/founder.jpg" alt="founder" />
      </div>
    </div>
  </div>
</template>

<script setup>
defineOptions({
  name: "about-page",
});
</script>
<style lang="scss" scoped>
.page-wrapper {
  display: flex;
  flex-direction: column;
  gap: 16px;
  color: #6caeed;
  padding-bottom: 20px;
  .mission {
    display: flex;
    align-items: center;

    .content-section {
      flex: 1.2;
      margin-left: 58px;
      .title {
        margin: 16px auto;
        font-size: 28px;
      }
      .content {
        font-size: 14px;

        .main {
          font-size: 18px;
        }
        .desc {
          margin-top: 8px;
        }
      }
    }
    .img-section {
      flex: 1;
      img {
        width: 100%;
      }
    }
  }
  .story {
    display: flex;
    flex-direction: column;
    align-items: center;

    .title {
      font-size: 28px;
      margin: 16px auto;
    }
    .story-detail {
      display: flex;
      gap: 16px;
      .img-section {
        flex: 1;
        img {
          width: 100%;
        }
      }
      .content-section {
        flex: 1;
      }
    }
  }
  .founder {
    margin: 16px 58px;

    .title {
      font-size: 28px;
      margin: 16px auto;
      text-align: right;
    }
    .founder-detail {
      display: flex;
      justify-content: end;
      align-items: flex-end;
      gap: 8px;

      img {
        max-height: 300px;
        border-radius: 20px 0px;
        box-shadow: 1px 1px;
      }
      .founder-name {
        font-weight: bold;
        font-size: 18px;
        text-align: right;
      }
    }
  }

  @media screen and (max-width: 768px) {
    .mission {
      flex-direction: column;
      gap: 16px;
      .content-section {
        margin-left: 0;
      }
      .img-section {
        img {
          max-width: 500px;
        }
      }
    }
    .story {
      .story-detail {
        flex-direction: column;
        gap: 16px;
        align-items: center;
        .content-section {
          margin-left: 0;
        }
        .img-section {
          img {
            max-width: 500px;
          }
        }
      }
    }
  }
}
</style>