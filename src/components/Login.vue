<template>
  <div class="login">
      <h2>{{loginView ? 'Log In' : 'Sign Up'}}</h2>
      <b-container>
            <b-form>
                <b-form-group>
                    <b-form-input :state="emailValid" placeholder="Enter Email ..." v-model="email"></b-form-input>
                    <br>
                    <b-form-input :state="passwordValid" type="password" placeholder="Enter Password ..." v-model="password"></b-form-input>
                    <br>
                    <b-form-input :state="passwordVerify" type="password" v-if="!loginView" placeholder="Confirm Password ..." v-model="passwordConfirm"></b-form-input>
                    <br>
                    <b-button :disabled="disableButton" @click="authenticate" variant="primary">{{ loginView ? 'Log In' : 'Sign Up'}}</b-button>
                    <br><br>
                    <a @click="toggleView">{{ !loginView ? 'Log In' : 'Sign Up'}}</a>
                </b-form-group>
            </b-form>
      </b-container>
  </div>
</template>

<script>
export default {
    name: 'Login',
    data() {
        return {
            loginView: true,
            email: '',
            password: '',
            passwordConfirm: '',
        }
    },
    methods: {
        toggleView() {
            this.loginView = !this.loginView
        },
        authenticate() {
            alert()
            if(this.loginView == true) {
                this.login()
            } else {
                this.signup()
            }
        },
        login() {

        },
        signup() {

        },
    },
    computed: {
        emailValid() {
            if (!this.email) {
                return null
            } else if (this.email.includes('@') && this.email.includes('.')) {
                return null;
            } else return false;
        },
        passwordValid() {
             if (!this.password) {
                return null
            } else if (this.password.length >= 6) {
                return null;
            } else return false;
        },
        passwordVerify() {
            if (!this.passwordConfirm) {
                return null
            } else if (this.passwordConfirm === this.password) {
                return null
            } else return false
        },
        disableButton() {
            if (!this.email && !this.password && !this.passwordConfirm) {
                return true
            } else return false
        },
    },
}
</script>

<style scoped>
    a {
        cursor: pointer;
    }
</style>