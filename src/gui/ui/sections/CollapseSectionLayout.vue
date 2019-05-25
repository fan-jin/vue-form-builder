<template>
    <div class="col-md-12 mb-2">
        <div class="collapseFormItem">
            <vs-collapse-item>
                <div slot="header">
                    {{section.label}}
                </div>
                <div :id="section.name + '_gui_body'" class="collapseBody collapse show">
                    <row-component :section="section" :key="section.name"></row-component>
                </div>
            </vs-collapse-item>

        </div>
    </div>
</template>

<script>
    import RowComponent from "sethFormBuilder/gui/ui/RowComponent";
    import {Hooks} from 'sethFormBuilder/gui/components/hook_lists';

    export default {
        name: "CollapseSectionLayout",
        components: {RowComponent},
        props: ['section'],
        created() {
            // before hook
            Hooks.Section.beforeRegister.run(this.section);
        },
        mounted() {
            // after hook
            Hooks.Section.afterRegister.run(this.section);
        },

    }
</script>

<style scoped>
    .clickable {
        cursor: pointer;
    }

    .collapseFormItem .title {
        font-weight: bold;
        border-bottom: 1px solid #000;
    }

    .collapseFormItem .collapsed .fa-chevron-up,
    .collapseFormItem .fa-chevron-down {
        display: none;
    }

    .collapseFormItem .collapsed .fa-chevron-down,
    .collapseFormItem .fa-chevron-up {
        display: inline-block;
    }
</style>
