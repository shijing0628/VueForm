<template>
  <div>
    <h3>Payment</h3>
    <form novalidate @submit.prevent="onSave()">
      <div class="row">
        <div class="col-md-6">
          <div><strong>Shipping Information</strong></div>
          <div class="form-group">
            <label for="fullName">Name</label>
            <input
              type="text"
              id="name"
              class="form-control"
              placeholder="your name"
              v-model="payment.fullName"
            />
          </div>
          <div class="form-group">
            <label for="company">Company Name</label>
            <input
              type="text"
              id="company"
              class="form-control"
              placeholder="company"
              v-model="payment.company"
            />
          </div>
          <div class="form-group">
            <label for="address1">Address1</label>
            <input
              type="text"
              id="Address1"
              class="form-control"
              placeholder="street address"
              v-model="payment.address1"
            />
          </div>
          <div class="form-group">
            <label for="address2">Address2</label>
            <input
              type="text"
              id="Address2"
              class="form-control"
              placeholder="street address"
              v-model="payment.address2"
            />
          </div>
         <div class="form-row">
            <div class="form-group col-md-6" >
              <label for="cityTown">City</label>
              <input
                type="text"
                id="cityTown"
                class="form-control"
                placeholder="e.g. new York"
                v-model="payment.cityTown"
              />
            </div>
             <div class="form-group col-md-3">
              <label for="stateProvince">State</label>
              <select
                id="stateProvince"
                class="form-control"
                v-model="payment.stateProvince"   
              >
              <option v-for="s in states" :key="s.abbreviation" :value="s.abbreviation">{{s.name}}</option>
              </select>
            </div>
            <div class="form-group col-md-3">
              <label for="">ZipCode</label>
              <input
                type="text"
                id="postalCode"
                class="form-control"
                placeholder="e.g.10101"
                v-model="payment.postalCode"  
              />
            </div>
         </div>
         <div class="form-group">
          <input type="submit" value="Next" class="btn btn-success"/>
         </div>
        </div>
        <div class="col-md-6">
          <div><strong>Billing Information</strong></div>
        </div>
      </div>
    </form>
    <div><pre>{{payment}}</pre></div>
  </div>
</template>

<script>
import {ref} from "vue";
import states from "./lookup/states";

export default {
setup(){
  const payment =ref ({
    fullName:"Brenda",
    postalCode:"12345"
  });
 function onSave(){
  alert("hi hi");
 }
  return{
    payment,
    states,
    onSave
  };
}
}

</script>
