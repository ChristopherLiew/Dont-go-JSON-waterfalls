<template>
    <div>              
            
         <base-header class="header pb-8 pt-5 pt-lg-8 d-flex"
                     style="min-height: 1000px; background-image: url(img/theme/profile-cover.jpg); 
                     background-size: cover; background-position: center top;">
            <!-- Mask -->
            <span class="mask bg-gradient-success opacity-8"></span>
            <div class="row justify-content-center">
                <div class="col-sm-8">
                    <div class="card bg-secondary shadow border-0">
                     <div class="card-header bg-transparent pb-5">
                        <img :src="logo" class="thankyoulogo" alt="...">
                            <div class="text-center mt-2 mb-3"><h1 style=font-size:40px>We've received your order!</h1></div>
                                
                                <hr>
                                <div style = margin-left:120px>
                               
                                    <h3 style=font-size:20px>Order Details:</h3>
                                    <div class = "row">
                                        <div class="col-sm-6" style=font-weight:bold>Order No:</div>
                                        <div class="col-sm-6" style=font-weight:bold>Order Date & Time:</div>
                                    </div>

                                    <div class = "row">
                                        <div class="col-sm-6">#12342243958938420</div>
                                        <div class="col-sm-6">17 September 2020, 18:00</div>
                                        
                                    </div>

                                    <p></p>
                                    <div class = "row">
                                        <div class="col-sm-6" style=font-weight:bold>Order for:</div>
                                        <div class="col-sm-6" style=font-weight:bold>Order Type:</div>
                                        
                                    </div>

                                    <div class = "row">
                                        <div class="col-sm-6" >Chris Liew</div>
                                        <div class="col-sm-6" style=font-weight:bold>Reservation:<span style=font-weight:normal>Yes</span></div>
                                        
                                    </div>

                                    <div class = "row">
                                        <div class="col-sm-6">+653249242</div>
                                        <div class="col-sm-6" style=font-weight:bold>Number of People:<span style=font-weight:normal> 5 </span></div>
                                        
                                    </div>

                                    <div class = "row">
                                        <div class="col-sm-6">chrisliew@gmail.com</div>
                                        <div class="col-sm-6" style=font-weight:bold> Ready-Time:<span style=font-weight:normal> 20 minutes </span></div>
                                    </div>
                                    <p></p>
                                    <div class = "row">
                                        <div class="col-sm-6" style=font-weight:bold>Payment:<span style=font-weight:normal> Mastercard **********678</span></div>
                                        <div class="col-sm-6"> </div>
                                    </div>
                                    
                                    <p></p>
                                   
                                </div> 

                                <h3 style=margin-left:120px;font-size:20px>Order Summary:</h3>
                                <hr>
                                <div style = margin-left:120px>
                                   
                                    <div class = "row">
                                        <div class = "col-sm-4">
                                            <img :src="salad" class="foodchoosen" alt="..."></div>
                                        <div class = "col-sm-6">
                                            <div class= "NameFood">Caesar Salad</div>
                                        
                                            Description: No eggs and onions
                                            <br />
                                            Price: $18.00
                                            <br />
                                            Quantity: 1
                                            <br/>
                                            <br/>
                                            <p class="qty" align= right> $18.00 </p>
                                        
                                            
                                        </div>
                    
                                    </div>

                                    

                                    <div class = "row">
                                        <div class = "col-sm-4">
                                            <img :src="steak" class="foodchoosen" alt="..."></div>
                                        <div class = "col-sm-6">
                                            <div class= "NameFood">Ribeye Steak</div>
                                            
                                            Description: Medium Rare
                                            <br />
                                            Price: $25.00
                                            <br />
                                            Quantity: 3
                                            <br/>
                                            <br/>
                                            <p class="qty" align= right>$75.00 </p>
                                            
                                        </div>
                                    </div>

                                    <div class = "row">
                                        <div class = "col-sm-4">
                                            <span class= "price"> Sub-Total:
                                            <br/> Service Charge: 
                                            <br/> Tax:
                                            <p class ="NameFood">Total: </p>
                                            </span>
                                        </div>
                                        <div class = "col-sm-6">
                                            <p class="qty" align= right>$83.00 
                                            <br/> $5.00
                                            <br/> $8.00
                                            <br/> $96.00
                                            </p>
                                        </div>
                                    </div>
                                </div>
                            
                        </div>
                    </div>
                </div>
            </div>
        </base-header>
    </div>
</template>

<script>
 export default {
    name: 'sidebar',
    props: {
      logo: {
        type: String,
        default: 'img/brand/success.png',
        description: 'tick mark'
      },
      salad: {
        type: String,
        default: 'img/brand/Caesar_Salad.jpg',
        description: 'salad'
      },
      steak: {
        type: String,
        default: 'img/brand/Ribeye_Steak.jpg',
        description: 'steak'
      }
    }
 }
</script>

<style>
.thankyoulogo {
    height:50px;
    width:50px;
   
    display: block;
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 20px;
    
}

.order {
    color: #525f7f;
    font-weight: bold;
}

.foodchoosen {
    height:90%;
    width:90%;
    float:left;
 
    margin-bottom: 20px;

}

.center {
    margin-left: auto;
    margin-right: auto;
    border: 3px solid #73AD21;
    padding: 10px;
}

.demotext {
    float: left ;
}

.NameFood {
    font-weight:bold;
    font-size:20px;
}

.qty {
    font-weight:bold;
}

#just-line-break {
  white-space: pre-line;
}

#line-break-and-tab {
  white-space: pre-wrap;
}

.price{
    font-size:18px;
   
}


</style>