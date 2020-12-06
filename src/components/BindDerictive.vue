<template>
    <div>
        <h1>Sign Up</h1>
        <br>
        <input v-model="email" :class="[email.length < 2 ? 'red' : 'green']">
        <br>
        <button onClick="alert('Sign Up')" v-bind:disabled="email.length < 2 " >Submit</button>
        <ul>
            <li v-for="mail in mails" :key="mail">{{mail}}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'bind-directive',
    data(){
        return{
            email: '',
            mails: [
                'warrior2215@gmail.com',
                'warrior2215@gmail.com',
                'warrior2215@gmail.com',
                'warrior2215@gmail.com',
                'warrior2215@gmail.com'
            ]
        }
    }
}
</script>

<style>
.red{
    border: 2px solid red;
}
.green{
    border: 2px solid green;
}
</style>