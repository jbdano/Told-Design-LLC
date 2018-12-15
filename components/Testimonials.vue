<template>
  <section class="testimonials">
    <div class="test-grid">
      <article
        class="test-grid-item"
        v-for="(testimonial, index) in testimonials"
        :key="'testimonial-'+index"
      >
        <img class="test-grid-img" :src="testimonial.image" :alt="testimonial.company">
        <h5 class="test-grid-company">{{testimonial.company}}</h5>
        <q class="test-grid-quote">{{testimonial.quote}}</q>
        <p class="test-grid-author">{{'- '+testimonial.author}}</p>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  name: "Testimonials",
  data() {
    return {
      testimonials: [
        {
          image: require("~/assets/givebutter.jpg"),
          company: "Givebutter",
          author: "Max Friedman, CEO",
          quote:
            "Working with the team at Told Design has been incredibly easy and they have produced awesome content for us so far. They take time to understand our brand and develop copywriting projects to help expand that brand. They have a talent for making complex or lengthy topics and stories enjoyable to read and easy to understand for our audience."
        },
        {
          image: require("~/assets/fisher_guiding.jpg"),
          company: "Fisher Guiding",
          author: "Luke CampbellL, Co-Founder And CMO",
          quote:
            "What really makes Told Design a trusted partner is that, with the professionalism and thoughtfulness they brought to our project, they made a positive impression with our guide partners that embodied our commitment to promoting their services."
        },
        {
          image: require("~/assets/startup_island.jpg"),
          company: "Startup Island",
          author: "Josh Gershon, Chief Of Vision",
          quote:
            "Working with Told Design has been wonderful. They bring so much entrepreneurial spirit and energy to our partnership, that it feels as though they are members of our team. This passion shows up in their work, and our brand has been able to enhance the stories we tell as a result of this collaboration."
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.testimonials {
  text-align: center;
  padding: 75px 25px;
}

.test-grid {
  display: grid;
  grid-template-columns: 1fr;
  grid-row-gap: 75px;

  @media screen and (min-width: 768px) {
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    grid-column-gap: 75px;
    width: 1200px;
    max-width: 100%;
    margin-left: auto;
    margin-right: auto;
  }
}

.test-grid-img {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  margin-bottom: 25px;
  box-shadow: 0 16px 38px -12px rgba(0, 0, 0, 0.56),
    0 4px 25px 0 rgba(0, 0, 0, 0.12), 0 8px 10px -5px rgba(0, 0, 0, 0.2);
}

.test-grid-company {
  margin-bottom: 15px;
}

.test-grid-author {
  font-size: 0.9em;
  margin-top: 15px;
}

.test-grid-quote {
  font-size: 0.9em;
}
</style>
