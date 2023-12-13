<template>
	<header class="stycky top-0 z-20 border-b bg-background/80 backdrop-blur">
		<div class="container flex h-16 items-center justify-between">
			<div class="flex items-center gap-3">
				<img
					src="/icon.svg"
					alt="VisualMetrics"
					class="w-7 h-7 object-contain"
				/>
				<NuxtLink class="text-xl font-bold" to="/">Visual Metrics</NuxtLink>
			</div>

			<div class="flex items-center gap-5">
				<button
					@click="toggleTheme"
					aria-label="Toggle theme"
					class="flex h-9 w-9 shrink-0 items-center justify-center rounded-full border bg-background"
				>
					<Icon name="heroicons:sun" class="w-5 h-5" />
				</button>
				<HMenu as="div" class="relative">
					<HMenuButton
						class="flex h-9 w-9 shrink-0 items-center justify-center rounded-full overflow-hidden border bg-background"
					>
						<img
							src="https://randomuser.me/api/portraits/med/men/79.jpg"
							alt="Logged in user"
							class="w-full h-full"
						/>
					</HMenuButton>
					<TransitionScale :scale="0.8" origin="top-right">
						<HMenuItems
							class="absolute right-0 z-10 mt-3 w-48 rounded-md border bg-background focus:outline:none focus-visible:ring-2 focus-visible:ring-ring"
						>
							<div class="border-b px-3 py-1.5 text-sm">
								<p class="font-semibold">Hello Stas</p>
								<a
									href="mailto:stas@gmail.com"
									class="leading-none text-muted-foreground"
									>stas@gmail.com
								</a>
							</div>
							<div class="p-1">
								<template v-for="(p, i) in profileMenuOptions" :key="i">
									<HMenuItem v-if="!p.divider" v-slot="{ active }">
										<button
											@click="p.click?.()"
											:class="[active && 'bg-muted']"
											class="inline-flex w-full items-center rounded-md p-2 text-sm font-medium"
										>
											{{ p.title }}
										</button>
									</HMenuItem>
									<hr v-if="p.divider" class="my-1" />
								</template>
							</div>
						</HMenuItems>
					</TransitionScale>
				</HMenu>
			</div>
		</div>
	</header>
</template>

<script lang="ts" setup>
const mode = useColorMode()
const toggleTheme = () => {
	mode.value = mode.value === 'light' ? 'dark' : 'light'
}

const profileMenuOptions = [
	{ title: 'Profile' },
	{ title: 'Billing' },
	{ title: 'Settings' },
	{ title: 'Team members' },
	{ title: 'Sales' },
	{ divider: true },
	{ title: 'Logout', click: () => alert('Logout') },
]
</script>
