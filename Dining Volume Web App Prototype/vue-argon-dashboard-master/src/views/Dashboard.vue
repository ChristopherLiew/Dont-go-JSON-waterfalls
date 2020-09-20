<template>
    <div>
        <base-header type="gradient-success" class="pb-6 pb-8 pt-5 pt-md-8">
            <!-- Card stats -->
            <div class="row">
                <div class="col-xl-3 col-lg-6">
                    <stats-card title="Total Guests"
                                type="gradient-red"
                                sub-title="127"
                                icon="ni ni-circle-08"
                                class="mb-4 mb-xl-0"
                    >

                        <template slot="footer">
                            <span class="text-success mr-2"><i class="fa fa-arrow-up"></i> 11.89%</span>
                            <span class="text-nowrap">Versus Yesterday</span>
                        </template>
                    </stats-card>
                </div>
                <div class="col-xl-3 col-lg-6">
                    <stats-card title="Total Capacity"
                                type="gradient-orange"
                                sub-title="54"
                                icon="ni ni-shop"
                                class="mb-4 mb-xl-0"
                    >

                        <template slot="footer">
                            <span class="text-success mr-2"><i class="fa fa-arrow-up"></i> 25.50%</span>
                            <span class="text-nowrap">Versus Average</span>
                        </template>
                    </stats-card>
                </div>
                <div class="col-xl-3 col-lg-6">
                    <stats-card title="Vacancies"
                                type="gradient-pink"
                                sub-title="12"
                                icon="ni ni-air-baloon"
                                class="mb-4 mb-xl-0"
                    >

                        <template slot="footer">
                            <span class="text-danger mr-2"><i class="fa fa-arrow-down"></i> 19.72%</span>
                            <span class="text-nowrap">Versus Past Hour</span>
                        </template>
                    </stats-card>

                </div>
                <div class="col-xl-3 col-lg-6">
                    <stats-card title="Satisfaction"
                                type="gradient-info"
                                sub-title="89.97%"
                                icon="ni ni-satisfied"
                                class="mb-4 mb-xl-0"
                    >

                        <template slot="footer">
                            <span class="text-success mr-2"><i class="fa fa-arrow-up"></i> 15.65%</span>
                            <span class="text-nowrap">Versus Average</span>
                        </template>
                    </stats-card>
                </div>
            </div>
        </base-header>

        <!--Charts-->
        <div class="container-fluid mt--7">
            <div class="row">
                <div class="col-xl-6 mb-5 mb-xl-0">
                    <card type="default" header-classes="bg-transparent">
                        <div slot="header" class="row align-items-center">
                            <div class="col">
                                <h6 class="text-light text-uppercase ls-1 mb-1">Overview</h6>
                                <h5 class="h3 text-white mb-0">Sales value</h5>
                            </div>
                            <div class="col">
                                <ul class="nav nav-pills justify-content-end">
                                    <li class="nav-item mr-2 mr-md-0">
                                        <a class="nav-link py-2 px-3"
                                           href="#"
                                           :class="{active: bigLineChart.activeIndex === 0}"
                                           @click.prevent="initBigChart(0)">
                                            <span class="d-none d-md-block">Month</span>
                                            <span class="d-md-none">M</span>
                                        </a>
                                    </li>
                                    <li class="nav-item">
                                        <a class="nav-link py-2 px-3"
                                           href="#"
                                           :class="{active: bigLineChart.activeIndex === 1}"
                                           @click.prevent="initBigChart(1)">
                                            <span class="d-none d-md-block">Week</span>
                                            <span class="d-md-none">W</span>
                                        </a>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <line-chart
                                :height="350"
                                ref="bigChart"
                                :chart-data="bigLineChart.chartData"
                                :extra-options="bigLineChart.extraOptions"
                        >
                        </line-chart>

                    </card>
                </div>
                <!-- Restaurant Info Card -->
                <div class="col-xl-6">
                    <card header-classes="bg-transparent">
                        <div slot="header" class="row align-items-center">
                            <div class="col">
                                <h3 class="text-uppercase text-muted ls-1 mb-1">Les Bouchons · Steak House</h3>
                                <h3 style="color: #2dce89;">OPEN</h3>
                            </div>
                        </div>
                        <!-- Quick Links (Remember to link) -->
                        <div class="row justify-content-md-center">
                          <div class="col-md-auto">
                          <base-button type="info" icon="ni ni-world-2">Website</base-button>
                          </div>
                          <div class="col-md-auto">
                          <base-button type="success" icon="ni ni-square-pin">Directions</base-button>
                          </div>
                          <div class="col-md-auto">
                          <base-button type="danger" icon="ni ni-favourite-28">Save</base-button>
                          </div>
                        </div>
                        <br>
                        <div>
                          <!-- Restaurant Photos (Add Carousel?)-->
                          <div style>
                            <img id="restProfilePic" alt="Image placeholder" src="img/theme/les_bouchons_rest.png">
                          </div>
                        </div>

                        <!-- Restaurant Details -->
                        <br>
                        <div class="row">
                          <div class="col-md-auto">
                            <span class="h5 mb-0"><i class="ni ni-check-bold text-green"></i> Dine-In</span>
                          </div>
                          <div class="col-md-auto">
                            <span class="h5 mb-0"><i class="ni ni-check-bold text-green"></i> Take-Away</span>
                          </div>
                          <div class="col-md-auto">
                            <span class="h5 mb-0"><i class="ni ni-fat-remove text-red"></i> No-Contact Delivery</span>
                          </div>
                        </div>
                        <br>
                        <div class="row">
                          <div class="col-sm">
                            <span class="h4 mb-0">Address: </span><span class="p mb-0">60 Robertson Quay, #01-02, Singapore 238252</span>
                          </div>
                        </div>
                        <br>
                        <div class="row">
                          <div class="col-sm">
                            <span class="h4 mb-0">Hours: </span><span class="p mb-0"> 11 am ~ 11 pm</span><span class="h3 mb-0"> · </span><span class="p mb-0"> Mondays to Sundays</span>
                          </div>
                        </div>
                        <br>
                        <div class="row">
                          <div class="col-sm">
                            <span class="h4 mb-0">Phone: </span><span class="p mb-0">60 Robertson Quay, #01-02, Singapore 238252</span>
                          </div>
                        </div>
                        <br>
                        <div class="row">
                          <div class="col-sm">
                            <span class="h4 mb-0">Order: </span><span class="p mb-0">deliveroo.com.sg | foodpanda.sg</span>
                          </div>
                        </div>
                        <br>
                        <div class="row">
                          <div class="col-sm">
                            <span class="h4 mb-0">Pick a date to visit</span>
                          </div>
                        </div>
                      <div>
                        <base-input addon-left-icon="ni ni-calendar-grid-58">
                          <flat-picker slot-scope="{focus, blur}" @on-open="focus" @on-close="blur" :config="{allowInput: true, enableTime: true, altInput: true, altFormat: 'F j, Y H:i',dateFormat: 'Y-m-d H:i'}" class="form-control datepicker" v-model="dates.simple">
                          </flat-picker>
                        </base-input>
                      </div>
                        <base-button type="danger" icon="ni ni-check-bold" >Reserve Now</base-button>
                    </card>
                </div>
            </div>
            <!-- End charts-->

            <!--Tables-->
            <div class="row mt-5">
                <div class="col-xl-12 mb-5 mb-xl-0">
                    <RestaurantNotifsTable></RestaurantNotifsTable> <!-- Change to Latest Reviews -->
                </div>
            </div>
            <!--End tables-->
        </div>

    </div>
