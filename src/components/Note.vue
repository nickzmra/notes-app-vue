<template>
    <div class="bg-teal-800 rounded-lg shadow-lg text-center p-2">
        <h3 class="text-2xl font-thin tracking-wide">{{$props.note.title}}</h3>
        <p class="text-sm-font">{{$props.note.content}}</p>
        <div class="flex justify-between">
            <button @click="editNote(note)" class="text-2xl hover:text-white"><mdi:playlist-edit/></button>
            <button @click="removeNote($props.note.id)" class="text-2xl hover:text-red-700"><raphael:trash/></button>
        </div>
    </div>
</template>

<script setup>
    import {defineProps, defineEmit} from 'vue'
    import {remove, showToggle, noteToEdit} from '~/helpers/useNotes'

    defineProps({
        note: Object,
        default: {
            id: 0,
            title: '',
            content: '',
        },
    })

    const emit = defineEmit(['deleted'])

    const removeNote = async (id) => {
        await remove(id)
        emit('deleted')
    }

    const editNote = note => {
        noteToEdit.value = note
        showToggle()
    }
</script>