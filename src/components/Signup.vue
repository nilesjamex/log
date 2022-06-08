<template>
  <div class="signup--form">
        <form action="" @submit.prevent="submit">
          <div class="signup--form--container">
            <div class="signup--form--name--box">
              <div class="signup--form--name">
                <label>First Name</label>
                <input
                  type="text"
                  name=""
                  v-model="form.firstname"
                  placeholder="Enter First Name"
                  id=""
                  required
                />
              </div>
              <div class="signup--form--name">
                <label>Last Name</label>
                <input
                  type="text"
                  name=""
                  v-model="form.lastname"
                  placeholder="Enter Last Name"
                  id=""
                  required
                />
              </div>
            </div>
            <div class="signup--form--input">
              <label>Email address</label>
              <input
                type="email"
                name=""
                v-model="form.email"
                placeholder="Enter Email"
                id=""
                required
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
                required
              />
            </div>
            <div class="signup--form--input">
              <label>Confirm Password</label>
              <input
                type="password"
                name=""
                v-model="form.password_confirmation"
                placeholder="Confirm Password"
                id=""
                required
              />
            </div>
            <button class="button--submit">SIGN UP</button>
           
          </div>
          <div class="signup--form--terms">
          <p>
            By clicking on Login, you agree to our
            <span>Terms & Conditions and Privacy Policy</span>
          </p>
        </div>
        </form>
      </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        firstname: "",
        lastname: "",
        email: "",
        password: "",
        password_confirmation: "",
      }
    }
  },
  methods: {
      submit() {
          console.log('yah')
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
  height: 100vh;
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
.signup--form--name--box {
  width: 400px;
  @include flex(space-between);
  input {
    background: #ffffff;
    border: 1px solid #cad0c9;
    box-sizing: border-box;
    border-radius: 4px;
    width: 180px;
    height: 45px;
    padding: 0.5rem;
    @include input;
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
  margin: 0.5rem auto 0 auto;
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