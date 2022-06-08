<template>
  <div class="signup--form">
        <form action="" @submit.prevent="handleSubmit">
          <div class="signup--form--container">
            <div class="signup--form--intro">
              <h3>Holla</h3>
              <p>Sign in to the vibe!</p>
            </div>
            <div class="signup--form--input">
              <label>Email address</label>
              <input
                type="email"
                name=""
                v-model="form.email"
                placeholder="Enter Email"
                id=""
              />
            </div>
            <div class="signup--form--input">
              <label>Password</label>
              <input
                type="password"
                name=""
                v-model="form.password"
                placeholder="Enter Password"
                id=""
              />
            </div>
            <button class="button--submit">SIGN UP</button>
            
            <div class="signup--form--terms">
              <p>
                By clicking on Login, you agree to our
                <span>Terms & Conditions and Privacy Policy</span>
              </p>
            </div>
          </div>
        </form>
      </div>
</template>

<script>
export default {
data() {
    return {
      form: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
      handleSubmit() {
          console.log('submitted')
      }
  }
}
</script>

<style lang="scss">
@import "@/styles/mixins.scss";
@import "@/styles/_variables.scss";
@import "@/styles/_typography.scss";
form {
  background: #ffffff;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.082937);
  border-radius: 6px;
  width: 50vw;
  height: 635px;
  padding: 2rem 1rem;
}
.signup--form--container {
  margin: 0 auto;
  width: 450px;
}
label {
  display: block;
  margin: 0.4rem 0;
  @include input {
    font-size: 16px;
    line-height: 20px;
    color: #30443c;
  }
}
::placeholder {
  @include placeholder;
}
.signup--form--intro {
  width: 400px;
  h3 {
    margin-bottom: 0.7rem;
    @include holla {
      font-weight: 400;
    }
  }
  p {
    @include holla-sign {
      font-weight: 400;
    }
  }
}
.signup--form--input {
  margin: 1.5rem 0;
  input {
    width: 400px;
    height: 45px;
    background: #ffffff;
    border: 1px solid #cad0c9;
    box-sizing: border-box;
    border-radius: 4px;
    padding: 0.5rem;
  }
}
button {
  margin: 2.5rem 0;
}

.signup--form--terms {
  margin: 1.5rem auto 0 auto;
  max-width: 100%;
  width: 405px;
  text-align: center;
  p {
    @include login {
      color: #97a19d;
    }
    span {
      color: $access-bg;
    }
  }
}
</style>