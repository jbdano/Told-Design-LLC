<template>
  <section class="testimonial-overview">
    <div class="to-background-img"></div>
    <div class="to-content">
      <h3 class="to-title">Straight from the horse's mouth.</h3>
      <p class="to-description">
        We won’t stop until you’re irrationally excited
        about the work we’ve done. But don't just take our word for it.
        Read what our clients have to say.
      </p>
    </div>
  </section>
</template>

<script>
export default {
  name: "TestimonialOverview"
};
</script>

<style lang="scss" scoped>
.testimonial-overview {
  height: calc(400px + (400 - 400) * ((100vw - 300px) / (1600 - 300)));
  width: 100vw;
  max-width: 100%;
  position: relative;
}

.to-background-img {
  height: 100%;
  background: url("~assets/traveling-map.jpeg");
  background-repeat: no-repeat;
  background-size: cover;
  filter: grayscale(100%) brightness(20%);
  background-position: center;
}

.to-content {
  box-sizing: border-box;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  width: 100%;
  max-width: 800px;
  padding: 0 25px;
}

.to-title {
  color: #fcfaf9;
  font-size: calc(24px + (36 - 24) * ((100vw - 300px) / (1600 - 300)));
}

.to-description {
  color: #fcfaf9;
}
</style>
