<script>
export default {
    name: 'DivPokemonsItem',
    props: {
        name: {
            type: String,
            default: 'Default'
        },
        img: {
            type: String,
            default: ''
        }
    }
}
</script>
<template>
    <div class="rounded-[15%] bg-[#ffffffd6] max-w-[100%] max-h-[328px] min-w-[21%] lg:h-[328px] lg:w-[23%] flex flex-col items-center justify-center">
        <div class="rounded-[15%] border-[2px] border-solid border-[#00000046] min-w-[100%] h-[100%] flex flex-col items-center justify-center type-grass">
            <p class="relative left-[30%] text-[18px] font-bold">Nº 1</p>
            <img class="w-[80%] h-[65%]" :src="img"/>
            <p class="text-[30px]">{{ name }}</p>
        </div>
    </div>

    <div class="rounded-[15%] bg-[#ffffffd6] max-w-[100%] lg:w-[23%] min-w-[21%] max-h-[328px] h-[328px] flex flex-col items-center justify-center">
        <div class="rounded-[15%] border-[2px] border-solid border-[#00000046] min-w-[100%] max-h-[328px] h-[350px] flex flex-col items-center justify-center type-grass">

            <p class="flex flex-wrap justify-center gap-[10px]"><span class="rounded-[50px] border-[1px] border-solid border-[#hahahhaha] w-[80px] h-[25px] text-[18px] flex justify-center items-center font-bold grass">Grass</span> <span class="rounded-[50px] border-[1px] border-solid border-[#hahahhaha] w-[80px] h-[25px] text-[18px] flex justify-center items-center font-bold poison">Poison</span></p>
            <p class="relative right-[28%] text-[18px] font-bold">Fraquesas:</p>
            <p class="flex flex-wrap justify-center gap-[10px]"><span class="rounded-[50px] border-[1px] border-solid border-[#hahahhaha] w-[80px] h-[25px] text-[18px] flex justify-center items-center font-bold fire">Fire</span> <span class="rounded-[50px] border-[1px] border-solid border-[#hahahhaha] w-[80px] h-[25px] text-[18px] flex justify-center items-center font-bold ice">Ice</span> <span class="rounded-[50px] border-[1px] border-solid border-[#hahahhaha] w-[80px] h-[25px] text-[18px] flex justify-center items-center font-bold flying">Flying</span> <span class="rounded-[50px] border-[1px] border-solid border-[#hahahhaha] w-[80px] h-[25px] text-[18px] flex justify-center items-center font-bold psychic">Psychic</span></p>
            <p class="m-[15px] text-[14px] text-justify">
            Stats
            HP
            Attack
            Defense
            Special Attack
            Special Defense
            Speed>
            For some time after its birth, it uses the nutrients that are packed into the seed on its back in order to grow.
            </p>

        </div>
    </div>
</template>