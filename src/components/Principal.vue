<script>
import DivBusca from './DivBusca.vue'
import ImgsTop from './ImgsTop.vue'
import DivPokemons from './DivPokemons.vue'
import ImgsBottom from './ImgsBottom.vue'
import { Pokedex } from 'pokeapi-js-wrapper'
export default {
    components: {
        DivBusca,
        ImgsTop,
        DivPokemons,
        ImgsBottom
    },
    async created() {
        const P = new Pokedex();
        const interval = { offset: 10, limit: 10}
        P.getPokemonsList(interval).then(function(response) {
            console.log(response.results[0].url)
            P.resource(response.results[0].url).then(function(pokemon){
                console.log('name', pokemon.name)
                console.log('id', pokemon.id)
                console.log('image', pokemon.sprites.other["official-artwork"].front_default)

                const types = pokemon.types.map((type) => type.type.name)
                console.log('types', types)

                pokemon.types.forEach((type) => {
                    P.getTypeByName(type.type.name).then(function(response){
                        const weak = response.damage_relations.double_damage_from.map((type) => type.name)

                        console.log('weaknesses of type ' + type.type.name, weak)
                    })
                })

                P.resource(pokemon.species.url).then(function(response){
                    console.log('description:\n', response.flavor_text_entries[0].flavor_text)
                })
            })
        })
    },
}
</script>

<template>

    <ImgsTop />

    <div class="absolute rounded-[6rem] bg-[#55feebc2] w-[70%] h-[76%] m-[12%] flex flex-wrap justify-center m-[6%] pb-[3.1%]">

        <DivBusca />

        <div class="overflow-y-auto h-[80%]">
        
            <div class="flex flex-wrap max-w-[80%] max-h-[328px] justify-between mx-auto gap-[1rem]">

                <DivPokemons />

            </div>

        </div>

    </div>

    <ImgsBottom />

</template>