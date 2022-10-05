<template>
	<div>
		<h1>IndexPage</h1>
		<button v-on:click="movePage1()">page1へ移動($router.push)</button>
	</div>
</template>

<script setup lang="ts">
import { ref, onBeforeMount, onMounted, onBeforeUpdate, onUpdated } from 'vue';
const router = useRouter();
const movePage1 = async () => {
	return navigateTo({
		path: '/page1',
		query: {},
	});
};
onBeforeMount(() => {
	console.log('on before mount');
});

onMounted(() => {
	console.log('on mount');
});

onBeforeUpdate(() => {
	console.log('on before update');
});

onUpdated(() => {
	console.log('on update');
});
</script>
