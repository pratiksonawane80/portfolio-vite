<template>
    <h2 class="md:text-[46px] text-2xl font-semibold pt-16 mb-10">
        Overview
    </h2>
    <div class="flex justify-between flex-wrap ">
        <div v-for="(data, ind) in detailInfo" :key="data" class="flex md:block relative md:static md:w-1/4">
            <div class="md:text-3xl text-xl font-semibold w-[20%] md:w-auto">{{ data.year }}</div>
            <div class="flex h-1 justify-between bg-white md:my-8 items-center last:w-0 absolute md:static top-[10px] md:left-2 left-[16.6%]"
                id="" :class="ind === 3 ? 'w-[24.5px]' : 'w-auto'">
                <span class="w-6 h-6 bg-gradient-to-r from-[#945DD6] via-[#6978D1] to-[#13ADC7] rounded-full"></span>
            </div>
            <p class="md:px-2 pl-6 text-[#929EB0] md:text-lg text-md font-medium w-[80%] md:w-auto border-l-2  md:border-none border-white"
                :class="ind === 3 ? 'border-none' : ''">
                {{ data.text }}
            </p>
        </div>
    </div>
</template>

<script>
export default {
    name: "AboutMe",
    data() {
        return {
            detailInfo: [
                // {
                //     id: 1,
                //     year: 2021,
                //     text: "Graduated from Jawaharlal Nehru Engineering College as a Bachelor of Engineer. After that for 1 year focused on coding mainly the frontend technologies."
                // },
                {
                    id: 2,
                    year: 2022,
                    text: "In Dec - 2021 joined my first company as an Intern. There worked for 4 months. My role was to fullfill the clients requirement and improving the performance of the product."
                },
                {
                    id: 3,
                    year: 2022,
                    text: "In Apr - 2022 joined SILOHO as a Fontend Developer (Full-time). Here my responsibility was to build the product using reusable components, improving the SEO of product using SSR and making pixel perfect design."
                },
                {
                    id: 4,
                    year: 2023,
                    text: "In Jan - 2023 joined Float Enterprises Pvt. Ltd. as a Software Developer (Frontend Technologies). My contribution is to take the requirement from product manager, divide the task in between team and work on modules with use of proper logic."
                },
                {
                    id: 4,
                    year: 2024,
                    text: "In Sept - 2024 Joined Hackett Group as a Full Stack Developer, led the development of a full-stack Procurement Tool integrated with SAP S/4HANA. Delivered a cross-platform mobile app for HBL and maintained React.js apps with Supabase backend, enhancing SAP functionality."
                },
            ]
        }
    }
}
</script>

<style>
.hideBorder:last-child {
    border: none;
}
</style>
