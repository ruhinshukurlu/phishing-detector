<template>
    <div class="flex flex-col items-center justify-center h-screen">
        <div class="flex space-y-4 flex-col border border-gray-300 rounded-md p-6 w-full md:w-1/3">
            <div class="flex flex-col items-center">
                <img class="w-1/4" src="https://play-lh.googleusercontent.com/1-hPxafOxdYpYZEOKzNIkSP43HXCNftVJVttoo4ucl7rsMASXW3Xr6GlXURCubE1tA=w3840-h2160-rw" alt="">
                <h1 class="font-bold text-xl text-center">Sign in</h1>
                <span>to countinue with <span class="text-blue-500">PhishingDetector</span></span>
            </div>
            <div class="flex flex-col space-y-3">
                <label for="email">Email : {{email}}</label>
                <input v-model="email" required class="p-4 border rounded-md border-gray-200 focus:outline-none focus:border-blue-400" type="email" name="email" id="email" placeholder="Enter Email...">
            </div>
            <div class="flex flex-col space-y-3">
                <label for="password">Password</label>
                <input v-model="pass" required class="p-4 border rounded-md border-gray-200 focus:outline-none focus:border-blue-400" type="password" name="password" id="password" placeholder="Enter Password...">
            </div>
            <div class="flex justify-end">
                <button @click="saveDynamicDataToFile" class="px-4 py-2 bg-blue-500 text-white rounded-md">Sign in</button>
            </div>
            <div v-if="error" class="flex justify-center bg-red-400 p-2 rounded-sm">
                <span class="text-white">Fields are required</span>
            </div>
        </div>


        <div class="flex w-1/3 mt-4 text-gray-500 justify-between">
            <a href="#">English</a>
            <div class="flex space-x-2">
                <a href="#">Help</a>
                <a href="#">Privacy</a>
                <a href="#">Terms</a>
            </div>
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