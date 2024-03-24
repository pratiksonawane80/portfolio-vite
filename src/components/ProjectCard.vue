<template>
    <div class="flex flex-wrap justify-center">
        <div v-for="data in companyData" :key="data.id" class="md:p-6 p-4">
            <div
                class="border rounded-md border-[#13ADC7] md:w-[480px] w-[320px] p-6 flex flex-col md:h-[600px] h-[500px] relative">
                <img :src="data.image" alt="" class="md:h-[220px] h-[180px]">
                <h3 class="py-4 md:text-3xl text-md font-semibold">{{ data.name }}</h3>
                <p class="md:text-lg text-sm font-medium text-[#929EB0]">{{ data.description }}</p>
                <div class="mt-4 flex justify-center">
                    <button @click="onClickDetails(data)"
                        class="p-4 rounded-[60px] w-[250px] text-lg bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7] absolute bottom-7">
                        Details
                    </button>
                </div>
            </div>
        </div>
    </div>
    <DetailsModal :openModal="showDetails" :companyData="perticulatData" @closeModal="showDetails = false"/>
</template>

<script>
import FloatImg from "../assets/floatImg.png"
import NeumannImg from "../assets/Image.png"
import SilohoImg from "../assets/silohoImg.png"
import NaestImg from "../assets/naestImg.png"
import DetailsModal from "./DetailsModal.vue"
export default {
    components: {DetailsModal},
    data() {
        return {
            FloatImg,
            NeumannImg,
            SilohoImg,
            NaestImg,
            showDetails: false,
            perticulatData: null,
            companyData: [
                {
                    id: 1,
                    name: "Neumann Fornax",
                    description: "Service based company mainly working for US clients",
                    role: "Vue.js, Quasar, HTML",
                    joiningDate: "1st Dec 2021",
                    lastDate: "11th Apr 2022",
                    image: NeumannImg,
                    resp: [
                      "Participated in implementation of VUE.js library",
                      "Leveraged the power of Google Maps API to implement an intelligent address autofill feature across the project",
                      "Worked on responsive landing pages with the use of programming languages (HTML, CSS, JavaScript)",
                      "Tested and Debugged thousand's of lines of code",
                      "Implemented front-end technical solutions to meet project requirements.",
                    ]
                },
                {
                    id: 2,
                    name: "Siloho: Simply Lovable Homes",
                    description: "Making designer homes accessible at the click of a button with AI tech, award-winning interior designers and top-notch furniture-fittings partnerships.",
                    role: "Vue.js, Nuxt.js, HTML, SCSS",
                    joiningDate: "18th Apr 2022",
                    lastDate: "31st Dec 2022",
                    image: SilohoImg,
                    resp: [
                      "Developed E-commerce website for Home and Interior Design where we can customize and view Interior on Website.",
                      "Worked on Javascript/ Jquery for building an Internal tool for the organization which helps employees to store and access data easily.",
                      "Worked on SCSS, Bootstrap for developing responsive UI and creating attractive pages.",
                      "Developing functionality and interlinking of different components according to needs."
                    ]
                },
                {
                    id: 3,
                    name: "Float Enterprises Pvt. Ltd.",
                    description: "Float Care specializes in solutions within the healthcare industry and aims to be the leader in healthcare management software. From practice management to patient engagement, the software tackles many of the pain points in healthcare.",
                    role: "Vue.js, vue-bootstrap, MongoDB",
                    joiningDate: "9th Jan 2023",
                    lastDate: "Till Now",
                    image: FloatImg,
                    resp: [
                      "Implemented a user-friendly directory structure within the application, inspired by the familiar Windows Explorer interface. This feature allows users to easily navigate and manage folders.. By incorporating this directory-like functionality.",
                      "Build the helpdesk feature within my application which provides users with a convenient and accessible platform to seek assistance and support for any issues they may encounter while using the application.",
                      "I effectively managed a team of five individuals and successfully facilitated the process of gathering project requirements from the project manager.",
                      "Working with technologies such as Vue (with composition API), Tailwind CSS, Pinia, and Vue Bootstrap enabled me to deliver high-quality web applications."
                    ]
                },
                {
                    id: 4,
                    name: "Shiksha Sopan",
                    description: "Exam portal for students where students can perform time based exams . 22k students gave exams at a time.",
                    role: "React.js, TypeScript, Tailwind",
                    joiningDate: "7th Mar 2023",
                    lastDate: "27th Jul 2023",
                    image: NaestImg,
                    resp: [
                      "Exam portal for students where students can perform time based exams . Nearabout 22k students gave exams at a time.",
                      "Organization is holded by prof HC Verma (padmashree ). Worked on his requirements.",
                      "Worked as an individual contractor for this project.",
                      "Technology used - React , Typescript , Tailwind."
                    ]
                },
            ]
        }
    },
    methods: {
        onClickDetails(data) {
            this.perticulatData = data
            console.log('clicked');
            this.showDetails = true;
        }
    }
}
</script>