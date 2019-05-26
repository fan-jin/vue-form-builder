<template>
    <div>
        <div class="row mt-2" v-if="control.type !== 'checkbox'">
            <div class="col-md-12">
                <div class="form-group">
                    <vs-input type="text" class="form-control" v-model="control.defaultValue" label="Default Value"/>
                </div>
            </div>
        </div>

        <div class="row mt-2">
            <div class="col-md-12">
                <div class="form-group">
                    <vs-input type="text" class="form-control" v-model="control.label" label="Question"/>
                </div>
                <div class="form-group">
                    <vs-checkbox v-model="control.labelBold">Bold</vs-checkbox>
                    <vs-checkbox v-model="control.labelItalic">Italic</vs-checkbox>
                    <vs-checkbox v-model="control.labelUnderline"> Underline</vs-checkbox>
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
