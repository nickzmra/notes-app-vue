<template>
    <div class="absolute inset-0 w-screen h-screen bg-blueGray-600 flex justify-center items-center">
        <button @click="showToggle" class="text-white absolute top-2 left-2">
            <ant-design:close-circle-outlined class="text-5xl"/>
        </button>
        <form @submit.prevent class="space-y-4">
            <div class="flex flex-col">
                <label for="title" class="text-white mb-1">Title</label>
                <input type="text" name="title" class="rounded py-2 px-4" placeholder="Title"/>
            </div>
            <div class="flex flex-col">
                <label for="content" class="text-white mb-1">Content</label>
                <textarea name="content" class="rounded py-2 px-4" placeholder="Note Content"/>
            </div>
            <div>
                <button class="w-full bg-indigo-500 p-2 rounded mt-4 hover:bg-indigo-700 hover:text-white">
                    Add
                </button>
            </div>
        </form>
    </div>
</template>

<script setup>
    import {showToggle} from '~/helpers/useNotes'
</script>