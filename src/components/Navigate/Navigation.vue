<template>
  <header>
    <nav class="flex items-center justify-between flex-wrap bg-blue-500 p-6">
      <div class="flex items-center flex-shrink-0 text-white mr-6">
        <svg
          class="fill-current h-8 w-8 mr-2"
          width="54"
          height="54"
          viewBox="0 0 54 54"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M13.5 22.1c1.8-7.2 6.3-10.8 13.5-10.8 10.8 0 12.15 8.1 17.55 9.45 3.6.9 6.75-.45 9.45-4.05-1.8 7.2-6.3 10.8-13.5 10.8-10.8 0-12.15-8.1-17.55-9.45-3.6-.9-6.75.45-9.45 4.05zM0 38.3c1.8-7.2 6.3-10.8 13.5-10.8 10.8 0 12.15 8.1 17.55 9.45 3.6.9 6.75-.45 9.45-4.05-1.8 7.2-6.3 10.8-13.5 10.8-10.8 0-12.15-8.1-17.55-9.45-3.6-.9-6.75.45-9.45 4.05z"
          />
        </svg>
        <span class="font-semibold text-xl tracking-tight">Gemadept</span>
      </div>
      <div class="block lg:hidden">
        <button
          class="flex items-center px-3 py-2 border rounded text-white-200 border-white-800 hover:text-white hover:border-white"
        >
          <svg
            class="fill-current h-3 w-3"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <title>Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
          </svg>
        </button>
      </div>
      <div class="w-full block flex-grow lg:flex lg:items-center lg:w-auto">
        <div class="text-base text-white lg:flex-grow flex lg:justify-start">
          <div
            class="block lg:inline-block lg:mt-0 lg:px-20 text-white-800 hover:text-white hover:border-white"
          >
            {{ role.toUpperCase() }}
          </div>
        </div>

        <div class="text-base text-white lg:flex-grow flex lg:justify-end">
          <a
            href="#responsive-header"
            class="block lg:border-r-2 mt-4 mr-2 lg:inline-block lg:mt-0 lg:px-20 text-white-800 hover:text-white hover:border-white"
          >
            Employee Management
          </a>
          <a
            href="#responsive-header"
            class="block mt-4 lg:inline-block lg:border-r-2 mr-2 lg:mt-0 lg:px-20 text-white-800 hover:text-white"
          >
            Recruitment
          </a>
          <a
            href="#responsive-header"
            class="block mt-4 lg:inline-block lg:mt-0 lg:px-20 text-white-800 hover:text-white"
          >
            Report and Analysis
          </a>
        </div>
        <div>
          <button
            @click="handleLogout"
            class="inline-block text-xl px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-white-500 mt-4 lg:mt-0"
          >
            Log Out
          </button>
        </div>
      </div>
    </nav>
    <div>
      <img
        src="../Navigate/image.png"
        alt=""
        width="100%"
        height="80%"
        class=""
      />
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      role: "",
    };
  },

  methods: {
    handleLogout() {
      localStorage.removeItem("accessToken");
      this.$router.push("/");
    },
  },
  created() {
    this.email = localStorage.getItem("email");
    this.role = localStorage.getItem("role");
  },
};
</script>

<style></style>
