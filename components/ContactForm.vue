<template>
  <div class="contact-form">
    <div class="cf-main">
      <div class="cf-banner">
        <p class="cf-banner-title">Contact Us</p>
      </div>
      <form class="cf-form">
        <div class="form-group">
          <input type="text" class="form-control cf-input" value placeholder="Your Name">
        </div>
        <div class="form-group">
          <input type="email" class="form-control cf-input" value placeholder="Your Email">
        </div>
        <div class="form-group">
          <input type="text" class="form-control cf-input" value placeholder="Subject">
        </div>
        <div class="form-group">
          <textarea
            value
            class="form-control cf-input cf-input-message"
            placeholder="Tell us what you're looking for"
            rows="8"
          ></textarea>
        </div>
        <div class="cf-footer">
          <button
            type="submit"
            class="theme-inline-button theme-inline-button-primary cf-submit-btn"
          >SEND IT</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactForm"
};
</script>

<style lang="scss" scoped>
.contact-form {
  max-width: 425px;
  margin: 0 auto;
}

.cf-main {
  background-color: #fcfaf9;
  padding: 75px 15px 25px;
  border-radius: 5px;
  position: relative;

  @media screen and (min-width: 992px) {
    padding: 75px 40px 25px;
  }
}

.cf-input {
  background-color: transparent;
  border-radius: 0px;
  border-top: none;
  border-right: none;
  border-left: none;
  color: #3c4858;
  border-bottom: 1px solid rgba(0, 0, 0, 0.25);
  box-shadow: none;
  -webkit-box-shadow: none;

  &:focus {
    border-bottom: 1px solid #50ada2;
  }
  &::placeholder {
    color: rgba(0, 0, 0, 0.25);
    font-family: "Josefin Sans", sans-serif;
  }
  &-message {
    resize: none;
  }
}

.cf-banner {
  padding: 25px 0px;
  width: 80%;
  background-color: #50ada2;
  position: absolute;
  top: 0;
  left: 50%;
  transform: translate(-50%, -50%);
  border-radius: 5px;
  text-align: center;
  box-shadow: 0 16px 38px -12px rgba(0, 0, 0, 0.56),
    0 4px 25px 0 rgba(0, 0, 0, 0.12), 0 8px 10px -5px rgba(0, 0, 0, 0.2);
}

.cf-banner-title {
  color: #fcfaf9;
  font-weight: bold;
  margin: 0;
}

.cf-footer {
  text-align: right;
}

.cf-submit-btn {
  color: #fcfaf9;
  padding: 15px 30px;
  margin-top: 20px;
}
</style>
