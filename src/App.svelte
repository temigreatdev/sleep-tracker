<script>
  import Icon from "svelte-awesome";
  import { table, plusCircle, areaChart, calendar } from "svelte-awesome/icons";
  import Datepicker from "svelte-calendar";
  import dayjs from "dayjs";
  import Forms from "./components/Forms.svelte"

  const daysOfWeek = [
    ["Domingo", "Dom"],
    ["Segunda", "Seg"],
    ["Terça", "Ter"],
    ["Quarta", "Qua"],
    ["Quinta", "Qui"],
    ["Sexta", "Sex"],
    ["Sábado", "Sáb"]
  ];
  const monthsOfYear = [
    ["Janeiro", "Jan"],
    ["Fevereiro", "Fev"],
    ["Março", "Mar"],
    ["Abril", "Abr"],
    ["Maio", "Mai"],
    ["Junho", "Jun"],
    ["Julho", "Jul"],
    ["Agosto", "Ago"],
    ["Setembro", "Set"],
    ["Outubro", "Out"],
    ["Novembro", "Nov"],
    ["Dezembro", "Dez"]
  ];

  let dateChosen = null;
  let selected = new Date();
</script>

<style>
  .container {
    display: flex;
    color: #9544eb;
  }

  .panel {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #313040a8;
    margin: 10px;
    text-align: center;
    line-height: 75px;
    font-size: 30px;
    font-weight: bold;
  }

  .btn-datepicker {
    color: #9544eb;
    border: 0;
    background-color: #313040a8;
    margin: 0 0 10% 0;
  }

  .opacity-100 {
    opacity: 1;
  }

  .opacity-90 {
    opacity: 0.9;
  }

  .wd-100 {
    width: 100%;
  }

  .wd-70 {
    width: 70%;
  }

  .wd-50 {
    width: 50%;
  }

  .wd-25 {
    width: 25%;
  }

  .vh-70 {
    height: 70vh;
  }

  .vh-30 {
    height: 30vh;
  }
</style>

<main>
  <div class="container vh-70">
    <div class="panel wd-100" >
      
      { dayjs(selected).format('DD/MM/YYYY') }
     
      <Forms/>

    </div>
  </div>
  <div class="container opacity-90 vh-30">
    <div class="panel wd-100">
      <div class="wd-25">
        <Datepicker
          format={date => dayjs(date).format('DD/MM/YYYY')}
          buttonBackgroundColor="#e20074"
          buttonTextColor="white"
          highlightColor="#e20074"
          dayBackgroundColor="#efefef"
          dayTextColor="#333"
          dayHighlightedBackgroundColor="#e20074"
          dayHighlightedTextColor="#fff"
          {daysOfWeek}
          {monthsOfYear}
          bind:dateChosen
          bind:selected >
               <Icon data={calendar} scale="5"/>
          </Datepicker>
      </div>
      <div class="wd-25">
        <Icon data={plusCircle} scale="5"/>
      </div>
      <div class="wd-25">
        <Icon data={table} scale="5"/>
      </div>
      <div class="wd-25">
        <Icon data={areaChart} scale="5" />
      </div>
    </div>
  </div>

</main>
