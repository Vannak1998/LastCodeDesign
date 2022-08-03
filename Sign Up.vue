<template>
    <div class="w-1/2 m-auto bg-orange-50 text-lg border rounded shadow-lg my-8">
        <form @submit.prevent="SignUp">
            <div class="text-xl">
                <div class="text-3xl font-bold border p-4 shadow-sm">
                    <h1 class="mx-14">Sign Up Form</h1>
                </div>
                <div class="mx-16 p-2">
                    <p>Please fill in this form to create an account.</p>
                </div>
            </div>
            <div class="space-y-4 my-8">
                <div class="flex mx-8 space-x-4 text-xl">
                    <div class="py-2 w-full">
                        <label for="">First Name</label>
                        <input type="text" v-model="form.firstname" required class=" w-full py-2 px-2 border rounded">
                    </div>
                    <div class=" py-2 w-full">
                        <label for="">Last Name</label>
                        <input type="text" v-model="form.lastname" required class="w-full py-2 px-2 border rounded">
                    </div>
                </div>
                <div class="mx-8 text-xl">
                    <label for="">Email</label><input type="email" v-model="form.email" requered class="w-full py-2 px-2 border rounded">
                </div>
                <div class="mx-8 text-xl ">
                    <label for="">Password</label><input type="password" v-model="form.password" required class="w-full py-2 px-2 border rounded">
                </div>
                <div class="mx-8 text-xl">
                    <label for="">Re-password</label><input type="password" v-model="form.repassword" required class="w-full py-2 px-2 border rounded">
                </div>
                <div class="mx-8 text-lg" >
                    <label> <input type="checkbox" checked="checked" name="remember"> Remember me </label>
                </div>
                <div  class="mx-8 text-lg">
                    <p>By creating an account you agree to our <a href="#" style="color:dodgerblue">Terms & Privacy</a>.</p>
                </div>
                <button @click="SignUp" class="border rounded py-2 px-4 mx-8 bg-sky-500 text-lg text-white font-bold">Sign Up</button>
            </div>
        </form>
    </div>
</template>
<script>
    export default{
        name:'Sign Up',
         data(){
            return{
                form:{
                    firstname: '',
                    lastname:'',
                    email: '',
                    password: '',
                    repassword:''
                }
            }
        },
          methods:{ 
            SignUp(){
                this.$store.commit('Sign Up',this.form.email)
            }  
        }
    }
</script>