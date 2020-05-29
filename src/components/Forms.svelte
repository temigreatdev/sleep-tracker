
  <script>
    import { createForm } from "svelte-forms-lib";

    export let selectedDate;

    const { form, handleChange, handleSubmit } = createForm({
      initialValues: {
        date:selectedDate,
        hourToBed: "00:00",
        hourLightsOff: "00:00",
        timeToStartSleepInMinutes: 0,
        timesAwakedDuringSleep: 0,
        totalTimeAwakedDuringSleepInHours:"00:00",
        hourAwaked:"00:00",
        hourGoOffTheBed:"00:00",
        totalHoursOfSleepLastNight:"00:00"
      },
      onSubmit: values => {
        alert(JSON.stringify(values));
      }
    });

   </script>

  <style>
    
    @import url(https://fonts.googleapis.com/css?family=Montserrat:400,700);

    form { 
        max-width:700;
        max-height: 100%;
        margin:10px auto; 
    }

    .input-wrapper {
        display: flex;
        background-color: transparent;
        width:100%;
        margin: 5px 5px;
        color:white;
        text-align: justify;
    }

    .input-wrapper span {
        margin-right: 15px;
    }

    .title-form {
        font-size: 14pt;
    }

    .feedback-input {
        height: 30px;
        color:white;
        background-color: transparent;
        font-family: Helvetica, Arial, sans-serif;
        font-weight:bold;
        font-size: 12pt;
        line-height: 11px;
        transition: all 0.3s;
        outline:0;
        border:none;
    }

    [type="submit"] {
        font-family: 'Montserrat', Arial, Helvetica, sans-serif;
        width: 100%;
        background:#9544eb;
        border-radius:5px;
        border:0;
        cursor:pointer;
        color:white;
        font-size:12pt;
        padding-top:10px;
        padding-bottom:10px;
        transition: all 0.3s;
        margin:5px 0 20px 5px;
        font-weight:700;
    }
    
    [type="submit"]:hover { 
        background:#9544ea; 
    }

    .container {
        height: 100%;
    }

    .wd-10 {
        width: 10%;
    }

    .wd-90 {
        width: 90%;
    }
    
  </style>

<div class="container">
    
    <form on:submit={handleSubmit}>
        
        <span id="date" class="title-form">{$form.date}</span>   
        
        <div class="input-wrapper">
            <span class="wd-90">Que horas você foi para a cama?</span>
            <input
            id="hourToBed"
            name="hourToBed"
            type="time"
            class="feedback-input wd-10"
            on:change={handleChange}
            bind:value={$form.hourToBed}
            required
            />
        </div>

        <div class="input-wrapper">
            <span class="wd-90">Que horas você desligou as luzes para dormir?</span>
            <input
            id="hourLightsOff"
            name="hourLightsOff"
            type="time"
            class="feedback-input wd-10"
            on:change={handleChange}
            bind:value={$form.hourLightsOff}
            required
            />
        </div>

        <div class="input-wrapper">
            <span class="wd-90">Quantos tempo você demorou para iniciar o sono? (minutos)</span>
            <input
            id="timeToStartSleepInMinutes"
            name="timeToStartSleepInMinutes"
            type="number"
            class="feedback-input wd-10"
            on:change={handleChange}
            bind:value={$form.timeToStartSleepInMinutes}
            required
            />
        </div>

        <div class="input-wrapper">
            <span class="wd-90">Quantas vezes você acordou na noite passada?</span>
            <input
            id="timesAwakedDuringSleep"
            name="timesAwakedDuringSleep"
            type="number"
            class="feedback-input wd-10"
            on:change={handleChange}
            bind:value={$form.timesAwakedDuringSleep}
            required
            />
        </div>

        <div class="input-wrapper">
            <span class="wd-90">Quanto tempo você ficou acordado ao longo da noite? (tempo total dos despertares.)</span>
            <input
            id="totalTimeAwakedDuringSleepInHours"
            name="totalTimeAwakedDuringSleepInHours"
            type="time"
            class="feedback-input wd-10"
            on:change={handleChange}
            bind:value={$form.totalTimeAwakedDuringSleepInHours}
            required
            />
        </div>

          <div class="input-wrapper">
            <span class="wd-90">Que horas você acordou pela manhã?</span>
            <input
            id="hourAwaked"
            name="hourAwaked"
            type="time"
            class="feedback-input wd-10"
            on:change={handleChange}
            bind:value={$form.hourAwaked}
            required
            />
        </div>

        <div class="input-wrapper">
            <span class="wd-90">Que horas você se levantou da cama?</span>
            <input
            id="hourGoOffTheBed"
            name="hourGoOffTheBed"
            type="time"
            class="feedback-input wd-10"
            on:change={handleChange}
            bind:value={$form.hourGoOffTheBed}
            required
            />
        </div>      

        <div class="input-wrapper">
            <span class="wd-90">Quantas horas você dormiu na noite passada?</span>
            <input
            id="totalHoursOfSleepLastNight"
            name="totalHoursOfSleepLastNight"
            type="time"
            class="feedback-input wd-10"
            on:change={handleChange}
            bind:value={$form.totalHoursOfSleepLastNight}
            required
            />
        </div>          

        <input type="submit" value="SALVAR"/>

    </form>
    
</div>