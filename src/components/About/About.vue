<template lang="html">
  <transition name="showAbout">
    <div class="about">
      <i @click="showAbout" class="close"></i>
      <div class="about-content">
        <h1>on</h1>
        <h2>Vue.js+Socket.ioCreate a smart chat room</h2>
        <p class="skill"><b>Technology stack</b>：</p>
        <div>Vue2(Page build + data driven)<br>Socket.io(Real-time communication)<br>Vuex(Different component state sharing)<br>vue-router(routing)<br>axios(Initiate an http request)<br>SASS(SCSS)<br>Express(The online version is Koa2)<br>Webpack(Automated build)<br>Moment.js(Time processing)<br>ES6(Throughout)<br>localStorage(HTML5)<br>CSS3(Animation and style)</div>
        <p class="url"><b>GitHub</b>：<a @touchstart="isHover=true" @touchEnd="isHover=false" :class="{hover: isHover}" href="https://github.com/Marlin005/" target="_blank">GitHub</a></p>
        <p class="url"><b>Personal website</b>：<a @touchstart="isHover=true" @touchEnd="isHover=false" :class="{hover: isHover}" href="https://github.com/Marlin005/" target="_blank">Marlin005</a></p>
        <p><br>&nbsp;&nbsp;&nbsp;Unemployed code farmers, seeking work ~ ~ If you think the project is good, you can also ask me to eat spicy</p>
        <div class="help">
          <img src="./help.png" alt="Marlin005">
        </div>
        <p class="copyright"><b>statement</b>：This project is for learning and communication purposes only, please do not use it for any commercial purposes. Please contact the author if you have any questions. <br><a href="mailto:github.com/Marlin005" ">github.com/Marlin005/" </a></p>
      </div>
      <div @click="showAbout" class="mask"></div>
    </div>
  </transition>

</template>

<script>
export default {
  name: 'about',
  data() {
    return {
      isHover: false
    }
  },
  computed: {
    isShowAbout() {
      return this.$store.state.isShowAbout;
    }
  },
  methods: {
    showAbout() {
      this.$store.commit('showAbout', false);
    }
  }

}
</script>

<style lang="scss" scoped>
  a {
    color: #3F51B5;
  }

  .about {
    display: flex;
    position: absolute;
    z-index: 2;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    width: 100%;
    height: 100%;
    justify-content: center;
    align-items: center;
    color: black;
    // background-color: rgba(0, 0, 0, .5);
    .close {
      position: absolute;
      z-index: 3;
      display: inline-block;
      width: 30px;
      height: 30px;
      background: url('./close.svg') no-repeat;
      background-size: contain;
      top: 11%;
      right: 12%;
    }
    @media screen and (min-width: 760px) {
      .close {
        right: 26%;
      }
    }
    .about-content {
      position: relative;
      z-index: 2;
      width: 80%;
      height: 80%;
      background-color: white;
      border-radius: 10px;
      padding: 30px 10px;
      box-shadow: 0 0 20px gray;
      overflow: auto;

      h1 {
        text-align: center;
        font-size: 1.2rem;
        color: #31c27c;
        transition: .3s ease-in-out;
      }
      h1:hover {
        transform: rotate(15deg);
        transition: .3s ease-in-out;
      }
      h2 {
        font-size: 1.1rem;
        text-align: center;
      }
      p {
        text-indent: 1em;
        word-break: break-all;
        margin-top: 6px;

        b {
          display: inline-block;
          transition: .3s ease-in-out;
        }
        b:hover {
          transform: rotate(-10deg);
          transition: .3s ease-in-out;
        }

      }
      p.copyright {
        text-indent: 0;
      }
      div {
        // letter-spacing: 1px;
        padding-left: 50px;
      }
      .help {
        padding: 0;
        width: 100%;
        img {
          width: 100%;
          height: auto;
        }
      }
    }
    @media screen and (min-width: 760px) {
      .about-content {
        width: 50%!important;
      }
    }
    .mask {
      position: absolute;
      z-index: 0;
      width: 100%;
      height: 100%;
      background: none;
    }
  }
  .showAbout-enter-active {
    transition: all .4s ease-in-out;
  }
  .showAbout-leave-active {
    transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
  }
  .showAbout-enter, .showAbout-leave-active {
    transform: rotateZ(180deg);
    opacity: 0;
  }
</style>
