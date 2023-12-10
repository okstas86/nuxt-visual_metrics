<template>
	<div class="mt-5"></div>
	<p class="font-bold">Recent orders</p>
	<div
		class="mt-5 overflow-x-auto rounded-md border bg-background scrollbar-thin scrollbar-thumb-input scrollbar-thumb-rounded-md"
	>
		<table class="f-full border-collapse">
			<thead>
				<tr class="border-b text-left text-xs">
					<th class="p-4 font-medium uppercase text-muted-foreground">
						Product
					</th>
					<th class="p-4 font-medium uppercase text-muted-foreground">
						Payment
					</th>
					<th class="p-4 font-medium uppercase text-muted-foreground">
						Status
					</th>
					<th class="p-4 font-medium uppercase text-muted-foreground"></th>
				</tr>
			</thead>
			<tbody>
				<tr
					v-for="(n, i) in 6"
					:key="i"
					class="border-b text-sm text-left last:border-b-0 hover:bg-muted"
				>
					<td class="p-4">Shoes</td>
					<td class="p-4">Paid</td>
					<td class="p-4">Shipped</td>
					<td class="p-4">
						<div class="flex item-center gap-3">
							<button>
								<Icon
									name="heroicons:pencil"
									class="w-4 h-4 text-muted-foreground"
								/>
							</button>
						</div>
					</td>
				</tr>
			</tbody>
		</table>
	</div>
</template>

<script lang="ts" setup></script>

<style></style>
