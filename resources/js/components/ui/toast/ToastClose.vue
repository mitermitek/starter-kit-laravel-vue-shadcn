<script setup>
import { ToastClose } from "radix-vue";
import { XIcon } from "lucide-vue-next";
import { cn } from "@/lib/utils";

const props = defineProps({
  class: { type: String, required: false },
});
</script>

<template>
  <ToastClose
    v-bind="props"
    :class="
      cn(
        'absolute right-1 top-1 rounded-md p-1 text-foreground/50 opacity-0 transition-opacity hover:text-foreground focus:opacity-100 focus:outline-none focus:ring-1 group-hover:opacity-100 group-[.destructive]:text-red-300 group-[.destructive]:hover:text-red-50 group-[.destructive]:focus:ring-red-400 group-[.destructive]:focus:ring-offset-red-600',
        props.class
      )
    "
  >
    <XIcon class="h-4 w-4" />
  </ToastClose>
</template>
