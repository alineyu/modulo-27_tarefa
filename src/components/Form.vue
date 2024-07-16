<script setup>
const props = defineProps(['valorN1', 'valorN2', 'trocarFiltro'])

</script>

<template>
    <form>
        <div class="row">
            <div class="col">
                <input @keyup="props.valorN1" class="form-control p-2 w-100" type="number">
            </div>
            <div class="col">
                <input @keyup="props.valorN2" class="form-control p-2 w-100" type="number">
            </div>
        </div>
        <select @change="props.trocarFiltro" class="form-control mt-4">
            <option value="adicao">Adição</option>
            <option value="subtracao">Subtração</option>
            <option value="multiplicacao">Multiplicação</option>
            <option value="divisao">Divisão</option>
        </select>
    </form>
</template>