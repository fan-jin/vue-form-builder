<template>
    <div>
        <label>
            <vs-checkbox name="isMultiLine" v-model="control.isMultiLine">Multi-line?</vs-checkbox>
        </label>
    </div>
</template>

<script>
    export default {
        name: "TextConfigComponent",
        props: {
            control: {
                type: Object
            },
        },
    }
</script>

<style scoped>

</style>
