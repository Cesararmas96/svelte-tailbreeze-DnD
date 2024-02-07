
<script lang="ts">
//   import { LOGONSERVER } from '$env/static/private';
	import Grid, { GridItem } from 'svelte-grid-extended';
//   import { Grid, GridItem, GridController } from 'svelte-grid-extended';

  // Creamos una instancia del controlador de Grid
//   let gridController: GridController;

//   // Esta función se encarga de obtener la primera posición disponible dentro del Grid
//   function getFirstAvailablePosition(w, h) {
//     return gridController.getFirstAvailablePosition(w, h);
//   }

const itemSize = { width: 100, height: 40 };
</script>

	<body>
		<div>
			<Grid  {itemSize} cols={0} rows={0} collision="compress">
				<GridItem  x={0} y={0} w={5} h={7} class="item " >
					<div class="card bg-slate-100 mb-4 inline-block w-full p-5">
						<div class="mb-4 flex items-start">
							<h4 class="font-bold leading-none text-heading">Sessions by Country</h4>

							<nav class="ml-auto -mt-2.5 -mr-2.5 flex items-center">
								<a class="icon btn hover:bg-light-100 dark:hover:bg-dark-200" href="">assessment</a>
								<a class="icon btn hover:bg-light-100 dark:hover:bg-dark-200" href="">download_for_offline</a>
								<a class="icon btn hover:bg-light-100 dark:hover:bg-dark-200" href="">info</a>
							</nav>
						</div>
						<div class="pb-3">
							<div id="map-sessions-country" class="mx-auto"></div>

							<div class="chart-bordered relative -mb-3 h-60 before:left-[3.4rem] before:top-[1.9rem] before:h-[calc(100%_-_3.8rem)] before:w-[calc(100%_-_3.6rem)]">
								<canvas id="chart-sessions-country" class="relative z-[1]"></canvas>
							</div>
						</div>
					</div>
				</GridItem>


			<GridItem  x={5} y={0} w={4} h={12} class="item bg-slate-200">
					<div class="card bg-slate-100 mb-4 inline-block w-full p-5">
					<div class="mb-4 flex items-start">
						<h4 class="font-bold leading-none text-heading">Active Users</h4>

						<nav class="ml-auto -mt-2.5 -mr-2.5 flex items-center">
							<a class="icon btn hover:bg-light-100 dark:hover:bg-dark-200" href="">assessment</a>
							<a class="icon btn hover:bg-light-100 dark:hover:bg-dark-200" href="">download_for_offline</a>
							<a class="icon btn hover:bg-light-100 dark:hover:bg-dark-200" href="">info</a>
						</nav>
					</div>

					<div class="-mb-2 text-heading">
						<div class="chart-bordered relative h-60 before:left-[1.75rem] before:top-0 before:h-[calc(100%_-_0.8rem)] before:w-[calc(100%_-_2rem)]">
							<canvas id="chart-active-users" class="relative z-[1]"></canvas>
						</div>

						<div class="flex items-center border-b border-light-200 py-3 dark:border-dark-200">
							<div class="flex-1 font-bold">/index.html</div>
							<div class="flex items-center text-green-500">
								<span class="icon mr-1 font-light">arrow_circle_up</span>
								78%
							</div>
							<div class="ml-3 w-10 text-right font-bold">1480</div>
						</div>
						<div class="flex items-center border-b border-light-200 py-3 dark:border-dark-200">
							<div class="flex-1 font-bold">/downloads/mobile.html</div>
							<div class="flex items-center text-green-500">
								<span class="icon mr-1 font-light">arrow_circle_up</span>
								69%
							</div>
							<div class="ml-3 w-10 text-right font-bold">1143</div>
						</div>
						<div class="flex items-center border-b border-light-200 py-3 dark:border-dark-200">
							<div class="flex-1 font-bold">/pricing.html</div>
							<div class="flex items-center text-red-500">
								<span class="icon mr-1 font-light">arrow_circle_down</span>
								65%
							</div>
							<div class="ml-3 w-10 text-right font-bold">954</div>
						</div>
						<div class="flex items-center border-b border-light-200 py-3 dark:border-dark-200">
							<div class="flex-1 font-bold">/blog/how-to-configure.html</div>
							<div class="flex items-center text-green-500">
								<span class="icon mr-1 font-light">arrow_circle_up</span>
								12%
							</div>
							<div class="ml-3 w-10 text-right font-bold">675</div>
						</div>
						<div class="flex items-center py-3">
							<div class="flex-1 font-bold">/products/design.html</div>
							<div class="flex items-center text-red-500">
								<span class="icon mr-1 font-light">arrow_circle_down</span>
								24%
							</div>
							<div class="ml-3 w-10 text-right font-bold">580</div>
						</div>
					</div>
				</div>
				</GridItem>
				
				<GridItem  x={9} y={0} w={5} h={10} class="item bg-slate-200">
				
					<div class="card bg-slate-100 mb-4 inline-block w-full p-5">
						<div class="mb-4 flex items-start">
							<h4 class="font-bold leading-none text-heading">Operating Systems Usage</h4>

							<nav class="ml-auto -mt-2.5 -mr-2.5 flex items-center">
								<a class="icon btn hover:bg-light-100 dark:hover:bg-dark-200" href="">info</a>
							</nav>
						</div>

						<div class="grid grid-cols-2 gap-3" id="os-usage-data"></div>
					</div>
				
				</GridItem>


				<GridItem  x={0} y={7} w={5} h={6} class="item bg-slate-200">
					
						<div class="card bg-slate-100 mb-4 inline-block w-full p-5">
					<div class="mb-4 flex items-start">
						<h4 class="font-bold leading-none text-heading">Device Sessions</h4>

						<nav class="-mr-2.5 -mt-2.5 ml-auto flex items-center">
							<a class="icon btn hover:bg-light-100 dark:hover:bg-dark-200" href="">info</a>
						</nav>
					</div>

					<div class="mb-4 flex items-center rounded bg-blue-500/20 p-1 text-blue-500">
						<i class="icon ml-2 mr-3 font-light">laptop_mac</i>

						<div class="flex-1">
							<div class="mr-2 flex h-8 items-center justify-end rounded bg-blue-500 px-2 text-sm font-bold text-white" style="width: 66%">66%</div>
						</div>
						<div class="w-16 pr-3 text-right text-lg font-bold">9983</div>
					</div>

					<div class="mb-4 flex items-center rounded bg-teal-500/20 p-1 text-teal-500">
						<i class="icon ml-2 mr-3 font-light">phone_iphone</i>

						<div class="flex-1">
							<div class="mr-2 flex h-8 items-center justify-end rounded bg-teal-500 px-2 text-sm font-bold text-white" style="width: 46%">46%</div>
						</div>
						<div class="w-16 pr-3 text-right text-lg font-bold">7532</div>
					</div>

					<div class="mb-4 flex items-center rounded bg-amber-500/20 p-1 text-amber-500">
						<i class="icon ml-2 mr-3 font-light">devices</i>

						<div class="flex-1">
							<div class="mr-2 flex h-8 items-center justify-end rounded bg-amber-500 px-2 text-sm font-bold text-white" style="width: 12%">12%</div>
						</div>
						<div class="w-16 pr-3 text-right text-lg font-bold">3156</div>
					</div>

					<div class="mt-3 flex items-center justify-center text-sm text-muted">
						<div class="flex items-center">
							<i class="mr-2 h-2 w-2 rounded-full bg-blue-400"></i>
							Desktop
						</div>
						<div class="mx-3 flex items-center">
							<i class="mr-2 h-2 w-2 rounded-full bg-teal-400"></i>
							Phone
						</div>
						<div class="mx-3 flex items-center">
							<i class="mr-2 h-2 w-2 rounded-full bg-amber-400"></i>
							Others
						</div>
					</div>
				</div>
				</GridItem>

				<GridItem  x={9} y={0} w={5} h={10} class="item bg-slate-200">
					
				</GridItem>

				<GridItem  x={5} y={12} w={4} h={7} class="item bg-slate-200">
						<div class="card bg-slate-100 mb-4 inline-block w-full p-5">
					<div class="mb-4 flex items-start">
						<h4 class="font-bold leading-none text-heading">Visits by Source</h4>

						<nav class="ml-auto -mt-2.5 -mr-2.5 flex items-center">
							<a class="icon btn hover:bg-light-100 dark:hover:bg-dark-200" href="">info</a>
						</nav>
					</div>

					<div class="relative mb-5 h-60">
						<canvas id="chart-visits-by-source"></canvas>
						<div class="pointer-events-none absolute left-0 top-0 z-0 flex h-full w-full flex-col items-center justify-center">
							<div class="-mb-1 text-2xl font-bold text-heading">645K</div>
							<div class="text-muted">Total Sessions</div>
						</div>
					</div>

					<div id="visit-by-source">
					</div>
				</div>
				</GridItem>

				<GridItem  x={9} y={0} w={5} h={10} class="item bg-slate-200">
				
				<div class="card bg-slate-100 mb-4 inline-block w-full p-5">
					<div class="mb-4 flex items-start">
						<h4 class="font-bold leading-none text-heading">Browser Bounce Rate</h4>

						<nav class="ml-auto -mt-2.5 -mr-2.5 flex items-center">
							<a class="icon btn hover:bg-light-100 dark:hover:bg-dark-200" href="">info</a>
						</nav>
					</div>

					<div id="browser-bounce-rate" class="-mb-2">
					</div>
				</div>
				</GridItem>

				<GridItem  x={9} y={10} w={5} h={6} class="item bg-slate-200">
					<div class="card bg-slate-100 mb-4 inline-block w-full p-5">
					<div class="mb-4 flex items-start">
						<h4 class="font-bold leading-none text-heading">Engagements</h4>

						<nav class="ml-auto -mt-2.5 -mr-2.5 flex items-center">
							<a class="icon btn hover:bg-light-100 dark:hover:bg-dark-200" href="">info</a>
						</nav>
					</div>

					<div class="flex items-center border-b border-light-200 py-2 dark:border-dark-200">
						<div class="flex-1">
							<h2 class="-mb-1 text-3xl text-heading">4.970</h2>
							<div class="text-muted">Daily page views per visitor</div>
						</div>
						<div class="flex items-center rounded bg-green-500 py-1 px-3 text-2xl text-white">
							2.5
							<i class="icon ml-2"> trending_up </i>
						</div>
					</div>
					<div class="flex items-center border-b border-light-200 py-2 dark:border-dark-200">
						<div class="flex-1">
							<h2 class="-mb-1 text-3xl text-heading">8.375</h2>
							<div class="text-muted">Daily time on site per about</div>
						</div>
						<div class="flex items-center rounded bg-red-500 py-1 px-3 text-2xl text-white">
							3.2
							<i class="icon ml-2"> trending_down </i>
						</div>
					</div>
					<div class="flex items-center pt-2">
						<div class="flex-1">
							<h2 class="-mb-1 text-3xl text-heading">65.3%</h2>
							<div class="text-muted">Average bounce rate</div>
						</div>
						<div class="flex items-center rounded bg-amber-500 py-1 px-3 text-2xl text-white">
							0.1
							<i class="icon ml-2"> trending_up </i>
						</div>
					</div>
				</div>
				</GridItem>

				<GridItem  x={0} y={12} w={5} h={6} class="item bg-slate-200">
				<div class="card bg-slate-100 mb-4 inline-block w-full p-5">
					<div class="mb-4 flex items-start">
						<h4 class="font-bold leading-none text-heading">Average Visit Duration</h4>

						<nav class="ml-auto -mt-2.5 -mr-2.5 flex items-center">
							<a class="icon btn hover:bg-light-100 dark:hover:bg-dark-200" href="">info</a>
						</nav>
					</div>

					<div class="h-52 rounded-md border border-light-200 pb-2 pl-2 pt-4 dark:border-dark-200">
						<canvas id="chart-average-visit-duration">
						</canvas>
					</div>
					<div class="mt-3 flex items-center justify-center text-sm text-muted">
						<div class="flex items-center">
							<i class="mr-2 h-2 w-2 rounded-full bg-teal-500"></i>
							Current Month
						</div>
						<div class="mx-3 flex items-center">
							<i class="mr-2 h-2 w-2 rounded-full bg-slate-300"></i>
							Last Month
						</div>
					</div>
				</div>
				</GridItem>
				
				
				
			</Grid>
		</div>

		
	
	</body>
<!-- </html> -->
