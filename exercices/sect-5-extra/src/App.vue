<template>
    <div class="container">
        <app-header></app-header>
        <hr>
        <div class="row">
            <ServerList></ServerList>
            <app-server-details></app-server-details>
        </div>
        <hr>
        <app-footer></app-footer>
    </div>
</template>

<script>
    import Header from './components/Shared/Header.vue';
    import Footer from './components/Shared/Footer.vue';
    import ServerList from './components/Server/ServerList.vue';
    import ServerDetails from './components/Server/ServerDetails.vue';

    export default {
        components: {
            appHeader: Header,
            ServerList,
            'app-server-details': ServerDetails,
            'app-footer': Footer
        }
    }
</script>

<style>

</style>
