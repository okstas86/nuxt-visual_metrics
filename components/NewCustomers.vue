<template>
	<section class="mt-5">
		<h3 class="font-bold">New Customers</h3>
		<div
			class="flex items-start w-full mt-5 gap-6 overflow-x-auto rounded-lg border bg-bacground p-5 scrollbar-thin scrollbar-thumb-input scrollbar-track-rounded-md"
		>
			<div class="flex shrink-0 flex-col items-center gap-2">
				<button
					class="flex w-10 h-10 items-center justify-center rounded-full bg-muted"
				>
					<Icon name="heroicons:plus" class="w-5 h-5" />
				</button>
				<div>
					<p class="text-sm font-semibold">Add</p>
				</div>
			</div>
			<template v-for="(n, i) in data" :key="i">
				<div class="flex shrink-0 flex-col items-center gap-2">
					<img
						:src="n.picture.thumbnail"
						alt="n.name.first"
						class="w-10 h-10 rounded-full object-cover"
					/>
					<div class="text-center">
						<p class="text-sm font-semibold">
							{{ n.name.first }} {{ n.name.last }}
						</p>
						<p class="text-xs text-muted-foreground">10 min ago</p>
					</div>
				</div>
			</template>
		</div>
	</section>
</template>

<script lang="ts" setup>
const { data } = await useAsyncData(
	'new-customers',
	() => $fetch('https://randomuser.me/api/?results=20'),
	{
		default: () => [],
		transform: (data: any) => data.results,
	}
)
</script>
