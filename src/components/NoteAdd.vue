<template>
    <div class="bg-teal-800 rounded-lg shadow-lg text-center flex justify-center items-center">
        <button @click="showToggle" class="opacity-50 transform transition-all hover:scale-110 hover:opacity-70">
            <ic:baseline-add-circle-outline class="w-40 h-40"/>
        </button>
    </div>
</template>

<script setup>
    import {showToggle} from '~/helpers/useNotes'
</script>