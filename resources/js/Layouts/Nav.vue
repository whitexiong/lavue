<script setup>
import {useStore} from 'vuex'
import {mdiThemeLightDark} from '@mdi/js'
import NavBarItem from '@/components/NavBarItem.vue'
import NavBarItemLabel from '@/components/NavBarItemLabel.vue'
import EasyWriteLogo from '@/components/EasyWriteLogo'
import stores from '../store'


const store = useStore()

const toggleLightDark = () => {
  stores.dispatch('darkMode')
}


</script>


<template>

  <div
      class="sticky bg-opacity-75 md:bg-opacity-50 top-0 z-40 w-full backdrop-blur flex-none transition-colors duration-500 lg:z-50 lg:border-b lg:border-gray-900/10 dark:border-gray-50/[0.06] bg-white supports-backdrop-blur:bg-white/95 dark:bg-gray-900/75">
    <div class="max-w-8xl mx-auto">
      <div class="py-4 border-b border-gray-900/10 lg:px-8 lg:border-0 dark:border-gray-300/10 px-4">
        <div class="relative flex items-center"><a class="mr-3 flex-none w-[2.0625rem] overflow-hidden md:w-auto"
                                                   href="/"><span class="sr-only"><font
            style="vertical-align: inherit;"><font style="vertical-align: inherit;">EasyWrite 主页</font></font></span>

          <easy-write-logo/>

        </a>

          <div id="docsearch"></div>

          <div class="relative hidden lg:flex items-center ml-auto">
            <nav class="text-sm leading-6 font-semibold text-gray-700 dark:text-gray-200">
              <ul class="flex space-x-8">
                <li><a class="hover:text-sky-500 dark:hover:text-sky-400" :href="route('home.login')"><font
                    style="vertical-align: inherit;"><font style="vertical-align: inherit;">登录</font></font></a>
                </li>
                <li><a
                    :href="route('home.register')"
                    class="hover:text-sky-500 dark:hover:text-sky-400"><span
                    style="vertical-align: inherit;"><font style="vertical-align: inherit;">注册</font></span></a>
                </li>

                <li>
                  <nav-bar-item
                      has-divider
                      is-desktop-icon-only
                      @click.prevent="toggleLightDark"
                  >
                    <nav-bar-item-label
                        :icon="mdiThemeLightDark"
                        label="Light/Dark"
                        is-desktop-icon-only
                    />

                  </nav-bar-item>
                </li>


              </ul>

            </nav>
            <div class="flex items-center border-l border-gray-200 ml-6 pl-6 dark:border-gray-800"><label
                class="sr-only" id="headlessui-listbox-label-3"><font style="vertical-align: inherit;"><font
                style="vertical-align: inherit;">主题</font></font></label>
              <button type="button" id="headlessui-listbox-button-4" aria-haspopup="true" aria-expanded="false"
                      aria-labelledby="headlessui-listbox-label-3 headlessui-listbox-button-4"><span
                  class="dark:hidden"><svg viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"
                                           stroke-linejoin="round" class="w-6 h-6"><path
                  d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z" class="stroke-gray-400 dark:stroke-gray-500"></path><path
                  d="M12 4v1M17.66 6.344l-.828.828M20.005 12.004h-1M17.66 17.664l-.828-.828M12 20.01V19M6.34 17.664l.835-.836M3.995 12.004h1.01M6 6l.835.836"
                  class="stroke-gray-400 dark:stroke-gray-500"></path></svg></span><span class="hidden dark:inline"><svg
                  viewBox="0 0 24 24" fill="none" class="w-6 h-6"><path fill-rule="evenodd" clip-rule="evenodd"
                                                                        d="M17.715 15.15A6.5 6.5 0 0 1 9 6.035C6.106 6.922 4 9.645 4 12.867c0 3.94 3.153 7.136 7.042 7.136 3.101 0 5.734-2.032 6.673-4.853Z"
                                                                        class="fill-transparent"></path><path
                  d="m17.715 15.15.95.316a1 1 0 0 0-1.445-1.185l.495.869ZM9 6.035l.846.534a1 1 0 0 0-1.14-1.49L9 6.035Zm8.221 8.246a5.47 5.47 0 0 1-2.72.718v2a7.47 7.47 0 0 0 3.71-.98l-.99-1.738Zm-2.72.718A5.5 5.5 0 0 1 9 9.5H7a7.5 7.5 0 0 0 7.5 7.5v-2ZM9 9.5c0-1.079.31-2.082.845-2.93L8.153 5.5A7.47 7.47 0 0 0 7 9.5h2Zm-4 3.368C5 10.089 6.815 7.75 9.292 6.99L8.706 5.08C5.397 6.094 3 9.201 3 12.867h2Zm6.042 6.136C7.718 19.003 5 16.268 5 12.867H3c0 4.48 3.588 8.136 8.042 8.136v-2Zm5.725-4.17c-.81 2.433-3.074 4.17-5.725 4.17v2c3.552 0 6.553-2.327 7.622-5.537l-1.897-.632Z"
                  class="fill-gray-400 dark:fill-gray-500"></path><path fill-rule="evenodd" clip-rule="evenodd"
                                                                        d="M17 3a1 1 0 0 1 1 1 2 2 0 0 0 2 2 1 1 0 1 1 0 2 2 2 0 0 0-2 2 1 1 0 1 1-2 0 2 2 0 0 0-2-2 1 1 0 1 1 0-2 2 2 0 0 0 2-2 1 1 0 0 1 1-1Z"
                                                                        class="fill-gray-400 dark:fill-gray-500"></path></svg></span>
              </button>
              <a href="https://github.com/tailwindlabs/tailwindcss"
                 class="ml-6 block text-gray-400 hover:text-gray-500 dark:hover:text-gray-300"><span
                  class="sr-only"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GitHub 上的 Tailwind CSS</font></font></span>
                <svg viewBox="0 0 16 16" class="w-5 h-5" fill="currentColor" aria-hidden="true">
                  <path
                      d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"></path>
                </svg>
              </a></div>
          </div>
          <button type="button"
                  class="ml-auto text-gray-500 w-8 h-8 -my-1 flex items-center justify-center hover:text-gray-600 lg:hidden dark:text-gray-400 dark:hover:text-gray-300">
            <span class="sr-only">Search</span>
            <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                 stroke-linejoin="round" aria-hidden="true">
              <path d="m19 19-3.5-3.5"></path>
              <circle cx="11" cy="11" r="6"></circle>
            </svg>
          </button>
          <div class="ml-2 -my-1 lg:hidden">
            <button type="button"
                    class="text-gray-500 w-8 h-8 flex items-center justify-center hover:text-gray-600 dark:text-gray-400 dark:hover:text-gray-300">
              <span class="sr-only">Navigation</span>
              <svg width="24" height="24" fill="none" aria-hidden="true">
                <path
                    d="M12 6v.01M12 12v.01M12 18v.01M12 7a1 1 0 1 1 0-2 1 1 0 0 1 0 2Zm0 6a1 1 0 1 1 0-2 1 1 0 0 1 0 2Zm0 6a1 1 0 1 1 0-2 1 1 0 0 1 0 2Z"
                    stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
              </svg>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>

import {defineComponent} from "vue";
import docsearch from '@docsearch/js';
import '@docsearch/css';
// import NavBarSearch from '@/components/NavBarItem.vue';


export default defineComponent({
  components: {
  },
  mounted() {
    docsearch({
      container: '#docsearch',
      appId: 'R2IYF7ETH7',
      apiKey: '599cec31baffa4868cae4e79f180729b',
      indexName: 'docsearch',
    });
  }

})

</script>