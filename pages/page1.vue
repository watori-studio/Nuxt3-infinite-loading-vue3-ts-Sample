<template>
	<div>
		<h1>List page</h1>
		<button v-on:click="buttonEvent()">SamplueButton</button>
		<button v-on:click="moveIndex()">indexへ移動($router.push)</button>
		<div>search</div>
		<infinite-loading @infinite="load">
			<template #spinner> // loading here </template>
			<template #no-more> // text no more </template>
			<template #no-results> // text no results </template>
		</infinite-loading>
	</div>
</template>

<script setup lang="ts">
import { ref, onBeforeMount, onMounted, onBeforeUpdate, onUpdated } from 'vue';
import InfiniteLoading from 'infinite-loading-vue3-ts';
const router = useRouter();
const mounted = ref(false);
const load = async ($state) => {
	try {
		$state.complete();
	} catch (error) {
		$state.error();
	} finally {
	}
};

const buttonEvent = async () => {
	alert('Clicked button');
};
const moveIndex = async () => {
	return navigateTo({
		path: '/',
		query: {},
	});
};
onBeforeMount(() => {
	console.log('on before mount');
	mounted.value = true;
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
