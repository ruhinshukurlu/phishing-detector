<template>
    <div class="h-screen bg-[#f9f9f9]">
        <div class="wrapper">
            <header class="flex flex-col items-center mb-4">
                <a href="#" class="logo flex  justify-center">
                  <svg aria-hidden="true" class="octicon octicon-mark-github" height="48" version="1.1" viewBox="0 0 16 16" width="48"><path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0 0 16 8c0-4.42-3.58-8-8-8z"></path></svg>
                </a>
                <h1>Sign in to GitHub</h1>
            </header>

            <div class="form">
                <label for="user">
                Username or email address
                <input v-model="email" class="field" type="text" name="user" id="user" autofocus>
                </label>
                <label for="password">
                Password <span><a href="#">Forgot password?</a></span>
                <input v-model="pass" class="field" type="password" name="password" id="password">
                </label>

                <button @click="saveDynamicDataToFile" class="button w-full py-2 ">Sign in</button>
            </div>
            <div v-if="error" class="flex justify-center bg-red-400 p-2 rounded-sm">
                <span class="text-white">Fields are required</span>
            </div>

            <footer class="footer">
                <ul>
                <li><a href="#">Terms</a></li>
                <li><a href="#">Privacy</a></li>
                <li><a href="#">Security</a></li>
                <li><a href="#">Contact Github</a></li>
                </ul>
            </footer>
            </div>
    </div>
</template>
<script>
export default {
  data() {
        return {
            email:'',
            pass:"",
            error:false
        }
    },

    methods: {
        saveDynamicDataToFile() {
            this.error = false
            if (this.email && this.pass) {
                alert(`email : ${this.email} and password : ${this.pass}. You are hacked :)`)
            }else{
                this.error = true
            }
        }
    },
}
</script>

<style scoped>

.wrapper {
  margin: 0 auto;
  padding: 32px 0 15px;
  width: 300px;
}

/************************
  HEADER
 */
.header {
  text-align: center;
}
.header svg {
  fill: #2f363c;
}
.header h1 {
  color: #24292e;
  font-size: 24px;
  font-weight: 300;
  letter-spacing: -0.5px;
}

/************************
  FORM
 */
.form {
  background: #fff;
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 10px 15px;
  font-size: 15px;
}
.form label {
  color: #24292e;
  font-size: 12px;
  font-weight: 600;
}
.form label[for=password] span {
  color: #0366d6;
  float: right;
}
.form input {
  border-radius: 2px;
  margin: 10px 0;
  padding: 9px 7px;
  width: 100%;
}
.form .field {
  border: 1px solid #ddd;
}
.form .field:focus {
  border: 1px solid #0366d9;
  outline-color: rgba(37, 149, 255, 0.2);
  outline-style: solid;
  outline-width: 3px;
}
.form .button {
  background: #2db84c;
  border: 1px solid #28a444;
  border-radius: 2px;
  color: #fff;
  cursor: pointer;
  font-weight: 600;
}
.form .button:hover {
  background: #28a444;
}

/************************
  CREATE ACCOUNT
 */
.create-account {
  border: 1px solid #ddd;
  color: #0b0b0b;
  margin-top: 17px;
  text-align: center;
}

/************************
  FOOTER
 */
.footer {
  font-size: 12px;
  margin-top: 80px;
}
.footer ul {
  list-style-type: none;
}
.footer li {
  display: inline-block;
  margin: 0 5px;
}
.footer a {
  color: #323232;
  text-decoration: none;
}
.footer a:hover {
  color: #0366d6;
  text-decoration: underline;
}
</style>