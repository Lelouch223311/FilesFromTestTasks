<template>
    <header>

        <nav class="border-gray-200 bg-gray-50 dark:bg-gray-800 dark:border-gray-700">
            <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
                <!-- <span class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white">header</span> -->
                <div class="hidden w-full md:block md:w-auto" id="navbar-solid-bg">
                    <ul
                        class="flex flex-col font-medium mt-4 rounded-lg bg-gray-50 md:space-x-8 rtl:space-x-reverse md:flex-row md:mt-0 md:border-0 md:bg-transparent dark:bg-gray-800 md:dark:bg-transparent dark:border-gray-700">
                        <li>
                            <NuxtLink to="/"
                                class="block py-2 px-3 md:p-0 text-white bg-blue-700 rounded md:bg-transparent md:text-blue-700 md:dark:text-blue-500 dark:bg-blue-600 md:dark:bg-transparent"
                                aria-current="page">Home</NuxtLink>
                        </li>
                        <li>
                            <NuxtLink to="/soobr"
                                class="block py-2 px-3 md:p-0 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">
                                Сообразительность</NuxtLink>
                        </li>
                        <li>
                            <NuxtLink to="/programm"
                                class="block py-2 px-3 md:p-0 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">
                                Программирование</NuxtLink>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>

    </header>
    <div>
        <slot />
    </div>
</template>

<script>
export default {
    setup() {


        return {}
    }
}
</script>

<style>
* {
    padding: 0;
    margin: 0;
    text-decoration: none;
    user-select: none;
}

nav {
    display: flex;
    padding: 10px;
}

ul {
    list-style-type: none;
}
h2,h1{
    padding:15px;
}

.your-custom-active-link{
    color:red;
}

.your-custom-exact-active-link {
   color: blue;
  }

</style>