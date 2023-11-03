<script setup>
import { useAttrs } from "vue";
import { PaginationEllipsis, useForwardProps } from "radix-vue";
import { DotsHorizontalIcon } from "@radix-icons/vue";
import { cn } from "@/lib/utils";

defineOptions({
  inheritAttrs: false,
});

const props = defineProps({
  asChild: { type: Boolean, required: false },
  as: { type: null, required: false },
});
const forwarded = useForwardProps(props);
const { class: className, ...rest } = useAttrs();
</script>

<template>
  <PaginationEllipsis
    :class="cn('w-9 h-9 flex items-center justify-center', className ?? '')"
    v-bind="{ ...forwarded, ...rest }"
  >
    <slot>
      <DotsHorizontalIcon />
    </slot>
  </PaginationEllipsis>
</template>