</template>
<script>
  // Date Input
  import flatPicker from "vue-flatpickr-component";
  import "flatpickr/dist/flatpickr.css";

  // Charts
  import * as chartConfigs from '@/components/Charts/config';
  import LineChart from '@/components/Charts/LineChart';

  // Tables
  import RestaurantNotifsTable from './Dashboard/RestaurantNotifsTable';

  export default {
    components: {
      LineChart,
      RestaurantNotifsTable,
      flatPicker
    },
    data() {
      return {
        bigLineChart: {
          allData: [
            [0, 20, 10, 30, 15, 40, 20, 60, 60],
            [0, 20, 5, 25, 10, 30, 15, 40, 40]
          ],
          activeIndex: 0,
          chartData: {
            datasets: [],
            labels: [],
          },
          extraOptions: chartConfigs.blueChartOptions,
        },
        redBarChart: {
          chartData: {
            labels: ['Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
            datasets: [{
              label: 'Sales',
              data: [25, 20, 30, 22, 17, 29]
            }]
          }
        },
        dates: {
            simple: "2020-09-15"
          }
      };
    },
    methods: {
      initBigChart(index) {
        let chartData = {
          datasets: [
            {
              label: 'Performance',
              data: this.bigLineChart.allData[index]
            }
          ],
          labels: ['May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
        };
        this.bigLineChart.chartData = chartData;
        this.bigLineChart.activeIndex = index;
      }
    },
    mounted() {
      this.initBigChart(0);
    }
  };
</script>
<style>
#restProfilePic {
  width: 100%;
  height: 100%;
}
div span {
  font-size: 10pt;
}
</style>
