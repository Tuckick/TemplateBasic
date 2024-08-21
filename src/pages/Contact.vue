<template>
  <div class="page-wrapper">
    <div class="card">
      <div class="title">Contact Us</div>
      <v-form validate-on="submit lazy" @submit.prevent="submit">
        <v-container>
          <v-text-field
            v-model="firstname"
            :counter="10"
            :rules="nameRules"
            label="First name"
            hide-details
            required
            width="300px"
            class="mb-4"
          ></v-text-field>

          <v-text-field
            v-model="lastname"
            :counter="10"
            :rules="nameRules"
            label="Last name"
            hide-details
            required
            width="300px"
            class="mb-4"
          ></v-text-field>

          <v-text-field
            v-model="email"
            :rules="emailRules"
            label="E-mail"
            hide-details
            required
            width="300px"
            class="mb-4"
          ></v-text-field>

          <v-textarea
            v-model="detail"
            label="Detail"
            hide-details
            required
            width="300px"
            height="100px"
            class="mb-4"
          ></v-textarea>
        </v-container>
        <v-btn :loading="loading" class="mt-2" type="submit" block
          >Submit</v-btn
        >
      </v-form>
    </div>
    <v-dialog v-model="success" width="auto">
      <v-card
        max-width="400"
        text="Thank you for the valuable opportunity. We will get back to you as soon as possible."
        title="Success"
      >
        <template v-slot:actions>
          <v-btn class="ms-auto" text="Ok" @click="success = false"></v-btn>
        </template>
      </v-card>
    </v-dialog>
  </div>
</template>

<script setup>
import { ref } from "vue";
import emailjs from "@emailjs/browser";

defineOptions({
  name: "contact-page",
});

const loading = ref(false);
const success = ref(false);
const firstname = ref("");
const lastname = ref("");
const email = ref("");
const detail = ref("");

const nameRules = [
  (value) => {
    if (value) return true;
    return "Name is required.";
  },
];

const emailRules = [
  (value) => {
    if (value) return true;
    return "E-mail is required.";
  },
  (value) => {
    if (/.+@.+\..+/.test(value)) return true;
    return "E-mail must be valid.";
  },
];

const submit = async (event) => {
  loading.value = true;

  const results = await event;

  loading.value = false;

  console.log(results);
  if (results.valid) {
    sendEmail(results);
  } else {
    console.log("Invalid form");
  }
};

const sendEmail = () => {
  emailjs
    .send(
      "service_28rd7jj",
      "template_kd8c73i",
      {
        from_name: `${firstname.value} ${lastname.value}`,
        to_name: "Godzicodev",
        message: `Name: ${firstname.value} ${lastname.value}, Email: ${email.value}, Detail: ${detail.value}`,
      },
      "iwBSx_Ofe9K-zfFLl"
    )
    .then((response) => {
      console.log("SUCCESS!", response.status, response.text);
      success.value = true;
      firstname.value = null;
      lastname.value = null;
      email.value = null;
      detail.value = null;
    });
};
</script>

<style lang="scss" scoped>
.page-wrapper {
  margin: -20px;
  background: linear-gradient(to right, #bde0fe, #ddeefa, #fcfbf5);
  height: calc(100vh + 20px); /* Ensure it covers the full viewport height */
  display: flex;
  justify-content: center;
  align-items: center;

  .card {
    border: 2px solid #6caeed;
    border-radius: 16px;
    padding: 24px 16px;

    .title {
      color: #6caeed;
      font-size: 24px;
      font-weight: bold;
      text-align: center;
    }
  }
}
</style>
