<template>
    <div>
        <form @submit.prevent="submit" >
            <div class="border rounded bg-slate-50 w-1/3 m-auto shadow-lg space-y-4 my-8">
                <div class="flex text-3xl justify-center font-bold uppercase border p-4 shadow-sm">
                    <h1>Login Form</h1>
                </div>
                <div class="mx-8 text-xl ">
                    <label for="">Email</label><br>
                    <input type="Email" v-model="form.email" required class="w-full py-2 px-2 border rounded bg-white">
                </div>
                <div class="mx-8 text-xl">
                    <label for="">Password</label><br>
                    <input type="Password" v-model="form.password" required class="w-full py-2 px-2 border rounded">
                </div>
                <div class="text-center ">
                    <button type="submit" class="border rounded py-2 px-4 m-4 bg-sky-500 text-lg text-white font-bold">Login</button>
                </div>
            </div>
        </form> 
    </div>
</template>
<script>
    export default{
        name:'Login',
        data(){
            return{
                form:{
                    email: '',
                    password: ''
                }
            }
        },
          methods:{ 
            submit(){
                this.$store.commit('login',this.form.email)
            }  
        }
    }
</script>