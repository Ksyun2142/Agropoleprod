<template>
<div class="center">
<table >
    <tr>
        <td align="center"><router-link :to="{ name:  'tree'}"><img src="../assets/images/main/plan_factor_analis.png" width="200"  height="200"><br>ПЛАН-ФАКТНЫЙ АНАЛИЗ<br>ПРОИЗВОДСТВЕННЫХ ЗАТРАТ</router-link></td>
        <td align="center"><router-link :to="{ name:  'tree'}"><img src="../assets/images/main/costs_kultures.png" width="200"  height="200"><br>ДЕТАЛИЗАЦИЯ <br>ЗАТРАТ ПО КУЛЬТУРАМ</router-link></td>
        <td align="center"><router-link :to="{ name:  'tree'}"><img src="../assets/images/main/map.png" width="200"  height="200"><br>КАРТА</router-link></td>
    </tr>
    <tr>
        <td align="center"><router-link :to="{ name: 'two' }"><img src="../assets/images/main/tasks_productions.png" width="200"  height="200"><br>ПРОИЗВОДСТВЕННЫЕ<br>ЗАДАЧИ</router-link></td>
        <td align="center"><router-link :to="{ name: 'one' }"> <img src="../assets/images/main/planning.png" width="200"  height="200"><br>ПЛАНИРОВАНИЕ</router-link></td>
        <td align="center"><router-link :to="{ name:  'tree'}"><img src="../assets/images/main/tr1.png" width="160"  height="160"><br>АГРОГАРАЖ</router-link></td>
    </tr>
    <tr>
        <td colspan="3" align="center"><router-link :to="{ name:  'tree'}"><img src="../assets/images/main/adminBig.png" width="75"  height="75"><br>АДМИНИСТРИРОВАНИЕ</router-link></td>
    </tr>
</table>
</div>
</template>

<style scoped>
.center{
   margin: auto;
   max-width:1000px;
   margin-top:5%;

}

td{
padding:30px;
}
.main-menu-btn {
    }
    a{
    width: 300px;
  /*  height: 300px; */
    height: 250px;
    display: inline-block;
    font-family: DINPro-Medium;
    padding: 10px 15px 0px 15px;
    background-color: transparent;
    font-size: 16px;
    text-align:center;
    color: #ffffff;
    border: 0;
    }
</style>
