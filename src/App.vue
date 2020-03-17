<template>
    <div>
        <animal-list ref="animalList"></animal-list>
    </div>
</template>

<script>
    import AnimalList from './components/AnimalList.vue';

    export default {
        name: 'App',
        components: { AnimalList },
        created() {
            this.generate(500, {});
        },
        methods: {
            generate(amount, options) {
                this.$refs.animalList.generate(amount, options);
            },
        }
    }
</script>

<style>

</style>
