<script setup>
import { ref, computed } from 'vue';

const props = defineProps(['text', 'search', 'effect']);

const parsedSearch = computed(() => {
    return '(' + props.search.trim().replace(/ +/g, '|') + ')';
});

const parsedMsg = computed(() => {
    return props.text.split(new RegExp(parsedSearch.value, 'gi'));
});

const getClass = (i) => {
    let myClass = {};
    myClass[props.effect] = !!i;
    return myClass;
};
</script>

<template>
    <span>
        <span v-for="(s, i) in parsedMsg" :key="i" :class="getClass(i % 2)">{{ s }}</span>
    </span>
</template>


<style>
.sexiness {
    background-color: #e0f0ff;
}
</style>