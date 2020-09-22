<template>
    <div>

        <base-header type="gradient-success" class="pb-6 pb-8 pt-5 pt-md-8">
        <div style=margin-left:2%><h1 style=font-size:50px>Find Places!</h1></div>
        <div class ="row">
        <div class="col-sm-3">
            <input
            type="text"
            background= "https://cdn4.iconfinder.com/data/icons/36-slim-icons/87/calender.png"
            placeholder="Location"
            class="trial">
        </div>
        <div class="col-sm-2">
            <multiselect v-model="value" :options="options" :multiple="true" placeholder="Number of Seaters"></multiselect>
        </div>

        <div class="col-sm-2">
            <multiselect v-model="value1" :options="options1" :multiple="true" placeholder="Price Range" style=font-size:20px ></multiselect>
        </div>

        <div class="col-sm-2">
           <multiselect v-model="value2" :options="options2" :multiple="true" placeholder= "Lvl of Crowdedness"></multiselect>
        </div>

        <div class="col-sm-3">
            <multiselect v-model="value3" :options="options3" :multiple="true" placeholder = "Measures of Precaution"></multiselect>
        </div>
        </div>
        <p></p>
        <p></p>
        <hr>
        <div class = "row">
        <div class = "col-sm-7">
            <img :src="maps" style="width:100%" alt="...">
        </div>
        <div class = "col-sm-5">
        
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
                            <img id="restProfilePic" alt="Image placeholder" src="img/theme/les_bouchons_rest.png" style= width:100%>
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
                        <p></p>
                        <div class="row">
                      <div class="col-lg">
                        <base-input addon-left-icon="ni ni-calendar-grid-58">
                          <flat-picker slot-scope="{focus, blur}" @on-open="focus" @on-close="blur" :config="{allowInput: true, enableTime: true, altInput: true, altFormat: 'F j, Y H:i',dateFormat: 'Y-m-d H:i'}" class="form-control datepicker" v-model="dates.simple">
                          </flat-picker>
                        </base-input>
                      </div>
                      <div class="col-lg">
                        <base-dropdown>
                          <base-button v-model="pax" icon="ni ni-single-02" slot="title" type="primary" class="dropdown-toggle">{{pax}}</base-button>
                              <a class="dropdown-item" @click="updatePax('1 Pax')">1 Pax</a>
                              <a class="dropdown-item" @click="updatePax('2 Pax')">2 Pax</a>
                              <a class="dropdown-item" @click="updatePax('3 Pax')">3 Pax</a>
                              <a class="dropdown-item" @click="updatePax('4 Pax')">4 Pax</a>
                              <a class="dropdown-item" @click="updatePax('5 Pax')">5 Pax</a>
                          </base-dropdown>
                      </div>
                        </div>
                      <br>
                        <div class="col-sm">
                        <base-button block type="danger" icon="ni ni-check-bold" >Reserve Now</base-button>
                      </div>
                    </card>
                
            </div>
        
        </div>
        
        
        </base-header>
        
        
        

      
        

        
    </div>
</template>
<script>
import Multiselect from 'vue-multiselect'

export default {
    // OR register locally
    components: { Multiselect },
    data () {
      return {
        value: [],
        options: ['3 seaters', '4 seaters', '5 seaters'],
        value1: [],
        options1: ['$5-10','$10-25','$25-50'],
        value2: [],
        options2: ['Low','Moderate','High'],
        value3: [],
        options3: ['Low','Moderate','High']
        
      }
    },
    props: {
      maps: {
        type: String,
        default: 'img/brand/mapspinning.jfif',
        description: 'tick mark'
      }
  }
}
</script>
<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>
<style>


.trial {
    margin-left:10%;
  border-radius: 20px;
  padding: 10px;
  width: 90%;
  
padding-left:30px;
  background-color: white;
  border: 2px solid #4CAF50;
  color: black;
  outline: none; /* removes the outer border when button is in focus */
  text-align: left;
  font-size:20px;
  
}

.multiselect__tags {
    border-radius: 20px;
    font-size: 18px;
}


</style>
