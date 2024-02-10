<template lang="">
    <div class="card">
        <span>
            <h4>id: {{props.id}} </h4>
            <h4>title: {{props.date}}</h4>
        </span>
        <h1>body: {{props.title}}</h1>
        <h1>date: {{props.body}}</h1>
        <button @click="clicked"> clickclick</button>
        <button @click="miNombre"> clickclick</button>
        <!-- <input type="text" v-model ="titulo"> -->
    </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import type { IPost } from '@/interface/IPost';


const props = defineProps<IPost>()
const emits = defineEmits(['SayHi','Nombre'])

const nombre = 'Jorge Ariel Hernández Sánchez'
//const titulo = ref('')
//const copia = props;
//Funciones
/* EMITIS PARA UN COMPONENTES SON ACCIONES DEL HIJO */
/* const pros = defineProps<Ipost>(); */
const clicked = () => {
    /* console.log('Botón clickeado'); */
    emits("SayHi", "Desde el hijo", 'Jorge Ariel Hernández Sánchez','esta presente')
}
const miNombre = () => {
    emits('Nombre',nombre)
}
</script>

<style scoped>
.card{
    border: 1px solid rgb(100, 27, 27);
    padding: 10px;
    margin: 5px;
}
</style>