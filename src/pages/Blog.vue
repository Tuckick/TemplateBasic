<template>
  <div class="page-wrapper">
    <h3 class="mb-5">Share knowledge</h3>
    <div class="content-container">
      <div v-for="item in list" :key="item.id" class="card">
        <div class="inner-card">
          <div class="inner2-card">
            <div class="inner3-card">
              <div class="content">
                <div class="title">
                  <strong>
                    {{ item.title }}
                  </strong>
                </div>
                <div class="desc">
                  {{ item.desc }}
                </div>
              </div>
              <div class="more">
                <a :href="item.link" target="_blank">...Read more</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="mt-5">
      Support by
      <strong><a href="https://medium.com/" target="_blank">Medium</a></strong>
    </div>
  </div>
</template>

<script setup>
defineOptions({
  name: "blog-page",
});
import { ref } from "vue";

const list = ref([
  {
    id: "1",
    title: "How to Use ChatGPT in Daily Life?",
    desc: "AI has made a huge leap in the past few years and this is just the beginning! With tools like ChatGPT and Midjourney, many have seen the power of AI. AI tools are now at the center of our lives.",
    link: "https://medium.com/gitconnected/how-to-use-chatgpt-in-daily-life-4688f7afb930",
  },
  {
    id: "2",
    title: "7 Simple Tips to Improve Daily Focus",
    desc: "Some days, you’ll feel on top of the world, effortlessly sharp and clear. On others, focusing for even three minutes can feel like a challenge.",
    link: "https://medium.com/twosapp/7-simple-tips-to-improve-your-daily-focus-6300d93effc8",
  },
  {
    id: "3",
    title:
      "Just The First Page of This Book Is Enough To Question Your Entire Life",
    desc: "I am a big fan of slow and intentional living. Growing up as an underconfident child, hustling as an adult, and feeling completely drained by the time I finished college, I realized one thing pretty early in life — the cost of success, the glamorous promises of the other side are just an illusion. It’s all fake. It doesn’t exist.",
    link: "https://medium.com/books-are-our-superpower/just-the-first-page-of-this-book-is-enough-to-question-your-entire-life-f98068a2da1b",
  },
  {
    id: "4",
    title: "Why I Am Always So Calm; How & WHY You Should Too",
    desc: "Back when I was in college, I used to get angry so easily that it became my default nature. As if everything, every word, and every person could trigger me.",
    link: "https://medium.com/better-advice/why-i-am-always-so-calm-how-why-you-should-too-17725f5c2db4",
  },
  {
    id: "5",
    title: "10 Things To Do In The Evening Instead Of Watching Netflix",
    desc: "Anyone worried about spending slightly too many hours bingeing Netflix or watching TV, you're not alone.",
    link: "https://medium.com/better-advice/10-things-to-do-in-the-evening-instead-of-watching-netflix-4e270e9dd6b9",
  },
]);
</script>

<style lang="scss" scoped>
.page-wrapper {
  color: #89cff0;
  .content-container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 16px;
    .card {
      border: 3px solid;
      border-radius: 16px;
      padding: 2px;
      margin-bottom: 24px;
      background-color: #89cff0;
      height: 100%;
      .inner-card {
        border: 3px solid #bde0fe;
        border-radius: 16px;
        padding: 2px;
        background-color: #bde0fe;
        height: 100%;
        .inner2-card {
          border: 3px solid #ddeefa;
          border-radius: 16px;
          padding: 2px;
          height: 100%;
          background-color: #ddeefa;
          .inner3-card {
            border: 3px solid #fcfbf5;
            border-radius: 16px;
            padding: 16px;
            background-color: #fcfbf5;
            height: 100%;

            display: flex;
            flex-direction: column;
            justify-content: space-between;

            .title {
              font-size: 18px;
              margin-bottom: 8px;
            }
            .more {
              text-align: right;
              a {
                color: #89cff0;
                text-decoration: none;
                &:hover {
                  text-decoration: underline;
                }
              }
            }
          }
        }
      }
    }

    @media screen and (max-width: 1456px) {
      grid-template-columns: 1fr 1fr;
    }

    @media screen and (max-width: 690px) {
      grid-template-columns: 1fr;
    }
  }
  a {
    color: #89cff0;
    text-decoration: none;
    &:hover {
      text-decoration: underline;
    }
  }
}
</style>