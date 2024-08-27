<template>
    <div v-for="Customer in CustomerData" :key="Customer">
        <p v-if="Customer.cus_id==1">
            <input name="customerName" type="radio" checked> {{ Customer.cus_name }}
        </p>
        <p v-else>
            <input name="customerName" type="radio"> {{ Customer.cus_name }}
        </p>
  </div>
</template>
  <script>
  
  export default {
      name : 'CustomerVue',
      props : {
          CustomerData: Array,
      }
  }
  </script>
  
  <style>
  
  </style>
