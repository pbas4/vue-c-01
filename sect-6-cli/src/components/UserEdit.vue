<template>
    <div class="component">
        <h3>You may edit the User here</h3>
        <p>Edit me!</p>
        <p>User Age: {{ userAgeMutable }}</p>
        <button @click="editAge">Edit Age</button>
    </div>
</template>

<script>
    import { eventBus } from '../main'

    export default {
        props: ['userAge'],
        data: function() {
            return {
                userAgeMutable: this.userAge
            }
        },
        methods: {
            editAge() {
                this.userAgeMutable = 30;
                // this.$emit('ageWasEdited', this.userAge)
                // eventBus.$emit('ageWasEdited', this.userAgeMutable)
                eventBus.changeAge(this.userAgeMutable)
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightgreen;
    }
</style>
