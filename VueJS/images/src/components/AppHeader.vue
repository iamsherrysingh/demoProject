<template>
    <div class="ui secondary pointing menu">
        <router-link to='/' class="active item">Image Storage</router-link>

        <div class="right menu">
            <div v-if="isLoggedIn" class="horizontal">
                <router-link to='/' class='item'>Gallery</router-link>
                <router-link to='/upload' class='item'>Upload</router-link>
                <a v-on:click="logout" class='item'>Logout</a>
            </div>

            <a v-else class="ui item" v-on:click="login">
                login
            </a>
        </div>
        
    </div>
</template>


<script>
import { mapActions, mapGetters } from 'vuex';


export default {
    name: 'AppHeader',
    methods: mapActions(['login', 'logout']),
    computed: mapGetters(['isLoggedIn'])

    
}
</script>


<style scoped>
    .horizontal{
        display: flex;
        flex-direction: row;
    }
</style>