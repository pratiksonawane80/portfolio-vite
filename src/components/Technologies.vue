<template>
    <section ref="techSection">
        <h2 class="md:text-[46px] text-2xl font-semibold pt-16 pb-10">Technologies</h2>
        <div v-for="(skill, i) in technologiesData" :key="i">
            <div class="flex justify-between md:mt-12 mt-8">
                <p class="md:text-3xl text-md font-semibold">{{ skill.name }}</p>
                <p class="md:text-lg text-md font-semibold">{{ skill.level }}</p>
            </div>
            <!-- Progress bar -->
            <div class="h-4 rounded-3xl bg-[#162950] md:mt-8 mt-4 overflow-hidden">
                <div class="h-4 rounded-3xl bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7] transition-all duration-1000 ease-out"
                    :class="isVisible ? skill.percentage : 'w-0'"></div>
            </div>
        </div>

        <h2 class="md:text-[46px] text-2xl font-semibold mt-20 mb-10">Additional Technologies & Skills</h2>
        <div class="grid md:grid-cols-3 grid-cols-2 md:text-3xl text-md gap-6">
            <div v-for="extra in extraSkills" :key="extra" class="flex items-center">
                <div class="w-6 h-6 bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7] rounded-full mr-6"></div>
                <span>{{ extra }}</span>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: "TechnologiesPart",
    data() {
        return {
            isVisible: false,
            technologiesData: [
                { name: "HTML", level: "Advanced", percentage: "w-4/5" },
                { name: "CSS, Tailwind & Bootstrap", level: "Advanced", percentage: "w-4/5" },
                { name: "JavaScript, JQuery", level: "Advanced", percentage: "w-full" },
                { name: "Vue.js, React.js, Svelt", level: "Advanced", percentage: "w-4/5" },
                { name: "Node.js, Express.js", level: "Intermediate", percentage: "w-4/5" },
                { name: "Java, Spring Boot", level: "Intermediate", percentage: "w-3/5" },
                { name: "MySQL, PostGress", level: "Intermediate", percentage: "w-3/5" }
            ],
            extraSkills: ["Git", "GitHub", "Postman", "MongoDB", "Supabase"]
        };
    },
    mounted() {
        const observer = new IntersectionObserver(
            entries => {
                if (entries[0].isIntersecting) {
                    this.isVisible = true;
                    observer.disconnect(); // animate only once
                }
            },
            { threshold: 0.2 }
        );
        observer.observe(this.$refs.techSection);
    }
};
</script>
