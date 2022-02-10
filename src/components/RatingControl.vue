<template>
    <ul>
        <li :class="{active: modelValue=='poor'}">
            <button type="button" @click="selectOption('poor')">Poor</button>
        </li>
        <li :class="{active: modelValue=='avg'}">
            <button type="button" @click="selectOption('avg')">Average</button>
        </li>
        <li :class="{active: modelValue=='great'}">
            <button type="button" @click="selectOption('great')">Great</button>
        </li>
    </ul>
</template>

<script>
    export default {
        props: ['modelValue'],
        emits: ['update:modelValue'],
        methods:{
            selectOption(option){
                this.$emit('update:modelValue', option);
            },
        }
    }
</script>

<style scoped>
.active{
    border-color: #4169e1;
}

.active button{
    color: #4169e1;
}

ul{
    list-style: none;
    margin: 0.5rem 0;
    padding: 0;
    display: flex;
}

li{
    margin: 0 1rem;
    border: 1px solid #ccc;
    padding: 1rem;
    display: flex;
    justify-content: center;
    align-items: center;
}

button{
    font: inherit;
    background-color: transparent;
    border: none;
    cursor: pointer;
}
</style>