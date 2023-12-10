<template>
	<div>
		<Header />
		<div class="container lg:grid lg:grid-cols-12 lg:gap-10">
			<Sidebar class="hidden lg:col-span-3 lg:block" />
			<main class="py-5 lg:col-span-6">
				<StatusCard />
				<NewCustomers />
				<SalesChart />
				<RecentOrders />
			</main>
			<div class="py-5 lg:col-span-3 lg:bloc">
				<ProfileInfo />
				<Reminders />
			</div>
		</div>
	</div>
</template>
