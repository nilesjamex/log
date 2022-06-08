<template>
 <section class="signup">
   <div class="signup--box">
     <div class="signup--intro square">
        <div v-if="toShow === 1" class="signup--intro--content">
          <div class="signup--intro--content--img">
            <img src="@/assets/welcome.svg" alt="" />
          </div>
          <div class="signup--intro--content--text">
            <h2>
              <span>Welcome back!</span> <br />
              We miss you.
            </h2>
          </div>
          <div class="signup--form--login">
              <p>
                Don't have an account?
                <span @click="handleTwo">Register Here</span>
              </p>
            </div>
        </div>
         <div v-else class="signup--intro">
        <div class="signup--intro--content">
          <div class="signup--intro--content--img">
            <img src="@/assets/girl.svg" alt="" />
          </div>
          <div class="signup--intro--content--text">
            <h2><span>Welcome!</span> Let’s get to know you.</h2>
            <p>
              Your first step toward a better financial lifestyle starts here.
            </p>
          </div>
           <div class="signup--form--login">
              <p>
                Already have an account?
                <span @click="handleOne">Login Here</span>
              </p>
            </div>
        </div>
      </div>
      </div>
      <div class="square">
        <Login v-if="toShow === 1" />
        <Signup v-else />
      </div>
   </div>
 </section>
</template>

<script>
import Login from '@/components/Login.vue';
import Signup from '@/components/Signup.vue';
import { gsap } from 'gsap';
import { Flip } from 'gsap/Flip';
gsap.registerPlugin(Flip);
export default {
  name: 'App',
  components: {
    Login,
    Signup
  },
  data() {
    return {
      toShow: 1
    }
  },
  methods: {
    handleOne() {
      this.toShow = 1;
      this.flipit()
    },
    handleTwo() {
      this.toShow = 2;
      this.flipit()
    },
    flipit() {
      const squares = gsap.utils.toArray('.square');
      const state = Flip.getState(squares);
      swap(squares);
      Flip.from(state, {
        duration: 1,
        delay: 0.2,
        ease: 'power1.inOut'
      });
      function swap([a, b]) {
        a.parentNode.children[0] === a ? a.parentNode.appendChild(a) : a.parentNode.appendChild(b);
      }
    }
  }
}
</script>

<style lang="scss">
@import "@/styles/mixins.scss";
@import "@/styles/_variables.scss";
@import "@/styles/_typography.scss";
.signup {
  background: #fcfbfc;
}
.signup--box {
  @include flex(center,);
}
.signup--intro {
   background: $access-bg;
}
.signup--intro--content {
  width: 50vw;
  height: 100vh;
  padding: 7% 0;
  margin: auto;
  text-align: center;
}
.signup--intro--content--text {
  text-align: center;
  margin: auto;
  h2 {
    width: 369px;
    margin: 1.5rem auto 0 auto;
    @include heading1 {
    }
    span {
      @include heading1 {
        color: white;
      }
    }
  }
  p {
     @include heading1 {
       width: 569px;
       margin: 0.1rem auto;
    }
  }
}
.signup--form--login {
  margin: 3rem auto 0 auto;
  max-width: 100%;
  width: 287.43px;
  p {
    @include login;
    span {
      cursor: pointer;
      color: #3F3D56;
    }
  }
}

</style>
