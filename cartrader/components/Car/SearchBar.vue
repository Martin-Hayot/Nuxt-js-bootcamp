<script setup>
	const city = ref("");
	const cityError = ref(false);
	const handleSearch = () => {
		if (!city.value) {
			return (cityError.value = true);
		}
		navigateTo(`/city/${city.value}/car`);
	};
</script>

<template>
	<!-- HOME SEARCH BAR -->
	<div
		class="font-serif w-[1000px] text-2xl rounded-full bg-white overflow-hidden flex justify-between drop-shadow-2xl mx-auto mb-96"
	>
		<input
			placeholder="Search by city..."
			type="text"
			v-model="city"
			class="py-3 px-5 w-full text-2xl rounded-full focus:outline-none"
			:class="cityError ? 'border-red-500 border' : ''"
		/>
		<button @click="handleSearch" class="bg-sky-500 px-10 text-white">
			Search
		</button>
	</div>
	<!-- HOME SEARCH BAR -->
</template>
