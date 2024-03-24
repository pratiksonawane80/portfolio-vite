<template>
    <h2 class="md:text-[46px] text-2xl font-semibold pt-16 pb-10">Technologies</h2>
    <div v-for="skill in technologiesData" :key="skill.name">
        <div class="flex justify-between md:mt-12 mt-8">
            <p class="md:text-3xl text-md md:font-semibold font-bold">{{ skill.name }}</p>
            <p class="md:text-lg text-md md:font-semibold font-bold">{{ skill.level }}</p>
        </div>
        <div class="h-4 rounded-3xl bg-[#162950] md:mt-8 mt-4">
            <p class="h-4 rounded-3xl bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7]" :class="skill.percentage">
            </p>
        </div>
    </div>

    <h2 class="md:text-[46px] text-2xl font-semibold mt-20 mb-10">Additional Technologies & Skills</h2>
    <div class="grid md:grid-cols-3 grid-cols-2 md:text-3xl text-md gap-6">
        <div class="flex items-center">
            <div class="w-6 h-6 bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7] rounded-full mr-6"></div>
            <span>Git</span>
        </div>
        <div class="flex items-center">
            <div class="w-6 h-6 bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7] rounded-full mr-6"></div>
            <p>GitHub</p>
        </div>
        <div class="flex items-center">
            <div class="w-6 h-6 bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7] rounded-full mr-6"></div>
            <p>Gitlab</p>
        </div>
        <div class="flex items-center">
            <div class="w-6 h-6 bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7] rounded-full mr-6"></div>
            <p>Postmen</p>
        </div>
        <div class="flex items-center">
            <div class="w-6 h-6 bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7] rounded-full mr-6"></div>
            <p>MongoDB</p>
        </div>
    </div>
</template>

<script>
export default {
    name: "TechnologiesPart",
    data() {
        return {
            technologiesData: [
                {
                    name: "HTML",
                    level: "Advanced",
                    percentage: "w-4/5"
                },
                {
                    name: "CSS, Tailwind & Bootstrap",
                    level: "Advanced",
                    percentage: "w-4/5"
                },
                {
                    name: "JavaScript, JQuery",
                    level: "Advanced",
                    percentage: "w-4/5"
                },
                {
                    name: "Vue",
                    level: "Advanced",
                    percentage: "w-4/5"
                },
                {
                    name: "Nuxt",
                    level: "Intermidiate",
                    percentage: "w-2/3"
                },
                {
                    name: "React",
                    level: "Beginer",
                    percentage: "w-1/2"
                },
            ]
        }
    }
}
</script>