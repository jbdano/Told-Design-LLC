<template>
  <section class="our-team">
    <div class="ot-grid">
      <template v-for="(member, index) in members">
        <div :class="['ot-photo-block', member.photoClass]" :key="'photo-block'+index"></div>
        <div class="ot-bio-block" :key="'bio-block'+index">
          <h4 class="ot-bio-name">{{member.name}}</h4>
          <p class="ot-bio-title">{{member.title}}</p>
          <p class="ot-bio-bio">{{member.bio}}</p>
        </div>
      </template>
    </div>
    <template v-for="(member, index) in members">
      <img
        :src="member.funImagePath"
        class="hiddenTeamPhoto"
        alt="member.name"
        :key="'photo-'+index"
      >
    </template>
  </section>
</template>

<script>
export default {
  name: "OurTeam",
  data() {
    return {
      members: [
        {
          name: "Tim O'Neil",
          funImagePath: require("~/assets/tim_oneil_fun.jpg"),
          photoClass: "photo-tim",
          title: "Copywriter",
          bio:
            "After receiving a degree in biomedical engineering, I became obsessed with entrepreneurship and the startup world while pursuing a Master’s in Business. After graduating, I spent a year interviewing young entrepreneurs and writing about startups for a digital media production I co-founded, The Hum. Through this work, I developed a deep knowledge of copywriting, content marketing, email marketing, and what makes successful startups tick. I also maintain a roller coaster, love/hate relationship with distance running and a steady, love/love relationship with food."
        },
        {
          name: "Maya Rhinehart",
          funImagePath: require("~/assets/maya_rhinehart_fun.jpg"),
          photoClass: "photo-maya",
          title: "UX Designer",
          bio:
            "An artist at heart, I knew that civil engineering wasn’t the right fit for me even before graduating with my degree. After stumbling upon the idea of design thinking in a behavioral psychology book, I instantly knew what had been missing. Thus began my journey into the world of UX design. Through theory; self-teaching and a UX Design internship with General Assembly, and practice; various freelance projects, I developed a unique eye and problem-solving strategy to design the best solutions for our clients. I also enjoy long walks on the beach, plants, chocolate chip cookies, and mediocre 90’s movies."
        },
        {
          name: "Julian Dano",
          funImagePath: require("~/assets/julian_dano_fun.jpg"),
          photoClass: "photo-julian",
          title: "Web Developer",
          bio:
            "I entered the entrepreneurship world immediately after graduating with a degree in industrial engineering. While working on my first startup full-time, I taught myself web development to carry out that project and, quite literally, fell in love. After my exit from that startup, I was hired full-time by Extreme Networks to work as a Web Developer to further my development skills. I used to be passionate about other things, but now it’s really just coding… and sushi… and sports."
        }
      ]
    };
  },
  methods: {
    handleScroll(event) {
      Array.from(document.getElementsByClassName("ot-photo-block")).forEach(
        function(item) {
          let rect = item.getBoundingClientRect();
          let top = rect.top;
          let bottom = rect.bottom;
          if (top > 0 && bottom < window.innerHeight) {
            let arr = item.className.split(" ");
            if (arr.indexOf("fun") == -1) {
              item.className += " fun";
            }
          } else {
            item.className = item.className.replace(/\bfun\b/g, "").trim();
          }
        }
      );
    }
  },
  created() {
    if (process.browser) {
      window.addEventListener("scroll", this.handleScroll);
    }
  },
  destroyed() {
    if (process.browser) {
      window.removeEventListener("scroll", this.handleScroll);
    }
  }
};
</script>

<style lang="scss" scoped>
.our-team {
  padding: 125px 25px;
  position: relative;
}

.ot-grid {
  display: grid;
  grid-template-columns: 1fr;
  @media screen and (min-width: 768px) {
    grid-template-columns: 1fr 1fr;
    grid-column-gap: 50px;
    width: 1000px;
    max-width: 100%;
    margin: 0 auto;
  }
}

.ot-photo-block {
  height: 250px;
  width: 250px;
  justify-self: center;
  background-size: cover;
  background-repeat: no-repeat;
  margin-bottom: 50px;
  filter: grayscale(100%) brightness(50%);
  box-shadow: 0 6px 30px 5px rgba(0, 0, 0, 0.12);
  transition: background-image 0.3s ease-out, filter 0.3s ease-out,
    width 0.3s ease-out, height 0.3s ease-out;

  &.fun {
    filter: grayscale(0%) brightness(100%);
    height: 255px;
    width: 255px;
  }
  @media screen and (min-width: 768px) {
    justify-self: right;
  }
}

.photo-tim {
  background-image: url("~assets/tim_oneil_prof.jpg");
  &.fun {
    background-image: url("~assets/tim_oneil_fun.jpg");
  }
}

.photo-maya {
  background-image: url("~assets/maya_rhinehart_prof.jpg");
  &.fun {
    background-image: url("~assets/maya_rhinehart_fun.jpg");
  }
}

.photo-julian {
  background-image: url("~assets/julian_dano_prof.jpg");
  &.fun {
    background-image: url("~assets/julian_dano_fun.jpg");
  }
}

.ot-bio-name {
  text-align: center;
  margin-bottom: 15px;
  @media screen and (min-width: 768px) {
    text-align: left;
  }
}

.ot-bio-title {
  text-align: center;
  text-transform: uppercase;
  @media screen and (min-width: 768px) {
    text-align: left;
    margin-bottom: 5px;
  }
}

.ot-bio-bio {
  margin-bottom: 100px;
}

.hiddenTeamPhoto {
  width: 1px;
  height: 1px;
  position: absolute;
  left: -100vw;
}
</style>
