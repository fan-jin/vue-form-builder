<template>
    <vs-popup title="Preview" :active.sync="popupActive">
        <div v-if="formData !== null">
            <form-builder-gui ref="FormBuilderGui" :form="formData" :key="formData._uniqueId"></form-builder-gui>
        </div>
    </vs-popup>
</template>

<script>
    import FormBuilderGui from 'sethFormBuilder/gui/FormBuilderGui';

    export default {
        name: "PreviewComponent",
        components: {FormBuilderGui},
        props: ['form'],
        data: () => ({
            popupActive: false,
            formData: null
        }),
        methods: {
            openModal(formData) {
                // set data
                this.formData = _.cloneDeep(formData);
                this.formData._uniqueId = Math.random();

                // open
                this.popupActive = true;
            },
            getData() {
                console.log(this.$refs.FormBuilderGui.getValue());
            },
        },
    }
</script>

<style scoped>

</style>
