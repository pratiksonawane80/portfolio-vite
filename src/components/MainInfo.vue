<template>
    <div class="md:flex justify-between text-center md:text-left fade-in">
        <div class="lg:text-[60px] md:text-3xl text-2xl font-semibold md:mr-10 md:w-3/5 md:my-40 my-16">
            <h1
                class="bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7] inline-block text-transparent bg-clip-text lg:py-10 md:py-12 p-0 md:m-0 m-auto mb-2">
                Hi, this is {{ text }}
            </h1>
            <h3>Front End Developer</h3>
            <p class="text-lg font-medium text-[#929EB0] mt-6">
                Full Stack Software Developer with strong experience leading teams and delivering scalable web and
                mobile solutions. Skilled in cross-platform app development, building full-stack tools using Java Spring
                Boot, React.js, and Supabase, and enhancing legacy systems for improved performance and stability.
                Passionate about leveraging modern technologies and AI tools to accelerate development and create
                impactful products.
            </p>
            <a :href="resume" :download="pdfName" class="hidden md:block text-left md:w-72 w-56">
                <button
                    class="p-4 md:mt-14 mt-4 md:m-0 rounded-[60px] md:w-72 w-56 md:text-lg text-sm bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7]">
                    Download Resume
                </button>
            </a>
        </div>
        <div class="md:my-20 my-10">
            <div
                class="md:w-[532px] md:h-[532px] w-[366px] h-[366px] border rounded-full absolute bg-transparent md:right-[170px] right-48 md:mt-10 border-[#945DD6]">
            </div>
            <img src="../assets/display-pic.jpeg" alt="profile-pic" class="rounded-full border border-[#945DD6] z-10
                absolute lg:right-40 right-32 animated-bg md:w-[301px] w-[201px] md:h-[301px] h-[201px]">
            <img src="../assets/blueCircle.svg" alt="cirlce" class="md:mt-40 md:ml-20 ml-28 pt-12">
        </div>
        <a :href="resume" :download="pdfName" class="md:hidden text-center">
            <button
                class="p-4 mt-8 md:m-0 rounded-[60px] md:w-72 w-56 md:text-lg text-sm bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7]">
                Download Resume
            </button>
        </a>
    </div>
</template>

<script>
import resume from "../assets/resume.pdf"
export default {
    name: "MainInfo",
    data() {
        return {
            resume,
            pdfName: "Pratik Sonawane",
            name: "Pratik,", // Replace with the desired string
            text: "",
            current: 0,
            intervalId: null
        }
    },
    mounted() {
        this.startTextUpdate();
    },
    methods: {
        startTextUpdate() {

            this.intervalId = setInterval(() => {

                if (this.current < this.name.length) {
                    this.text += this.name[this.current];
                    this.current++;
                } else {
                    clearInterval(this.intervalId); // Clear the interval once the text is fully written
                }
            }, 200);
        }
    },
    beforeDestroy() {
        // Clear the interval when the component is destroyed to prevent memory leaks
        if (this.intervalId) {
            clearInterval(this.intervalId);
        }
    }
}
</script>

<style>
.animated-bg {
    filter: drop-shadow(0 0 10px #945DD6);
    animation: glow 1s alternate infinite
}

@keyframes glow {
    0% {
        filter: drop-shadow(0 0 5px #945DD6);
    }

    100% {
        filter: drop-shadow(0 0 15px #945DD6);
    }
}
</style>