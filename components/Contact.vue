<template>
  <section class="contact">
    <div class="contact-back-filter"></div>
    <div class="contact-grid">
      <div class="contact-grid-content">
        <h3 class="contact-content-title">Get in touch.</h3>
        <p>Questions? Want a quote? Just want to say, "What's Up?" Use the contact form and we will get back to you the same day.</p>
        <p>
          Or email us directly at
          <a href="#">hello@told.design</a>.
        </p>
        <button
          href="mailto:hello@told.design"
          class="theme-inline-button theme-inline-button-primary contact-email-btn"
        >Email Us</button>
      </div>
      <div class="contact-grid-form">
        <ContactForm/>
      </div>
    </div>
  </section>
</template>

<script>
import ContactForm from "./ContactForm.vue";
export default {
  name: "Contact",
  components: {
    ContactForm
  }
};
</script>

<style lang="scss" scoped>
.contact {
  background: url("~assets/open-sign.png");
  background-repeat: no-repeat;
  background-size: cover;
  padding: 75px 20px;
  position: relative;

  @media screen and (min-width: 992px) {
    padding: 125px 20px;
  }
}

.contact-back-filter {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}

.contact-grid {
  position: relative;
  display: grid;
  grid-template-columns: 1fr;
  grid-row-gap: 125px;
  width: 1000px;
  max-width: 100%;
  margin: 0 auto;

  @media screen and (min-width: 992px) {
    grid-template-columns: 1fr 1fr;
    grid-column-gap: 100px;
  }

  h1,
  h2,
  h3,
  h4,
  h5,
  p,
  a {
    color: white;
    margin-bottom: 15px;
  }
}

.contact-grid-content {
  padding: 0px 15px;
}

.contact-content-title {
  font-weight: bold;
}

.contact-email-btn {
  padding: 15px 30px;
}
</style>
