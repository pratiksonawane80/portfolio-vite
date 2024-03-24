<template>
    <div class="hidden md:block fade-in">
        <div class="flex justify-between">
            <h3 class="text-3xl">P.S. Portfolio</h3>
            <ul class="flex justify-around text-lg">
                <li class="pr-4 cursor-pointer" @click="scrollToViewport('projects')">Projects</li>
                <li class="px-4 cursor-pointer" @click="scrollToViewport('technologies')">Technologies</li>
                <li class="pl-4 cursor-pointer" @click="scrollToViewport('aboutMe')">About me</li>
            </ul>
            <div class="flex">
                <a href="https://www.linkedin.com/in/pratiksonawane80/" target="_blank"><img src="../assets/linkdin.png" alt="linkdin" height="27" width="27" class="mx-4"></a>
                <a href="https://github.com/pratiksonawane80" target="_blank"><img src="../assets/github.png" alt="github" height="27" width="27" class="mx-4"></a>
            </div>
        </div>
    </div>

    <div class="md:hidden fade-in">
        <div class="flex justify-between">
            <h3 class="text-3xl">P.S. Portfolio</h3>
            <div class="flex">
                <a href="https://www.linkedin.com/in/pratiksonawane80/" target="_blank"><img src="../assets/linkdin.png"
                        alt="linkdin" height="27" width="27" class="mr-4"></a>
                <a href="https://github.com/pratiksonawane80" target="_blank"><img src="../assets/github.png" alt="github"
                        height="27" width="27" class="ml-4"></a>
            </div>
        </div>
        <ul class="flex justify-between text-sm mt-12">
            <li class="cursor-pointer" @click="scrollToViewport('projects')">Projects</li>
            <li class="cursor-pointer" @click="scrollToViewport('technologies')">Technologies</li>
            <li class="cursor-pointer" @click="scrollToViewport('aboutMe')">About me</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "TheNavabr",
    data() {
        return {
            name: "pratik"
        }
    },
    methods: {
        scrollToViewport(comp) {
            this.$emit('scrollToViewport', comp)
        }
    }
}
</script>