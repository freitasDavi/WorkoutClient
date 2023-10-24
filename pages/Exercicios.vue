

<script setup>
import axios from "axios";
const data = ref([]);
const tableColumns = [{
    key: 'id',
    label: 'Código'
}, {
    key: 'nome',
    label: 'Nome'
}, {
    key: 'imagem',
    label: 'Imagem'
}]

const res = await axios.get("http://localhost:5097/api/Exercicios");
data.value = res.data;

</script>
<template>
    <main>
        <div class="bg-green-300 p-10 text-2xl font-semibold">
            <h1>Exercícios</h1>
        </div>
        <UTable :columns="tableColumns" :rows="data" />
    </main>
</template>
