<template>
    <div class="right-block">
        <div class="right-block__top h-25">
            <div class="charts-container-wrapper h-100">
                <div class="row">
                    <div class="col-4">
                        <div class="age-container-chart">
                            <DoughnutChart
                            chart-title="Возраст"/>
                        </div>
                    </div>
                    <div class="col-4">
                        <div class="sex-container-chart">
                            <DoughnutChart
                            chart-title="Пол"/>
                        </div>
                    </div>
                    <div class="col-4">
                        <div class="cash-container-chart">
                            <DoughnutChart
                            chart-title="Уровень дохода"/>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="right-block__bottom h-75">
            <div class="groups-container h-100">
                <div class="groups-container-header">
                    <span class="group-container-header__text">
                        Площадки
                    </span>
                </div>
                <div class="groups-container-sites-wrapper">
                    <ul class="groups-container-sites">
                        <li class="group-container-site active">
                            <span class="group-container-site__text">
                                Вконтакте
                            </span>
                        </li>
                        <li class="group-container-site">
                            <span class="group-container-site__text">
                                Телеграм
                            </span>
                        </li>
                        <li class="group-container-site">
                            <span class="group-container-site__text">
                                Яндекс.Дзен
                            </span>
                        </li>
                        <li class="group-container-site">
                            <span class="group-container-site__text">
                                YouTube
                            </span>
                        </li>
                    </ul>
                </div>
                <div class="groups-container-info">
                    <!-- <ag-grid-vue
                        style="width: 100%; height: 200px"
                        :columnDefs="columnDefs"
                        :rowData="rowData"
                        >
                    </ag-grid-vue> -->
                    <table class="table">
                        <thead>
                            <tr>
                                <th scope="col">name</th>
                                <th scope="col">URL</th>
                                <th scope="col">Подписчики</th>
                                <th scope="col">Охват</th>
                                <th scope="col">Стоимость</th>
                                <th scope="col">Соответствие</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <th scope="row">1</th>
                                <td>Mark</td>
                                <td>Otto</td>
                                <td>@mdo</td>
                            </tr>
                            <tr>
                                <th scope="row">2</th>
                                <td>Jacob</td>
                                <td>Thornton</td>
                                <td>@fat</td>
                            </tr>
                                <tr>
                                <th scope="row">3</th>
                                <td colspan="2">Larry the Bird</td>
                                <td>@twitter</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
import DoughnutChart from '@/components/doughnutChart.vue'
// import { AgGridVue } from "ag-grid-vue3";

import "ag-grid-community/dist/styles/ag-grid.css";
import "ag-grid-community/dist/styles/ag-theme-alpine.css";

export default {
    name: 'RightBlock',
    components: {
        DoughnutChart,
        // AgGridVue
    },
    setup() {
        return {
        columnDefs: [
            { headerName: " ", field: "name" },
            { headerName: "URL", field: "url" },
            { headerName: "Подписчики", field: "subscribers" },
            { headerName: "Лайки", field: "likes" },
            { headerName: "Репосты", field: "reposts" },
            { headerName: "Комментарии", field: "comments" },
            { headerName: "Стоимость", field: "cost" },
            { headerName: "Соответствие", field: "define" },
        ],
        rowData: [
            { name: "Netflix", url: "https://vk.com/tvnetflix", subscribers: 35000, likes: 3500, reposts: 3500, comments:100, cost: 10000, define: "54%"},
            { name: "Читающие", url: "https://vk.com/tvnetflix", subscribers: 35000, likes: 3500, reposts: 3500, comments:100, cost: 10000, define: "54%"},
            { name: "Импровизация", url: "https://vk.com/tvnetflix", subscribers: 35000, likes: 3500, reposts: 3500, comments:100, cost: 10000, define: "54%"},
            { name: "Toyota club", url: "https://vk.com/tvnetflix", subscribers: 35000, likes: 3500, reposts: 3500, comments:100, cost: 10000, define: "54%"},
            { name: "Группа по интересам", url: "https://vk.com/tvnetflix", subscribers: 35000, likes: 3500, reposts: 3500, comments:100, cost: 10000, define: "54%"},
        ],
        };
    },
}
</script>

<style scoped>
/* .right-block__top {

} */
.right-block__bottom {
    padding: 10px 0 10px 0;
}
.charts-container-wrapper {
    border-radius : 10px;
    background: #fff;
    display: flex;
    justify-content : center;
    align-items : center;
}
.groups-container{
    border-radius: 10px;
    background-color: #fff;
}
.groups-container-header {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    height: 40px;
    /* border: 1px solid red; */
}
.group-container-header__text {
    padding-left: 15px;
}
.groups-container-sites {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding: 0;
    margin: 0;
    height: 40px;
}
.group-container-site {
    list-style-type: none;
    margin-left: 15px;
    background-color: #F5F5F5;
    border-radius: 5px;
    padding: 5px;
}
.group-container-site.active {
    background-color: rgb(1, 76, 152);
    opacity: 0.7;
    color: white;
}
.groups-container-info {
    margin-top: 10px;
    height: calc(100%-80px);
}

</style>


                    <!-- <div class="row groups-container-info-headers">
                        <div class="col"></div>
                        <div class="col">URL</div>
                        <div class="col">Подписчики</div>
                        <div class="col">Лайки</div>
                        <div class="col">Репосты</div>
                        <div class="col">Комментарии</div>
                        <div class="col">Стоимость</div>
                        <div class="col">Соответствие</div>
                    </div>
                    <hr>
                    <div class="row groups-container-info-content">
                        <div class="col">Netflix</div>
                        <div class="col">https://vk.com/tvnetflix</div>
                        <div class="col">Подписчики</div>
                        <div class="col">Лайки</div>
                        <div class="col">Репосты</div>
                        <div class="col">Комментарии</div>
                        <div class="col">Стоимость</div>
                        <div class="col">Соответствие</div>
                    </div> -->