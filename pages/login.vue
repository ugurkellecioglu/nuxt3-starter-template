<script setup lang="ts">
definePageMeta({ auth: false })
const { signIn } = useSession()
const loginForm = reactive({
  email: "",
  password: "",
})
const rememberMe = ref(false)

const login = async () => {
  try {
    await signIn("credentials", {
      email: loginForm.email,
      password: loginForm.password,
      rememberMe: rememberMe.value,
    }).then((res) => {
      console.log("res", res)
      useRouter().push("/")
    })
  } catch (error) {
    console.log(error)
  }
}
</script>
<template>
  <div>
    <div id="login-page">
      <div class="max-w-6xl relative z-10 m-auto px-6 lg:mt-16">
        <div
          class="grid md:grid-cols-2 lg:grid-cols-2 items-center login-section"
        >
          <div
            class="bg-white rounded-lg p-10 sm:m-auto md:m-auto lg:m-0 dark:bg-gray-800 dark:text-gray-300"
            style="border: solid 1px #caced0; min-height: 524px"
          >
            <div class="sm:w-full text-left m-auto lg:m-0">
              <h1 class="text-3xl md:text-4xl font-bold mb-3">
                Log in to your account
              </h1>
              <p class="mb-10">
                Not a member yet?
                <NuxtLink to="/register" class="no-underline tw-blue"
                  >Get started free now!</NuxtLink
                >
              </p>
              <div class="w-full">
                <div id="login-form">
                  <div>
                    <label
                      for="email"
                      class="block text-sm font-medium leading-8 text-gray-700 dark:text-gray-300"
                    >
                      Email address
                    </label>
                    <div class="mt-1 rounded-md">
                      <input
                        id="email"
                        v-model="loginForm.email"
                        type="email"
                        placeholder="Email"
                        name="email"
                        autofocus="true"
                        required="true"
                        class="appearance-none block w-full px-3 py-2 border border-gray-300 rounded-md placeholder-gray-400 focus:outline-none focus:shadow-outline-blue focus:border-blue-300 transition duration-150 ease-in-out sm:text-sm sm:leading-5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-gray-300"
                      />
                    </div>
                  </div>

                  <div class="mt-2">
                    <label
                      for="password"
                      class="block text-sm font-medium leading-8 text-gray-700 dark:text-gray-300"
                    >
                      Password
                    </label>
                    <div class="mt-1 rounded-md">
                      <input
                        type="password"
                        placeholder="Password"
                        name="password"
                        required="true"
                        v-model="loginForm.password"
                        class="appearance-none block w-full px-3 py-2 border border-gray-300 rounded-md placeholder-gray-400 focus:outline-none focus:shadow-outline-blue focus:border-blue-300 transition duration-150 ease-in-out sm:text-sm sm:leading-5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-gray-300"
                      />
                    </div>
                  </div>

                  <div class="mt-2 flex flex-col md:flex-row justify-between">
                    <div class="flex items-center">
                      <input
                        id="remember-me"
                        type="checkbox"
                        v-model="rememberMe"
                        class="form-checkbox h-4 w-4 tw-blue transition duration-150 ease-in-out"
                      />
                      <label
                        for="remember-me"
                        class="ml-2 block text-sm leading-5 text-gray-900 dark:text-gray-300"
                      >
                        Remember me
                      </label>
                    </div>

                    <div class="text-sm leading-5 mt-4 md:mt-0">
                      <NuxtLink
                        to="/forgot-password"
                        class="font-medium tw-blue focus:outline-none no-underline transition ease-in-out duration-150 dark:text-gray-300"
                      >
                        Forgot password?
                      </NuxtLink>
                    </div>
                  </div>

                  <div class="mt-10">
                    <span class="block w-full rounded-md">
                      <button
                        @click="login"
                        class="w-full flex justify-center py-2 px-4 border border-transparent text-md font-medium rounded-md text-white bg-tailwind-blue focus:outline-none focus:shadow-outline-indigo transition duration-150 ease-in-out dark:bg-gray-700"
                      >
                        Log in
                      </button>
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div
            class="text-center pt-10 md:pt-0 lg:pt-0 m-auto md:m-0 lg:m-0 hidden md:block lg:block"
          >
            <img
              class="rounded-lg md:ml-4 lg:ml-4"
              style="height: 524px"
              src="https://images.unsplash.com/photo-1622880474994-dbf749088e8d?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=387&q=80"
              alt="Ladybug on a leaf"
            />
          </div>
        </div>
      </div>
      <div id="bg-login-wind"></div>
    </div>
  </div>
</template>

<style scoped></style>
