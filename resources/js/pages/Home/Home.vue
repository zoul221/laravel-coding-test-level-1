<template>
    <div >
        <div class="container" style="padding-top:40vh">

            <div class="justify-content-center text-white" style="text-align:center;">
                <h3 >We're an event management, but we're also loves random dad jokes!</h3>
                <p >Click on the button to get a random dad jokes!</p>
                <button type="button" style="margin:auto;" class="btn btn-primary m-1" @click="fetchRandomJokes()">I want dad jokes!</button>
                <div v-if="getJokeSuccess" style="margin:2rem;">
                    <h4>{{randomJoke.setup}}</h4>
                    <h4 > {{randomJoke.punchline}} </h4>
                </div>
            </div>
        </div>
        
            <svg id="logo" width="1192" height="113" viewBox="0 0 1192 113" fill="none" xmlns="http://www.w3.org/2000/svg">
            <mask id="path-1-outside-1_202_4" maskUnits="userSpaceOnUse" x="0.439575" y="0.479996" width="1192" height="113" fill="black">
            <rect fill="white" x="0.439575" y="0.479996" width="1192" height="113"/>
            <path d="M18.5436 17.288V50.84H55.1196V61.64H18.5436V96.2H59.4396V107H5.43958V6.488H59.4396V17.288H18.5436Z"/>
            <path d="M162.212 6.632L124.34 107H109.22L71.3477 6.632H85.3157L116.852 93.176L148.388 6.632H162.212Z"/>
            <path d="M189.684 17.288V50.84H226.26V61.64H189.684V96.2H230.58V107H176.58V6.488H230.58V17.288H189.684Z"/>
            <path d="M329.32 107H316.216L263.512 27.08V107H250.408V6.488H263.512L316.216 86.264V6.488H329.32V107Z"/>
            <path d="M413.434 6.632V17.288H386.074V107H372.97V17.288H345.466V6.632H413.434Z"/>
            <path d="M484.285 48.68V59.768H426.829V48.68H484.285Z"/>
            <path d="M610.685 7.352V107H597.581V32.696L564.461 107H555.245L521.981 32.552V107H508.877V7.352H522.989L559.853 89.72L596.717 7.352H610.685Z"/>
            <path d="M692.236 84.68H648.46L640.396 107H626.572L662.86 7.208H677.98L714.124 107H700.3L692.236 84.68ZM688.492 74.024L670.348 23.336L652.204 74.024H688.492Z"/>
            <path d="M808.852 107H795.748L743.044 27.08V107H729.94V6.488H743.044L795.748 86.264V6.488H808.852V107Z"/>
            <path d="M890.518 84.68H846.742L838.678 107H824.854L861.142 7.208H876.262L912.406 107H898.582L890.518 84.68ZM886.774 74.024L868.63 23.336L850.486 74.024H886.774Z"/>
            <path d="M1004.25 35.72C1001.47 29.864 997.437 25.352 992.157 22.184C986.877 18.92 980.733 17.288 973.725 17.288C966.717 17.288 960.381 18.92 954.717 22.184C949.149 25.352 944.733 29.96 941.469 36.008C938.301 41.96 936.717 48.872 936.717 56.744C936.717 64.616 938.301 71.528 941.469 77.48C944.733 83.432 949.149 88.04 954.717 91.304C960.381 94.472 966.717 96.056 973.725 96.056C983.517 96.056 991.581 93.128 997.917 87.272C1004.25 81.416 1007.95 73.496 1009 63.512H968.973V52.856H1022.97V62.936C1022.2 71.192 1019.61 78.776 1015.2 85.688C1010.78 92.504 1004.97 97.928 997.773 101.96C990.573 105.896 982.557 107.864 973.725 107.864C964.413 107.864 955.917 105.704 948.237 101.384C940.557 96.968 934.461 90.872 929.949 83.096C925.533 75.32 923.325 66.536 923.325 56.744C923.325 46.952 925.533 38.168 929.949 30.392C934.461 22.52 940.557 16.424 948.237 12.104C955.917 7.688 964.413 5.48 973.725 5.48C984.381 5.48 993.789 8.11999 1001.95 13.4C1010.2 18.68 1016.2 26.12 1019.95 35.72H1004.25Z"/>
            <path d="M1053.4 17.288V50.84H1089.98V61.64H1053.4V96.2H1094.3V107H1040.3V6.488H1094.3V17.288H1053.4Z"/>
            <path d="M1166.98 107L1143.07 65.96H1127.23V107H1114.13V6.632H1146.53C1154.11 6.632 1160.5 7.928 1165.68 10.52C1170.96 13.112 1174.9 16.616 1177.49 21.032C1180.08 25.448 1181.38 30.488 1181.38 36.152C1181.38 43.064 1179.36 49.16 1175.33 54.44C1171.39 59.72 1165.44 63.224 1157.47 64.952L1182.67 107H1166.98ZM1127.23 55.448H1146.53C1153.63 55.448 1158.96 53.72 1162.51 50.264C1166.06 46.712 1167.84 42.008 1167.84 36.152C1167.84 30.2 1166.06 25.592 1162.51 22.328C1159.06 19.064 1153.73 17.432 1146.53 17.432H1127.23V55.448Z"/>
            </mask>
            <path d="M18.5436 17.288V50.84H55.1196V61.64H18.5436V96.2H59.4396V107H5.43958V6.488H59.4396V17.288H18.5436Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            <path d="M162.212 6.632L124.34 107H109.22L71.3477 6.632H85.3157L116.852 93.176L148.388 6.632H162.212Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            <path d="M189.684 17.288V50.84H226.26V61.64H189.684V96.2H230.58V107H176.58V6.488H230.58V17.288H189.684Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            <path d="M329.32 107H316.216L263.512 27.08V107H250.408V6.488H263.512L316.216 86.264V6.488H329.32V107Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            <path d="M413.434 6.632V17.288H386.074V107H372.97V17.288H345.466V6.632H413.434Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            <path d="M484.285 48.68V59.768H426.829V48.68H484.285Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            <path d="M610.685 7.352V107H597.581V32.696L564.461 107H555.245L521.981 32.552V107H508.877V7.352H522.989L559.853 89.72L596.717 7.352H610.685Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            <path d="M692.236 84.68H648.46L640.396 107H626.572L662.86 7.208H677.98L714.124 107H700.3L692.236 84.68ZM688.492 74.024L670.348 23.336L652.204 74.024H688.492Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            <path d="M808.852 107H795.748L743.044 27.08V107H729.94V6.488H743.044L795.748 86.264V6.488H808.852V107Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            <path d="M890.518 84.68H846.742L838.678 107H824.854L861.142 7.208H876.262L912.406 107H898.582L890.518 84.68ZM886.774 74.024L868.63 23.336L850.486 74.024H886.774Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            <path d="M1004.25 35.72C1001.47 29.864 997.437 25.352 992.157 22.184C986.877 18.92 980.733 17.288 973.725 17.288C966.717 17.288 960.381 18.92 954.717 22.184C949.149 25.352 944.733 29.96 941.469 36.008C938.301 41.96 936.717 48.872 936.717 56.744C936.717 64.616 938.301 71.528 941.469 77.48C944.733 83.432 949.149 88.04 954.717 91.304C960.381 94.472 966.717 96.056 973.725 96.056C983.517 96.056 991.581 93.128 997.917 87.272C1004.25 81.416 1007.95 73.496 1009 63.512H968.973V52.856H1022.97V62.936C1022.2 71.192 1019.61 78.776 1015.2 85.688C1010.78 92.504 1004.97 97.928 997.773 101.96C990.573 105.896 982.557 107.864 973.725 107.864C964.413 107.864 955.917 105.704 948.237 101.384C940.557 96.968 934.461 90.872 929.949 83.096C925.533 75.32 923.325 66.536 923.325 56.744C923.325 46.952 925.533 38.168 929.949 30.392C934.461 22.52 940.557 16.424 948.237 12.104C955.917 7.688 964.413 5.48 973.725 5.48C984.381 5.48 993.789 8.11999 1001.95 13.4C1010.2 18.68 1016.2 26.12 1019.95 35.72H1004.25Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            <path d="M1053.4 17.288V50.84H1089.98V61.64H1053.4V96.2H1094.3V107H1040.3V6.488H1094.3V17.288H1053.4Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            <path d="M1166.98 107L1143.07 65.96H1127.23V107H1114.13V6.632H1146.53C1154.11 6.632 1160.5 7.928 1165.68 10.52C1170.96 13.112 1174.9 16.616 1177.49 21.032C1180.08 25.448 1181.38 30.488 1181.38 36.152C1181.38 43.064 1179.36 49.16 1175.33 54.44C1171.39 59.72 1165.44 63.224 1157.47 64.952L1182.67 107H1166.98ZM1127.23 55.448H1146.53C1153.63 55.448 1158.96 53.72 1162.51 50.264C1166.06 46.712 1167.84 42.008 1167.84 36.152C1167.84 30.2 1166.06 25.592 1162.51 22.328C1159.06 19.064 1153.73 17.432 1146.53 17.432H1127.23V55.448Z" stroke="white" stroke-width="10" mask="url(#path-1-outside-1_202_4)"/>
            </svg>
        
    </div>
</template>

<script>
export default {
    name:'Home',
    data(){
            return{
                randomJoke:{
                    type: Object,
                },
                getJokeSuccess:false,
            };
    },
    methods:{
        fetchRandomJokes:async function(id){
            this.getJokeSuccess=false;
            const options = {
                method: 'GET',
                url: 'https://dad-jokes.p.rapidapi.com/random/joke',
                headers: {
                    'X-RapidAPI-Key': 'Get-your-own-api',
                    'X-RapidAPI-Host': 'dad-jokes.p.rapidapi.com'
            }
            };
            await axios.request(options).then((response)=>
            {
                if(response.data.success){
                    this.randomJoke = response.data.body[0];
                    this.getJokeSuccess=true;
                }
                

            }).catch(err => console.log(err));

        },
    }
}
</script>

<style>

</style>
