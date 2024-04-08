<template>
    <div v-if="openModal" class="bg-[#6978D1]/50 w-full h-full text-yellow-700 z-[99] top-0 left-0 fixed">
        <div class="max-w-10xl h-screen bg-[#6978D1] bg-opacity-20  mx-auto left-0 right-0 absolute z-[999] p-10 ">
            <div class="bg-light-blue h-full overflow-y-auto px-6 py-10 text-black rounded relative">
                <!-- <div class="right-3 text-end text-2xl text-white cursor-pointer mr-2 mt-[-15px]" @click="closeModal">
                    X
                </div> -->
                <h1
                    class="text-center font-heebo xl:text-4xl text-2xl font-bold uppercase bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7] text-transparent bg-clip-text">
                    {{ companyData.name }}
                </h1>

                <div class="max-w-4xl mx-auto xl:mt-16 mt-8">
                    <div class="md:flex justify-between">
                        <div class="md:w-2/4">
                            <img :src="companyData.image" alt="img">
                        </div>
                        <div>
                            <ul class="mt-8 md:ml-4 ml-0 xl:text-xl text-base">
                                <div class="flex items-center gap-2 my-4">
                                    <h2 class="">Software Developer</h2>
                                </div>
                                <div class="flex items-center gap-2 my-4">
                                    <h2 class="">{{ companyData.role }}</h2>
                                </div>
                                <div class="flex gap-2 my-2">
                                    <h2 class="">{{ companyData.joiningDate }}</h2>
                                    <h2 class="">to</h2>
                                    <h2 class="">{{ companyData.lastDate }}</h2>
                                </div>
                            </ul>
                        </div>

                    </div>

                    <div class="mt-16 xl:min-w-[60rem]">
                        <h2 class="xl:text-2xl text-lg mt-12 font-monster">
                            Roles & Responsibilities
                        </h2>

                        <ul class="mt-6 list-disc">
                            <template v-for="(role, ind) in companyData.resp" :key="ind">
                                <li class="mt-6 text-[#929EB0]">
                                    {{ role }}
                                </li>
                            </template>
                        </ul>
                        <div class="mt-6 flex justify-center">
                            <button @click="closeModal"
                                class="rounded-[40px] p-2 w-[250px] text-lg bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7]">
                                Close
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import FloatImg from "../assets/floatImg.png"
import NeumannImg from "../assets/Image.png"
import SilohoImg from "../assets/silohoImg.png"
import NaestImg from "../assets/naestImg.png"
export default {

    name: "ModalComponent",
    props: ["companyData", "openModal", "previousScrollY"],
    data() {
        return {
            FloatImg,
            NeumannImg,
            SilohoImg,
            NaestImg
        }
    },
    methods: {
        closeModal() {
            this.$emit("closeModal");
            document.body.style.overflow = 'auto';
            document.body.style.position = '';
            window.scrollTo(0, this.previousScrollY);
        }
    }

}
</script>

<style></style>