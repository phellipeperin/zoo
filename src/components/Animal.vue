<template>
    <span class="ml-6">
        <v-icon
            class="mx-1"
            :class="[color]"
            v-text="'$vuetify.icons.' + species"
        />
        <span>{{ name }}</span>
    </span>
</template>

<script>
    export default {
        name: 'Animal',
        props: {
            species: { type: String, required: true },
            name: { type: String, required: true },
            color: { type: String, required: true },
            size: { type: String, required: true },
        }
    }
</script>

<style lang="scss" scoped>

</style>