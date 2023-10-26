<template>
  <div>
    <div class="px-20 py-20">
      <div>
        <p class="pb-3">Enter Number</p>
        <div class="flex gap-5">
          <!-- Input -->
          <input
            class="border px-2 rounded-lg"
            v-model="quantity"
          />
          <button
            class="bg-indigo-600 px-5 py-2 rounded-lg text-white border border-blue-600"
            @click="addBoxes"
          >
            Submit
          </button>
        </div>
      </div>
      <div>
        <div class="flex gap-3 items-center">
          <p>Even Numbers</p>
          <p class="h-[10px] w-[10px] rounded-lg bg-orange-500"></p>
        </div>
        <div class="flex gap-3 items-center">
          <p>Odd Numbers</p>
          <p class="h-[10px] w-[10px] rounded-lg bg-red-700"></p>
        </div>
        <div class="flex gap-3 items-center">
          <p>Prime Numbers</p>
          <p class="h-[10px] w-[10px] rounded-lg bg-green-300"></p>
        </div>
      </div>
      <div class="mt-10 border px-10 py-10 border-blue-600 rounded-lg bg-blue-100">
        <!-- Render the box divs -->
        <div class="flex flex-wrap gap-5">
          <div
            v-for="(box, index) in boxes"
            :key="index"
            class="h-28 w-28 rounded-lg bg-blue-300 flex justify-center items-center text-xl text-white"
          >
            {{ box }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>

import {ref} from "vue";

const quantity =ref();
const boxes = ref ([]);
const addBoxes =() => {
  boxes.value=[];
  for (let i =0; i<quantity.value;i++){
    boxes.value.push(i+1)
  }
}
</script>
