<template>
    <div>
        <div class="row mt-2" v-if="control.type !== 'checkbox'">
            <div class="col-md-12">
                <div class="form-group">
                    <label>Default value</label>
                    <vs-input type="text" class="form-control" v-model="control.defaultValue"/>
                </div>
            </div>
        </div>

        <div class="row mt-2">
            <div class="col-md-12">
                <div class="form-group">
                    <label>Question label</label>
                    <vs-input type="text" class="form-control" v-model="control.label"/>
                </div>
                <div class="form-group">
                    <label><vs-checkbox v-model="control.labelBold"/> Bold</label>
                    <label><vs-checkbox v-model="control.labelItalic"/> Italic</label>
                    <label><vs-checkbox v-model="control.labelUnderline"/> Underline</label>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "BaseStyleComponent",
        props: {
            control: {
                type: Object
            },
        },
    }
</script>

<style scoped>

</style>
