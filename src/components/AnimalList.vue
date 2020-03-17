<template>
    <v-row>
        <v-col
            cols="12"
            sm="4"
            md="3"
            lg="2"
        >

        </v-col>
    </v-row>
</template>

<script>
    export default {
        name: 'AnimalList',
        data: () => ({ 
            list: [],
            // Possible
            possibleConsonants: ['b', 'c', 'd', 'f', 'g', 'h', 'j', 'k', 'l', 'm', 'n', 'p', 'q', 'r', 's', 't', 'v', 'w', 'x', 'z'],
            possibleVogals: ['a', 'e', 'i', 'o', 'u', 'y'],
            possibleColors: ['orange', 'light-blue', 'yellow', 'light-purple', 'red', 'light-green'],
            possibleSizes: ['x-small', 'small', 'regular', 'large', 'x-large'],
        }),
        methods: {
            generate(amount) {
                for (let i = 0; i < amount; i++) {
                    const species = i % 2 === 0 ? 'cat' : 'dog';
                    const size = species === 'cat' ? this.getRandomAnimalSize() : 'x-small';

                    this.list.push({
                        species,
                        size,
                        color: this.getRandomAnimalColor(),
                        name: this.generateAnimalName(4),
                    });
                }
            },
            // Aux
            generateAnimalName(size) {
                let name = '';
                for (let i = 0; i < size; i++) {
                    const possibleArray = i % 2 ? this.possibleVogals : this.possibleConsonants;
                    let letter = possibleArray[Math.floor(Math.random() * possibleArray.length)];
                    if (i === 0) letter = letter.toUpperCase();
                    name += letter;
                }
                return name;
            },
            getRandomAnimalColor() {
                return this.possibleColors[Math.floor(Math.random() * this.possibleColors.length)];
            },
            getRandomAnimalSize() {
                return this.possibleSizes[Math.floor(Math.random() * this.possibleSizes.length)];
            },
        },
    }
</script>

<style lang="scss" scoped>

</style>
