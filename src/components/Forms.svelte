
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
        totalTimeAwakedDuringSleepInHours:0,
        hourAwaked:"00:00",
        hourGoOffTheBed:"00:00",
        totalHoursOfSleepLastNight:0
      },
      onSubmit: values => {
        alert(JSON.stringify(values));
      }
    });

    /**
        1. Que horas você foi para a cama? 
        2. Que horas você desligou as luzes para dormir?
        3. Quanto tempo você demorou para iniciar o sono? 
        4. Quantas vezes você acordou na noite passada? 
        5. Quanto tempo você ficou acordado ao longo da noite? (tempo total dos despertares.) 
        6. Que horas você acordou pela manhã?
        7. Que horas você se levantou da cama?
        8. Quantas horas você dormiu na noite passada?

        date:"",
        hourToBed: "",
        hourLightsOff: "",
        timeToStartSleepInMinutes: 0,
        timesAwakedDuringSleep: 0,
        totalTimeAwakedDuringSleepInHours:0,
        hourAwaked:"",
        hourGoOffTheBed:"",
        totalHoursOfSleepLastNight:""

    */
   </script>

  <style>
    
    @import url(https://fonts.googleapis.com/css?family=Montserrat:400,700);

    form { 
        max-width:420px;
        max-height: 100%;
        margin:10px auto; 
    }

    .feedback-input {
        height: 30px;
        color:white;
        font-family: Helvetica, Arial, sans-serif;
        font-weight:500;
        font-size: 12pt;
        border-radius: 5px;
        line-height: 11px;
        background-color: transparent;
        border:2px solid #9544eb;
        transition: all 0.3s;
        padding: 6px;
        margin: 0px 5px;
        width:100%;
        box-sizing: border-box;
        outline:0;
    }

    .feedback-input:focus { 
        border:2px solid #9544ea; 
    }

    input:invalid:before {
        color: #808080;
        content: attr(placeholder);
        padding-left: 10px;
        pointer-events: none;
        position: absolute;
        left: 20px;
    }

    input:valid:before,
    input:focus:before,
    input:active:before {
    display: none;
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
    
  </style>

<div class="container">
            <span id="date">{$form.date}</span>   
    <form on:submit={handleSubmit}>
        
            <label for="hourToBed">Que horas você foi para a cama?</label>    
            <input
            id="hourToBed"
            name="hourToBed"
            on:change={handleChange}
            bind:value={$form.hourToBed}
            class="feedback-input"
            placeholder="Que horas você foi para a cama?"
            type="time"
            />

            <input
            id="hourToBed"
            name="hourToBed"
            on:change={handleChange}
            bind:value={$form.hourToBed}
            class="feedback-input"
            placeholder="Que horas você foi para a cama?"
            />

            <input
            id="hourToBed"
            name="hourToBed"
            on:change={handleChange}
            bind:value={$form.hourToBed}
            class="feedback-input"
            placeholder="Que horas você foi para a cama?"
            />

            <input
            id="hourToBed"
            name="hourToBed"
            on:change={handleChange}
            bind:value={$form.hourToBed}
            class="feedback-input"
            placeholder="Que horas você foi para a cama?"
            />

            <input
            id="hourToBed"
            name="hourToBed"
            on:change={handleChange}
            bind:value={$form.hourToBed}
            class="feedback-input"
            placeholder="Que horas você foi para a cama?"
            />

            <input
            id="hourToBed"
            name="hourToBed"
            on:change={handleChange}
            bind:value={$form.hourToBed}
            class="feedback-input"
            placeholder="Que horas você foi para a cama?"
            />

            <input
            id="hourToBed"
            name="hourToBed"
            on:change={handleChange}
            bind:value={$form.hourToBed}
            class="feedback-input"
            placeholder="Que horas você foi para a cama?"
            />

            <input
            id="hourToBed"
            name="hourToBed"
            on:change={handleChange}
            bind:value={$form.hourToBed}
            class="feedback-input"
            placeholder="Que horas você foi para a cama?"
            />

            <input type="submit" value="SALVAR"/>

    </form>
    
</div>