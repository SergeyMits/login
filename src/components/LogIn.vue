<script setup>
import { ref } from "vue";

const error = ref(false);
</script>
<template>
  <div class="flex">
    <div class="mb-6 p-4">
      <div
        class="bg-base-100 rounded-lg p-4 shadow-lg w-auto flex flex-col gap-3"
        :class="{ 'rotate-enter-active': error }"
      >
        <input type="text" class="input input-bordered" value="Usermane" />
        <input type="Password" class="input input-bordered" value="Password" />
        <button
          class="btn bg-emerald-300 text-slate-800 hover:bg-emerald-500"
          @click="error = !error"
        >
          Log In
        </button>
        <Transition name="shake">
          <div class="alert alert-error shadow-lg rounded-lg" v-if="error">
            <div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="stroke-current flex-shrink-0 h-6 w-6"
                fill="none"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z"
                />
              </svg>
              <span>Error! Login failed .</span>
            </div>
          </div>
        </Transition>
      </div>
    </div>
  </div>
</template>

<style>
.alert-enter-from,
.alert-leave-to {
  opacity: 0;
}

.alert-enter-from {
  height: 0;
}

.alert-enter-active,
.alert-leave-active {
  transition: 0.3s ease;
}

.shake-enter-active,
.shake-leave-active {
  animation: shake 0.3s;
}

@keyframes shake {
  0%,
  100% {
    transform: translateX(0);
  }
  25% {
    transform: translateX(10px);
  }
  75% {
    transform: translateX(-10px);
  }
}

.rotate-enter-active {
  animation: rotate 0.2s;
}

@keyframes rotate {
  0%,
  100% {
    transform: rotate(0);
  }
  20% {
    transform: rotate(3deg);
  }
  40% {
    transform: rotate(-3deg);
  }
  60% {
    transform: rotate(3deg);
  }
  80% {
    transform: rotate(-3deg);
  }
}
</style>
