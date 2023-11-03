<script setup>
import { PaginationPrev, useForwardProps } from "radix-vue";
import { ChevronLeftIcon } from "@radix-icons/vue";
import { Button } from "@/components/ui/button";

const props = defineProps({
  asChild: { type: Boolean, required: false, default: true },
  as: { type: null, required: false },
});
const forwarded = useForwardProps(props);
</script>

<template>
  <PaginationPrev v-bind="forwarded">
    <Button class="w-9 h-9 p-0" variant="outline">
      <slot>
        <ChevronLeftIcon />
      </slot>
    </Button>
  </PaginationPrev>
</template>
