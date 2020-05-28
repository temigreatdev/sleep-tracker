
  <script>
    import { createForm } from "svelte-forms-lib";

    const { form, handleChange, handleSubmit } = createForm({
      initialValues: {
        date:"",
        hourToBed: "",
        hourLightsOff: "",
        timeToStartSleepInMinutes: 0,
        timesAwakedDuringSleep: 0,
        totalTimeAwakedDuringSleepInHours:0,
        hourAwaked:"",
        hourGoOffTheBed:"",
        totalHoursOfSleepLastNight:""
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

  <form on:submit={handleSubmit}>
    <label for="hourToBed">Que horas você foi para a cama?</label>
    <input
      id="hourToBed"
      name="hourToBed"
      on:change={handleChange}
      bind:value={$form.hourToBed}
    />

    <label for="name">name</label>
    <input
      id="name"
      name="name"
      on:change={handleChange}
      bind:value={$form.name}
    />

    <label for="email">email</label>
    <input
      id="email"
      name="email"
      on:change={handleChange}
      bind:value={$form.email}
    />

    <button type="submit">Submit</button>
  </form>
