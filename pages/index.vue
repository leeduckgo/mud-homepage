<template>
  <div class="flex flex-col w-content mx-auto pt-9">
    <div class="header h-16 flex justify-between items-center">
      <div class="flex items-center space-x-3">
        <img src="/img/logo.png" alt="logo" class="h-12" />
        <p class="text-xl font-minecraft">- rootMUD -</p>
      </div>
      <div class="links flex items-center space-x-5 text-black-1 dark:text-white font-['Poppins'] text-[17px]">
        <a href="https://x.com/root_mud" target="_blank">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="#1DA1F2" viewBox="0 0 24 24">
            <path
              d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z" />
          </svg>
        </a>
        <div class="flex justify-center ml-2" @click="toggleColorMode">
          <input type="checkbox" name="light-switch" class="light-switch sr-only" />
          <label
            class="relative h-[30px] p-[3px] bg-[#F0F2F5] dark:bg-[#2C2C2C] rounded-full after:content-[''] after:transition-transform after:duration-500 after:absolute after:dark:translate-x-full after:w-6 after:h-6 after:p-[6px] after:rounded-full after:bg-gradient-to-r after:from-[#439DFF] after:to-[#6052FF] flex items-center cursor-pointer select-none"
            for="light-switch">
            <img class="m-[6px] z-20 w-3 h-3" src="~/assets/svg/light-mode.svg" alt="light-mode">
            <img class="m-[6px] z-20 w-3 h-3" src="~/assets/svg/dark-mode.svg" alt="dark-mode">
            <span class="sr-only">Switch to light / dark version</span>
          </label>
        </div>
      </div>
    </div>
    <div class="slogon mt-12 flex justify-between items-center">
      <div class="flex flex-col space-y-12">
        <div class="texts flex flex-col space-y-6">
          <div class="titles flex flex-col space-y-9">
            <div class="flex flex-col space-y-4 text-black-1 dark:text-white">
              <span class="w-[600px] text-[32px] leading-none font-minecraft font-medium tracking-[0.6px]">MUD Space based
                on AI & Web3</span>
            </div>

          </div>

          <div class="flex items-center space-x-2 text-third-gray dark:text-gray-4 text-[16px]">
            <span>
              <p>rootMUD is an AI-powered text-based virtual community with the following features:</p>
              <p>* Use BRC20 as login token</p>
              <p>* All elements of the community, such as maps, etc., are governed through DAO</p>
              <p>* All components in the community are pluggable to fully unleash the potential of Developer GC</p>
              <p>* User data and item data are stored on the blockchain, enabling data to be used across games</p>
            </span>
          </div>
        </div>
        <div class="buttons flex items-center space-x-8">
          <template v-for="button in buttons" :key="button">
            <TheButton :text="button.text" :uppercase="true" :high="true" :colored-border="button.coloredBorder"
              :change-text="true" />
          </template>
        </div>
      </div>
      <img class="w-[568px]" src="/img/mud.png" alt="rootMUD">
    </div>
    <div class="mt-40 mx-auto w-[1160px] flex flex-col items-center space-y-[142px]">
      <div class="w-full flex justify-start items-center space-x-60">
        <div class="w-[555px] flex flex-col space-y-6 items-start">
          <table class="w-full text-[16px] text-second-gray dark:text-white font-['Poppins']">
            <tr>
              <td>Week 0x01. Launch MUD Space</td>
              <td>[----] 0%</td>
            </tr>
            <tr>
              <td>Week 0x02. Launch On-Chain Ascii Pet Module</td>
              <td>[----] 0%</td>
            </tr>
            <tr>
              <td>Week 0x03. Launch On-Chain Ascii Pet 2.0 with AI abilities</td>
              <td>[----] 0%</td>
            </tr>
            <tr>
              <td>Week 0x04. Launch rootMUD v1.0.0</td>
              <td>[----] 0%</td>
            </tr>
          </table>
        </div>
        <div class="title text-black-2 dark:text-white text-[40px] font-['Poppins'] font-semibold font-minecraft">ROAD MAP
        </div>
      </div>
    </div>

    <div class="footer mt-60 pb-24 flex flex-col space-y-3">
      <LinearLine />
      <div class="flex flex-col text-third-gray dark:text-white font-['Poppins'] text-[12px]">
        <div class="flex items-center">
          <span v-for="text in footerTexts2" :key="`second-${text}`">{{ text }}</span>
        </div>
        <div class="flex items-center">
          <span v-for="text in footerTexts3" :key="`second-${text}`">{{ text }}</span>
        </div>
        <br>
        <div class="flex justify-between items-center">
          <span v-for="text in footerTexts" :key="`first-${text}`">{{ text }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const links = [

]
const buttons = [
  {
    text: 'MINT BRC20',
    coloredBorder: true,
  },
  {
    text: 'READ DOCS',
    coloredBorder: false,
  },
]
const footerTexts = [
  'Copyright © 2023 rootMUD. All rights reserved.',
  'Terms of Use & Privacy Policy'
]

const footerTexts2 = [
  'rootMUD is a community fair engraving project where community developers voluntarily participate in technology development and community operations out of interest. ',
]
const footerTexts3 = [
  'Community developers are not responsible for the value or market performance of the token itself, as the price of a token is typically determined by market supply and demand and investor behavior.',
]
// 'rootMUD is a community fair engraving project where community developers voluntarily participate in technology development and community operations out of interest. Community developers are not responsible for the value or market performance of the token itself, as the price of a token is typically determined by market supply and demand and investor behavior.'

const colorMode = useColorMode()
const toggleColorMode = () => {
  if (colorMode.preference === 'dark') {
    colorMode.preference = 'light'
  } else {
    colorMode.preference = 'dark'
  }
}

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  })
}
</script>

<style scoped></style>