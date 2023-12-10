<template>
	<div class="flex flex-col">
		<template v-for="(l, i) in links" :key="i">
			<NuxtLink
				v-if="!l.items"
				to="/"
				class="inline-flex items-center gap-4 px-4 p-3 text-left text-[15px]"
			>
				<Icon
					v-if="l.icon"
					:name="l.icon"
					class="w-5 h-5 text-muted-foreground"
				/>
				<p class="truncate">{{ l.title }}</p>
			</NuxtLink>

			<HDisclosure v-slot="{ open }" v-else>
				<HDisclosureButton
					class="inline-flex items-center justify-between gap-4 px-4 p-3 text-left text-[15px]"
				>
					<div class="flex items-center gap-4">
						<Icon
							v-if="l.icon"
							:name="l.icon"
							class="w-5 h-5 text-muted-foreground"
						/>
						<p class="truncate">{{ l.title }}</p>
					</div>
					<div>
						<Icon
							:class="[open && 'rotate-180']"
							name="heroicons:chevron-down"
							class="w-5 h-5 text-muted-foreground transition"
						/>
					</div>
				</HDisclosureButton>
				<TransitionExpand>
					<HDisclosurePanel class="flex flex-col mx-6 px-3 border-l">
						<SidebarItem :links="l.items" />
					</HDisclosurePanel>
				</TransitionExpand>
			</HDisclosure>
		</template>
	</div>
</template>

<script lang="ts" setup>
const props = defineProps<{
	links?: any[]
}>()
</script>

<style></style>
