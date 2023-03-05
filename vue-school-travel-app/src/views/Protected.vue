<template>
    <div>
        <h1>Greetings, {{ username }}</h1>
        <button @click="logout">Logout</button>
        <router-link :to="{name: 'invoices'}">
            <button>Invoices</button>
        </router-link>
    </div>
</template>
<script>
import router from '@/router';
import { findProp } from '@vue/compiler-core';
import {ref, computed} from 'vue';
import {useRouter, useRoute} from 'vue-router'
    export default {
        setup(){
            const username = computed(() => window.user)
            const router = useRouter()
            const route = useRoute()
            const logout = () => {
                window.user = null
                router.push({name: 'Home'})
            }
            return {username, logout}
        }

    }
</script>


