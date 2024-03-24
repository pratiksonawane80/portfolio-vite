<template>
    <h2 class="md:text-[46px] text-2xl md:py-16 md:pt-8 pt-14">Experience and Portfolio</h2>
    <div class="">
        <div class="p-6">
            <Project companyData="companyData" />
        </div>
    </div>
</template>

<script>
import Project from "./ProjectCard.vue"
export default {
    name: "TheProjects",
    components: { Project },
    data() {
        return {
            
        }
    }
}
</script>