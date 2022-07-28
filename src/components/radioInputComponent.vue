<template>

<div id="error" v-if="error === false" >
{{message}}

</div>
  <div class=" grid">
    <div  class="border radio"    @click="click" v-for="item in items"    :key="item.ind" :aria-valuenow="item.ind " >{{item.ind}}</div>
  </div>



</template>

<script>
export default {
  name: "RadioInputComponent",
  data() {
    return {
      message : "",
      error : false,
      isActive : false,
      id : "",
      response: "",
      item: "",
      val: "",
      items: [],
      ind : "",
      data : false

    }
  }
  ,
  methods: {



    check (e) {

     console.log( this.items[3].ind)


      for (let i = 0; i <this.items.length; i++) {
console.log(e.target.ariaValueNow)
        if(this.items[i].ind === e.target.ariaValueNow) {
          this.error = false;


          if(this.error === false ) {
console.log(this.error)
            this.message = "";

          }
        }
        else {
          this.error = true;

          if(this.error === true) {
            this.message = "les valeurs sont null ou ne correspondent pas";

          }
        }


      }





    },

    click(e) {


      this.check(e)


    }
  },
  mounted() {
    this.items = [
      {ind: '0-5'},
      {ind: '6-10'},
      {ind: '50-100'},
      {ind: '100+'},
    ]
  }
}

</script>

<style scoped>
.active {

  background: red;
}
:root {
  --blue: #1e90ff;
  --white: #ffffff;
}
.border {
  border: 1px solid blue;
  padding: 5px 10px;
}

.grid {

  border-radius: 4px;
  border: 1px solid blue;
  margin: auto;
  display: flex;
  flex-wrap: nowrap;
  flex-direction: row;
  max-width: 230px;
  justify-content: center;
  min-width: 230px;

}


.radioClassToggle {
  background : #458FFF;

}
</style>
