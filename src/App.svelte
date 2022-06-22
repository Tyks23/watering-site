<script>
	import DatePicker from "./DatePicker.svelte";
  
	let currentDate = new Date();
  
	const onDateChange = d => {
	  currentDate = d.detail;
	};
  </script>
 	<div>
		<img src="https://i.giphy.com/media/8cMMs939wIlDWO8pB7/giphy.webp" style="height: 200px;"/>
	</div>
  <div class="container">
	<img src="https://media0.giphy.com/media/l0IpXgEBZ3y3UEljO/giphy.gif?cid=790b76118045ca2188432fc26b6a36dff35b3719447e067d&rid=giphy.gif&ct=s" />
	<DatePicker
	on:datechange={onDateChange}
	selected={currentDate}
	isAllowed={date => {
	  const millisecs = date.getTime();
	  if (millisecs + 25 * 3600 * 1000 < Date.now()) return false;
	  if (millisecs > Date.now() + 3600 * 24 * 45 * 1000) return false;
	  return true;
	}} />
	<img src="https://media0.giphy.com/media/l0IpXgEBZ3y3UEljO/giphy.gif?cid=790b76118045ca2188432fc26b6a36dff35b3719447e067d&rid=giphy.gif&ct=s" />
	</div>
	<img src="https://i.giphy.com/media/1PdgEaPoXb5CdZtaiv/200w.webp" />
	<img src="https://i.giphy.com/media/1PdgEaPoXb5CdZtaiv/200w.webp" />
	<img src="https://i.giphy.com/media/1PdgEaPoXb5CdZtaiv/200w.webp" />
	<img src="https://i.giphy.com/media/1PdgEaPoXb5CdZtaiv/200w.webp" />
	<img src="https://i.giphy.com/media/1PdgEaPoXb5CdZtaiv/200w.webp" />
	<img src="https://i.giphy.com/media/1PdgEaPoXb5CdZtaiv/200w.webp" />
	<img src="https://i.giphy.com/media/1PdgEaPoXb5CdZtaiv/200w.webp" />
	<img src="https://i.giphy.com/media/1PdgEaPoXb5CdZtaiv/200w.webp" />
	<img src="https://i.giphy.com/media/1PdgEaPoXb5CdZtaiv/200w.webp" />
  
  <!--
	// setInterval(() => {
	//   currentDate = new Date(currentDate.getTime() + 24 * 3600 * 1000);
	// }, 1000);
  
	// const isAllowed = date => {
	//   const millisecs = date.getTime();
	//   if (millisecs + 25 * 3600 * 1000 < Date.now()) return false;
	//   if (millisecs > Date.now() + 3600 * 24 * 30 * 1000) return false;
	//   return true;
	// };
  -->
  
  <style>

	.container{
		display:flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		text-align: center;
		background-color: rgb(197, 104, 199);
		align-items: center;
		padding: 5px;
		border-radius: 10%;
		color:rgb(73, 9, 86);
	}
  </style>