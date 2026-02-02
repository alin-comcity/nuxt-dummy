<template>
  <section class="body-font relative text-gray-600 h-screen">
    <div class="absolute inset-0 bg-gray-300">
      <iframe width="100%" height="100%" frameborder="0" marginheight="0" marginwidth="0" title="map" scrolling="no" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d7304.442158746845!2d90.3814588160403!3d23.73949446292245!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3755b91aab95a5ef%3A0xad8b0e10a93b67a2!2sComputer%20City%20Technologies%20Ltd!5e0!3m2!1sen!2sbd!4v1712468216580!5m2!1sen!2sbd"
      ></iframe>
    </div>
    
    <div class="container mx-auto flex px-5 py-24">
      <form @submit.prevent="sendMail" class="relative z-10 mt-10 flex w-full flex-col rounded-lg bg-white p-8 shadow-md dark:bg-gray-700 md:ml-auto md:mt-0 md:w-1/2 lg:w-1/3">
        <h2 class="title-font mb-1 text-lg font-medium text-gray-900 dark:text-white">Feedback</h2>
        <div class="relative mb-4">
          <label for="email" class="text-sm leading-7 text-gray-600 dark:text-white">Email</label>
          <input type="email" id="email" v-model="email" name="email" class="w-full rounded border border-gray-300 bg-white px-3 py-1 text-base leading-8 text-gray-700 outline-none transition-colors duration-200 ease-in-out focus:border-indigo-500 focus:ring-2 focus:ring-indigo-200"/>
        </div>
        
        <div class="relative mb-4">
          <label for="message" class="text-sm leading-7 text-gray-600 dark:text-white">Message</label>
          <textarea id="message" v-model="message" name="message" class="h-32 w-full resize-none rounded border border-gray-300 bg-white px-3 py-1 text-base leading-6 text-gray-700 outline-none transition-colors duration-200 ease-in-out focus:border-indigo-500 focus:ring-2 focus:ring-indigo-200"></textarea>
        </div>

        <button v-if="sendButton"
          class="rounded border-0 bg-lime-500 px-6 py-2 text-lg text-white focus:outline-none">
          {{buttonName}}
        </button>

        <button v-else disabled
          class="rounded border-0 bg-gray-800 px-6 py-2 text-lg text-white">
          {{buttonName}}
        </button>
      </form>
    </div>
  </section>


</template>

<script setup>
const email = ref('');
const message = ref('');
const sendButton = ref(true);
const buttonName = ref('Send');

const sendMail = async function(){
  await $fetch('https://formspree.io/f/xyzegbpk', {
    method: 'POST',
    body: {
      email : email.value,
      message : message.value
    },
    headers: {
          'Accept': 'application/json'
    },
  })

  // after sending the email
  email.value = '';
  message.value = '';
  sendButton.value = false; 
  buttonName.value = 'Sucess';
}
</script>
