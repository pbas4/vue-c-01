<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User Name: {{ myName }}</p>
        <p>User Age: {{ mutableUserAge }}</p>
        <p>User Name Reverser: {{ switchName() }}</p>
        <button @click="resetName">Reset Name</button>
        <button @click="resetFn()">Reset Name Fn</button>
    </div>
</template>

<script>
    import { eventBus } from '../main'

    export default {
        props: {
            myName: {
                type: String,
                default: 'Carles',
                // required: true
            },
            resetFn: Function,
            userAge: Number
        },
        data: function() {
            return {
                mutableName: this.myName,
                mutableUserAge: this.userAge
            }
        },
        methods: {
            switchName() {
                return this.myName.split("").reverse().join("")
            },
            resetName() {
                this.mutableName = 'Max'
                this.$emit('nameWasReset', this.mutableName)
            }
        },
        created() {
            eventBus.$on('ageWasEdited', (age) => {
                console.log('userDetail age', age)
                this.mutableUserAge = age
            })
        }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
