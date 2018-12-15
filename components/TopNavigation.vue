<template>
  <nav class="navbar fixed-top navbar-expand-lg navbar-light bg-light" :class="{ isTop: atTop }">
    <div class="container">
      <a class="navbar-brand" href="#">
        <span>told</span>.design
      </a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNavDropdown"
        aria-controls="navbarNavDropdown"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavDropdown">
        <ul class="navbar-nav ml-auto mt-2 mt-lg-0">
          <li class="nav-item active">
            <a class="nav-link" href="#">
              Home
              <span class="sr-only">(current)</span>
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Portfolio</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "TopNavigation",
  data() {
    return {
      atTop: true
    };
  },
  methods: {
    handleScroll(event) {
      let top = $(window).scrollTop();
      this.atTop = top < 100 ? true : false;
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
.navbar-brand {
  color: #3c4858;
  span {
    color: #50ada2;
  }
}

li,
a {
  margin-bottom: 0px;
}

@media screen and (min-width: 992px) {
  .navbar {
    transition: all 0.3s ease-out;
    box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.15);
    padding-top: 0;
    padding-bottom: 0;
  }

  .navbar-nav {
    li {
      padding: 0.3rem 0.8rem;
      .nav-link {
        color: #3c4858;
      }

      &.active {
        background-color: #50ada2;
        .nav-link {
          color: #fcfaf9;
        }
      }
    }
  }

  .isTop {
    &.navbar {
      background-color: transparent !important;
      box-shadow: none;
    }
    .navbar-brand {
      color: #fcfaf9;
    }
    .navbar-nav li:not(.active) .nav-link {
      color: #fcfaf9;
    }
  }
}
</style>
