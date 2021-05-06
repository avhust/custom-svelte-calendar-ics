<script>
	import FullCalendar from 'svelte-fullcalendar';
	import dayGridPlugin from '@fullcalendar/daygrid';
	import iCalendarPlugin from '@fullcalendar/icalendar'

	let options = {
		droppable: true,
		editable: true,
		initialView: 'dayGridMonth',
		plugins: [dayGridPlugin, iCalendarPlugin],
		height: 'auto',
		weekends: true,
		events: {
    url: 'https://secured.sirvoy.com/ical/16b1f029-0b65-476d-854a-a52733013cd1',
    // url: '/sirvoy_ical_16b1f029-0b65-476d-854a-a52733013cd1.ics',
    format: 'ics'
  }
	};
	let calendarComponentRef;

</script>

<style>
	.demo-app {
		width: 100vw;
		height: 100vh;
		font-family: Arial, Helvetica Neue, Helvetica, sans-serif;
		font-size: 14px;
	}
	.demo-app-calendar {
		margin: 0 auto;
		max-width: 900px;
	}
	:global(.draggable) {
		color: white;
		background: #3788d8;
		width: fit-content;
		padding: 1rem;
		margin: 1rem;
		cursor: pointer;
	}
</style>

<div class="demo-app">

	<div class="demo-app-calendar">
		<FullCalendar bind:this={calendarComponentRef} {options} />
	</div>
</div>