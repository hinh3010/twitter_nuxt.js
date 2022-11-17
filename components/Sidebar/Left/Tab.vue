<template>
    <nuxt-link to="#" class="flex items-center p-3 min-w-full text-black rounded-full   dark:text-white"
        :class="bgClasses">

        <div class="w-6 h-6 text-dark">
            <slot name="icon"></slot>
        </div>

        <div class="hidden ml-4 text-xl xl:block" :class="textClasses">
            <slot name="name"></slot>
        </div>

    </nuxt-link>
</template>

<script setup>

const { defaultTransition } = useTailwindConfig()

const props = defineProps({
    active: {
        type: Boolean,
        default: false
    }
})

const textClasses = computed(() => props.active ? 'font-semibold' : 'font-normal')
const bgClasses = computed(() => props.active
    ? 'bg-blue-400 ' + defaultTransition
    : defaultTransition + ' hover:bg-gray-200 dark:hover:bg-dim-200'
)

</script>