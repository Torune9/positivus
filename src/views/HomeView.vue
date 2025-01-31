<template>
     <MainLayout>
          <template #content>
               <!-- services -->
               <section class="h-20">
                    <div class="flex flex-row gap-x-28 items-center h-10">
                         <h1 class="bg-lime-300 font-medium text-2xl px-2 h-full rounded flex items-center">Services
                         </h1>
                         <p class=" w-xl text-sm">At our digital marketing agency, we offer a range of services to help
                              businesses grow and succeed online. These services include:</p>
                    </div>
               </section>
               <!-- service -->
               <section class="mt-12 grid grid-cols-2 grid-flow-row gap-8">
                    <div v-for="(service, i) in services"
                         class="h-64 rounded-4xl grid grid-cols-2 grid-flow-row p-10 border-b-8 border"
                         :class="service.bg">
                         <div>
                              <h1 class="w-fit text-lg font-semibold rounded-sm px-1"
                                   :class="service.bgHead ? service.bgHead : 'bg-white'">{{ service.name }}</h1>
                              <h1 class="w-fit text-lg font-semibold rounded-sm px-1"
                                   :class="service.bgHead ? service.bgHead : 'bg-white'">{{ service.name2 }}</h1>
                         </div>
                         <div>
                              <img :src="service.image" alt="service-image" class="h-32">
                         </div>
                         <div class="flex flex-row gap-x-4 items-center hover:cursor-pointer">
                              <button class="-rotate-[30deg] rounded-full hover:cursor-pointer"
                                   :class="service.bgBtn ? service.bgBtn : 'text-white'">
                                   <font-awesome-icon icon="fa-solid fa-circle-arrow-right" size="2xl" />
                              </button>
                              <p :class="i == 2 || i == 5 ? 'text-white' : ''">Learn More</p>
                         </div>
                    </div>
               </section>
               <!-- CTA -->
               <section class="mt-42">
                    <div
                         class="bg-slate-200 h-80 rounded-4xl flex flex-row px-10 items-center box-border justify-between">
                         <div class="flex flex-col gap-6">
                              <h1 class="text-2xl font-medium">Let's make things happen</h1>
                              <p class="w-96">Contact us today to learn more about how our digital marketing services
                                   can help your business grow and succeed online.</p>
                              <button
                                   class="border w-fit bg-slate-950 p-3 px-4 rounded-lg text-white hover:bg-slate-900 transition-colors hover:cursor-pointer duration-300">Get
                                   your free proposal</button>
                         </div>
                         <div>
                              <img :src="cta" alt="cta-image" class=" ">
                         </div>
                    </div>
               </section>
               <!-- Cases -->
               <section class="mt-42 flex flex-col gap-y-20">
                    <div class="flex flex-row gap-x-28 items-center h-10">
                         <h1 class="bg-lime-300 font-medium text-2xl px-2 h-full flex items-center rounded-md">Case
                              Studies</h1>
                         <p class="w-[450px]">
                              Explore Real-Life Examples of Our Proven Digital Marketing Success through Our Case
                              Studies
                         </p>
                    </div>
                    <div class="bg-slate-950 grid grid-cols-3 h-64 rounded-4xl content-center">
                         <div class="text-white h-40 px-18 flex flex-col gap-y-5" v-for="(message, i) in caseStudies"
                              :class="i !== 0 ? 'border-l' : ''">
                              <p>{{ message.case }}</p>
                              <button
                                   class="flex flex-row gap-x-2 text-lime-300 w-fit hover:bg-lime-900 rounded-md transition-colors duration-300 hover:cursor-pointer">
                                   <p class="w-fit">Learn More</p>
                                   <span class="-rotate-[32deg]">
                                        <font-awesome-icon icon="fa-solid fa-arrow-right" />
                                   </span>
                              </button>
                         </div>
                    </div>
               </section>
               <!-- Working -->
               <section class="mt-42 flex flex-col gap-y-20">
                    <div class="flex flex-row gap-x-28 items-center h-10">
                         <h1 class="bg-lime-300 font-medium text-2xl px-2 h-full flex items-center rounded-md">Our
                              Working Process</h1>
                         <p class="w-64">
                              Step-by-Step Guide to Achieving Your Business Goals
                         </p>
                    </div>
                    <div class="flex flex-col gap-y-6">
                         <div class="border-b-5 border h-full rounded-3xl px-10" v-for="(work, i) in works"
                              :class="!i ? 'bg-lime-300' : 'bg-slate-200'" :key="i">
                              <div class="flex flex-row justify-between items-center h-28">
                                   <div class="flex flex-row items-center gap-x-6">
                                        <p class="text-6xl font-semibold">{{ '0' + (i + 1) }}</p>
                                        <h1 class="text-lg">{{ work.service }}</h1>
                                   </div>
                                   <button @click="toggleDesc(i)"
                                        class="border rounded-full h-10 w-10 flex justify-center items-center hover:cursor-pointer hover:bg-slate-500 transition-colors duration-300">
                                        <font-awesome-icon
                                             :icon="activeIndex === i ? 'fa-solid fa-minus' : 'fa-solid fa-plus'"
                                             size="xl" />
                                   </button>
                              </div>
                              <p class="border-t py-12" v-if="activeIndex === i">{{ work.description }}</p>
                         </div>
                    </div>
               </section>
               <!-- Contact us -->
               <section class="mt-42 flex flex-col gap-y-20">
                    <div class="flex flex-row gap-x-28 items-center h-10">
                         <h1 class="bg-lime-300 font-medium text-2xl px-2 h-full flex items-center rounded-md">
                              Contact Us
                         </h1>
                         <p class="w-64">
                              Connect with Us: Let's Discuss Your Digital Marketing Needs
                         </p>
                    </div>
                    <div class="bg-slate-100 rounded-4xl flex flex-row p-20 relative overflow-hidden">
                         <form action="#" class="w-[500px] flex flex-col gap-y-5">
                              <div class="flex flex-row gap-x-10">
                                   <div class="flex items-center space-x-2">
                                        <label for="say-hi" class="flex items-center space-x-2 cursor-pointer">
                                             <input type="radio" name="choice" id="say-hi" class="peer hidden">
                                             <div
                                                  class="w-6 h-6 border rounded-full flex items-center justify-center relative before:w-3 before:h-3 before:rounded-full before:bg-transparent before:content-[''] peer-checked:before:bg-lime-300">
                                             </div>
                                             <span class="text-gray-700">Say Hi</span>
                                        </label>
                                   </div>
                                   <div class="flex items-center space-x-2">
                                        <label for="get-quote" class="flex items-center space-x-2 cursor-pointer">
                                             <input type="radio" name="choice" id="get-quote" class="peer hidden">
                                             <div
                                                  class="w-6 h-6 border rounded-full flex items-center justify-center relative before:w-3 before:h-3 before:rounded-full before:bg-transparent before:content-[''] peer-checked:before:bg-lime-300">
                                             </div>
                                             <span class="text-gray-700">Get Quote</span>
                                        </label>
                                   </div>
                              </div>

                              <div class="flex flex-col gap-y-2">
                                   <label for="name">Name</label>
                                   <input class="border h-10 text-sm pl-4 rounded-xl bg-white" type="text" name="name" id="name" placeholder="Name">
                              </div>
                              <div class="flex flex-col gap-y-2">
                                   <label for="email">Email*</label>
                                   <input class="border h-10 text-sm pl-4 rounded-xl bg-white" type="text" name="email" id="email" placeholder="Email">
                              </div>
                              <div class="flex flex-col gap-y-2">
                                   <label for="message">Message*</label>
                                   <textarea name="message" id="message"
                                        class="border h-36 rounded-xl bg-white pl-4" placeholder="Message"></textarea>
                              </div>
                              <button class="bg-slate-900 p-3 text-white rounded-lg">
                                   Send Message
                              </button>
                         </form>
                         <figure class="absolute -right-60 flex justify-center">
                              <img :src="ctu" alt="contact-us-illustrator" width="500">
                         </figure>
                    </div>
               </section>
          </template>
     </MainLayout>
