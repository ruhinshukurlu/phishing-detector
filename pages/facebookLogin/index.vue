<template>
    <div class="flex flex-col items-center">
        <div class="flex bg-[#365899] w-full">
            <img class="w-32" src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/7c/Facebook_New_Logo_%282015%29.svg/1280px-Facebook_New_Logo_%282015%29.svg.png" alt="">
        </div>
        <div class="flex flex-col px-4 w-full lg:w-1/5 mt-20 space-y-4">
            <div class="flex justify-between space-x-3 items-center">
                <label for="email">Email or phone</label>
                <input v-model="email" class=" border rounded-sm border-gray-200 focus:outline-none focus:border-blue-400" type="email" name="email" id="email" >
            </div>
            <div class="flex justify-between space-x-3 items-center">
                <label for="password">Password</label>
                <input v-model="pass" class=" border rounded-sm border-gray-200 focus:outline-none focus:border-blue-400" type="password" name="password" id="password">
            </div>
            <div class="flex justify-end">
                <button @click="saveDynamicDataToFile" class="px-2 py-1 bg-[#365899] text-white rounded-sm">Login</button>
            </div>
        </div>
        <div v-if="error" class="flex justify-center bg-red-400 p-2 rounded-sm">
            <span class="text-white">Fields are required</span>
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