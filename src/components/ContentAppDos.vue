<template>
  <div class="container">
    <div id="app" class="container">
      <div class="text-right"><button class="btn btn-primary" data-toggle="modal" data-target="#cartModal">Cart ({{totalItems}})</button></div>
      
      <!-- Modal --> 
      <div class="modal fade" id="cartModal" tabindex="-1" role="dialog" aria-labelledby="myModalLabel">
          <div class="modal-dialog" role="document">
            <div class="modal-content">
                <div class="modal-header">
                  <button type="button" class="close" data-dismiss="modal" aria-label="Close">          
                    <span aria-hidden="true">&times;</span></button>
                  <h4 class="modal-title" id="myModalLabel">Cart</h4>
                </div>
                <div class="modal-body">
                  <shopping-cart inline-template :items="cartItems">
                      <div>
                        <table class="table table-cart">
                            <tr v-for="(item, index) in items">
                              <td>{{item.title}}</td>
                              <td style="width:120px">QTY:
                                  <input v-model="item.qty" class="form-control input-qty" type="number" min="1">
                              </td>
                              <td class="text-right">${{item.price | formatCurrency}}</td>
                              <td>
                                  <button @click="removeItem(index)"><span class="glyphicon glyphicon-trash"></span></button>
                              </td>
                            </tr>
                            <tr v-show="items.length === 0">
                              <td colspan="4" class="text-center">Cart is empty</td>
                            </tr>
                            <tr v-show="items.length > 0">
                              <td></td>
                              <td class="text-right">Cart Total</td>
                              <td class="text-right">${{Total | formatCurrency}}</td>
                              <td></td>
                            </tr>
                        </table>
                      </div>
                      <!-- /.container -->
                  </shopping-cart>
                </div>
                <div class="modal-footer">
                  <button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
                </div>
            </div>
          </div>
      </div>
      
      <div class="container">
          <div class="row">
            <div class="col-xs-3 text-center" v-for="item in items">
                <img class="img-responsive" :src="item.image" alt="">
                <h5>{{ item.title }}</h5>
                <h6>${{ item.price | formatCurrency }}</h6>
                <p class="text-center"><input v-model="item.qty" type="number" class="form-control" placeholder="Qty" min="1"/></p>
                  
                  <button @click="addToCart(item)" class="btn btn-sm btn-primary">Add to Cart</button>
                </p>
            </div>
          </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: "App",
  components: {

  },
};
</script>