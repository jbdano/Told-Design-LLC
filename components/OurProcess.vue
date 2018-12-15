<template>
  <section class="our-process">
    <h3 class="op-title">It's all about the approach.</h3>
    <p class="op-subtitle">
      We take a unique approach to design and build
      websites, newsletters, and blogs that make your company better.
      And we’d like to think we’re pretty good at it.
    </p>
    <div class="op-grid">
      <article class="op-grid-item" v-for="step in steps" :key="step.id">
        <i :class="[ 'op-grid-img', step.iconClass ]" v-bind:style="{ color: step.iconColor }"></i>
        <h4 class="op-grid-title" v-text="step.title"></h4>
        <p class="op-grid-desc" v-text="step.description"></p>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  name: "OurProcess",
  data() {
    return {
      steps: [
        {
          id: "1",
          iconClass: "far fa-clipboard",
          iconColor: "#e91e63",
          title: "Learn",
          description:
            "We put in the time to learn about you, your company, your brand, your goals, and, most importantly, your customers."
        },
        {
          id: "2",
          iconClass: "fa fa-comments",
          iconColor: "#50ada2",
          title: "Collaborate",
          description:
            "We believe in a collaborative process. We are here to brainstorm, discuss, and tweak with you until we get things just right."
        },
        {
          id: "3",
          iconClass: "fa fa-truck",
          iconColor: "#4caf50",
          title: "Deliver",
          description:
            "We deliver value at all costs. If a project takes longer than anticipated, we will never charge you more than our original quote."
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.our-process {
  text-align: center;
  padding: 75px 25px;
}

.op-title {
  margin-bottom: 25px;
}

.op-subtitle {
  width: 75%;
  margin: 0 auto;
}

.op-grid {
  display: grid;
  grid-template-columns: 1fr;
  grid-row-gap: 75px;
  margin-top: 75px;

  @media screen and (min-width: 768px) {
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    grid-column-gap: 75px;
    width: 1200px;
    max-width: 100%;
    margin-left: auto;
    margin-right: auto;
  }
}

.op-grid-img {
  font-size: 100px;
  margin-bottom: 30px;
}

.op-grid-title {
  margin-bottom: 15px;
}

.op-grid-desc {
  margin: 0;
}
</style>
