<script setup>
import { ref } from 'vue';
import Search from '@components/Inputs/Search.vue';
import UserInfo from '@components/User/UserInfo.vue';
import Button from '@components/Button/Button.vue';
import Badge from '@components/Badge/Badge.vue';

const props = defineProps(['title']);
const data = ref({
    image: 'https://avatars.githubusercontent.com/u/2681643',
    name: 'Tolga Eğilmezel',
    email: 'egilmezel@tolga.com'
})

const searchHandler = (value) => {
    alert(value);
}
</script>

<template>
    <header class="header">
        <div class="header__title">
            {{ title }}
        </div>
        <div class="header__content">
            <Search placeholder="Search" @search="searchHandler" />
        </div>
        <div class="header__actions">
            <div class="btn-group">
                <Button icon="chat" variant="icon" classes="text-strong" />
                <Badge icon="notifications" active/>
                <Button icon="settings" variant="icon" classes="text-strong" />
            </div>
            <UserInfo :data="data" />
        </div>
    </header>
</template>