</template>

<script setup>
import MainLayout from '@/layouts/MainLayout.vue';

import at from '@/assets/images/service-image/at.png'
import cc from '@/assets/images/service-image/cc.png'
import em from '@/assets/images/service-image/em.png'
import ppc from '@/assets/images/service-image/ppc.png'
import se from '@/assets/images/service-image/se.png'
import smm from '@/assets/images/service-image/smm.png'
import cta from '@/assets/images/cta.png'
import ctu from '@/assets/images/ctu.png'

import { ref } from 'vue';

const services = [
     {
          name: 'Search engine',
          name2: 'optimization',
          bg: "bg-slate-200",
          image: se,
          bgHead: "bg-lime-300",
          bgBtn: "bg-lime-300 text-slate-900"
     },
     {
          name: 'Pay-per-click',
          name2: ' advertising',
          bg: "bg-lime-300",
          image: ppc,
          bgBtn: "text-slate-900"
     },
     {
          name: 'Social Media',
          name2: 'Marketing',
          bg: "bg-slate-900",
          image: smm,

     },
     {
          name: 'Email',
          name2: ' Marketing',
          bg: "bg-slate-200",
          image: em,
          bgHead: "bg-lime-300",
          bgBtn: "bg-lime-300 text-slate-900"
     },
     {
          name: 'Content',
          name2: 'Creation',
          bg: "bg-lime-300",
          image: cc,
          bgBtn: "bg-lime-300 text-slate-900"
     },
     {
          name: 'Analitics and',
          name2: 'Tracking',
          bg: "bg-slate-900",
          image: at,
          bgHead: "bg-lime-300 text-slate-900",
     },
]

const caseStudies = [
     {
          case: 'For a local restaurant, we implemented a targeted PPC campaign that resulted in a 50% increase in website traffic and a 25% increase in sales.'
     },
     {
          case: 'For a B2B software company, we developed an SEO strategy that resulted in a first page ranking for key keywords and a 200% increase in organic traffic.'
     },
     {
          case: 'For a national retail chain, we created a social media marketing campaign that increased followers by 25% and generated a 20% increase in online sales.'
     }
]

const works = [
     {
          service: 'Consultation',
          description: 'During the initial consultation, we will discuss your business goals and objectives, target audience, and current marketing efforts. This will allow us to understand your needs and tailor our services to best fit your requirements.'
     },
     {
          service: 'Research and Strategy Development',
          description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tempora nisi inventore eaque delectus distinctio consectetur enim voluptas itaque aliquam repudiandae!'
     },
     {
          service: 'Implementation',
          description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tempora nisi inventore eaque delectus distinctio consectetur enim voluptas itaque aliquam repudiandae!'
     },
     {
          service: 'Monitoring and Optimization',
          description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tempora nisi inventore eaque delectus distinctio consectetur enim voluptas itaque aliquam repudiandae!'
     },
     {
          service: 'Reporting and Communication',
          description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tempora nisi inventore eaque delectus distinctio consectetur enim voluptas itaque aliquam repudiandae!'
     },
     {
          service: 'Continual Improvement',
          description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tempora nisi inventore eaque delectus distinctio consectetur enim voluptas itaque aliquam repudiandae!'
     },
]


const activeIndex = ref(null);

const toggleDesc = (index) => {
     activeIndex.value = activeIndex.value === index ? null : index;
};

</script>

<style></style>