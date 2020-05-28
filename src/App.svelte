<script>

    import Icon from 'svelte-awesome';
    import { beer, refresh, comment, codeFork, camera, ban } from 'svelte-awesome/icons';
    import Datepicker from "svelte-calendar";
    import dayjs from "dayjs"
    
    const daysOfWeek = [
    [ 'Domingo', 'Dom' ],
    [ 'Segunda', 'Seg' ],
    [ 'Terça', 'Ter' ],
    [ 'Quarta', 'Qua' ],
    [ 'Quinta', 'Qui' ],
    [ 'Sexta', 'Sex' ],
    [ 'Sábado', 'Sáb' ],
  ];
  const monthsOfYear = [
    [ 'Janeiro', 'Jan' ],
    [ 'Fevereiro', 'Fev' ],
    [ 'Março', 'Mar' ],
    [ 'Abril', 'Abr' ],
    [ 'Maio', 'Mai' ],
    [ 'Junho', 'Jun' ],
    [ 'Julho', 'Jul' ],
    [ 'Agosto', 'Ago' ],
    [ 'Setembro', 'Set' ],
    [ 'Outubro', 'Out' ],
    [ 'Novembro', 'Nov' ],
    [ 'Dezembro', 'Dez' ],
  ];

  let dateChosen = null;

</script>

<main>
    <div class="container vh-70">
        <div class="panel wd-100"> 
            
        </div>
    </div>
    <div class="container opacity-80 vh-30">
        <div class="panel wd-100">
        <div class="wd-25"> 
                <Datepicker
                    format={date => dayjs(date).format('DD/MM/YYYY')}
                    buttonBackgroundColor='#e20074'
                    buttonTextColor='white'
                    highlightColor='#e20074'
                    dayBackgroundColor='#efefef'
                    dayTextColor='#333'
                    dayHighlightedBackgroundColor='#e20074'
                    dayHighlightedTextColor='#fff'
                    daysOfWeek={daysOfWeek}
                    monthsOfYear={monthsOfYear}
                    bind:dateChosen
                >
                </Datepicker>        
            </div>
            <div class="wd-25">
                <Icon data={beer} scale="2"/>
            </div>
            <div class="wd-25">
                <Icon data={beer} scale="2"/>
            </div>
            <div class="wd-25">
                <Icon data={beer} scale="2"/>
            </div>
        </div>
    </div>
              


        
</main>

<style>

    .container {
        display: flex;
        color: white;
    }

    .panel {
        display: flex;
        background-color: #313040a8;
        margin: 10px;
        text-align: center;
        line-height: 75px;
        font-size: 30px;
        font-weight: bold;
    }

    .opacity-80 {
        opacity: 0.8;
    }

    .wd-100 {
        width:100%;
    }

    .wd-70 {
        width:70%;
    }

    .wd-50 {
        width:50%;
    }

    .wd-25 {
        width:25%;
    }

    .vh-70 {
        height: 70vh;
    }
    
    .vh-30 {
        height: 30vh;
    }

</style>