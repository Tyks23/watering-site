<script>
    import { createEventDispatcher } from "svelte";
    import Calender from "./Calender.svelte";
    import { getMonthName } from "./date-time.js";
  
    const dispatch = createEventDispatcher();
  
    // props
    export let isAllowed = () => true;
    export let selected = new Date();
  
    // state
    let date, month, year, showDatePicker;
  
    // so that these change with props
    $: {
      date = selected.getDate();
      month = selected.getMonth();
      year = selected.getFullYear();
    }
  
    // handlers
    const onFocus = () => {
      showDatePicker = true;
    };
  
    const next = () => {
      if (month === 11) {
        month = 0;
        year = year + 1;
        return;
      }
      month = month + 1;
    };
  
    const prev = () => {
      if (month === 0) {
        month = 11;
        year -= 1;
        return;
      }
      month -= 1;
    };
  
    let dayVar = "";
    let wateringBool;

    const decideWateringStatus = () => {
    dayVar = selected.toDateString().split(' ')[0];
    if(dayVar == 'Mon' || dayVar == "Thu"){
        wateringBool = true;
        return "Täna peab lilli kastma";
    }
    else{
        wateringBool = false;
        return "Täna ei pea lilli kastma";
    }
    }
    let wateringVar = decideWateringStatus();

  </script>
  
  <style>
    .relative {
      position: relative;
    }
    .box {
      position: absolute;
      top: 40px;
      left: 0px;
      border: 1px solid green;
      display: inline-block;
    }
  
    .month-name {
      display: flex;
      justify-content: space-around;
      align-items: center;
      margin: 6px 0;
    }
  
    .center {
      display: flex;
      justify-content: center;
      align-items: center;
    }

    #watering {
        font-size: 36px;
    }
  </style>
  
  
  <div class="relative">
    <p id="watering">{wateringVar}</p>
    <p>{selected.toDateString()}</p>
    {#if wateringBool}
    <img src="https://www.engledow.com/wp-content/uploads/2018/06/Watering-Garden-e1528137712132-300x200.jpg" />
    {:else}
    <img src="https://static.wixstatic.com/media/e7a85a_98522c9b461d47e1b24f89b8f3834c24~mv2.jpg/v1/fill/w_800,h_619,al_c,q_90/file.jpg" />
    {/if}
  </div>
  