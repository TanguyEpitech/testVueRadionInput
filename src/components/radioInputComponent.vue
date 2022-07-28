<template>

<div id="error" v-if="error === false" >
{{message}}

</div>
  <div class=" grid">
    <div  class="border radio"    @click="click" v-for="item in items" :id="item.ind" :key="item.ind" >{{item.ind}}</div>
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
send(param) {

  return param},


    check (e) {


      for (let i = 0; i <this.items.length; i++) {

        document.querySelector(".grid").children[i].style.backgroundColor="green"

        if(this.items[i].ind === e.target.id) {
          document.querySelector(".grid").children[i].style.backgroundColor="red !important"
console.log(e.target)


          this.error = false;

          if(this.error === false ) {

            this.message = "";
            this.send(e.target.id)
          }


        }
        else {
          this.error = true;

          if(this.error === true) {
            this.message = "les valeurs sont null ou ne correspondent pas";

          }
        }

        e.target.style.backgroundColor="white"

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
