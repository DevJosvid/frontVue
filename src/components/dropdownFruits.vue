<template>
    <div class="row">
    <div class="col s6 m3">
      <div class="row">
        <div class="input-field col s12">
          <!-- <i class="material-icons prefix">textsms</i> -->
          <div class="check" v-on:click="aaaaa">
          <input type="text" placeholder="Select an item " id="autocomplete" class="autocomplete" v-on:keyup="ffff">
          <div class="icon"></div>
        </div>
          <!-- <chevron_right></chevron_right> -->
          <div class="col s6 m3">
      <div class="row spaceResults">
          <div id="res">
            <p id="options" v-bind:key="index" v-for="(fruit,index) in Fruits"> 
              {{fruit}}
            </p> 
          </div>
      </div>
          </div>
          <!-- <label for="autocomplete-input">Autocomplete</label> -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import chevron_right from 'vue-material-design-icons/chevron_right.vue';
import axios from 'axios'
export default {
  name: 'DropdownFruits',
  data:function(){
    return {
      "Fruits":{},
      "fruitssearch":""
      
    }
  },
  created:function() {
    this.ApiFruits()
    // if (this.$root.page=='aviatur') {
    //   this.site = "https://agenciasenlinea.aviatur.com"
    // }
    //console.log(this.$root.page);
  },
  methods:{

    ApiFruits:function(){
      //var axios = require("axios");
      var config ={
      method: "get",
      url: "http://127.0.0.1:8888/api/fruits",
      headers: {}
    }
    axios(config)
    .then(response =>{
      this.Fruits = response.data.data.fruits
      console.log(this.Fruits)
      console.log(response.data.data)
    } )
    },

    ffff:function(){
      
      const input = document.querySelector('.autocomplete').value;
      const options = document.querySelectorAll('#options');
      console.log(options)
      console.log(input.value) 
      let g = this.Fruits
      console.log(g)
      
      g.forEach((element,index) => {
        console.log(element)
        if(element.toLowerCase().includes(input.toLowerCase() )){        
           options[index].style.display = "block" 
        }else{
          options[index].style.display = "none"
        }
      });
        
    }  ,
    aaaaa:function(){
      const results = document.querySelector('#res');
      const autocomplete = document.querySelector('#autocomplete');
      console.log(results)
      autocomplete.style.boxShadow = "none"
      autocomplete.style.borderBottomLeftRadius = "0px"
      autocomplete.style.borderBottomRightRadius = "0px"
      results.style.display = "block"

      //this.ffff()
    }
   
},

}



</script>

<style>
.autocomplete{
  border: none;
  outline: none;
  height: 50px;
  width: 15%;
  border-radius: 5px;
  box-shadow: 5px 5px 10px #234e523f
}
.autocomplete:active{
  border: none
}
.autocomplete:focus{
  border: none
}
.autocomplete:target{
  border: none
}
.autocomplete::placeholder{
  size: 2rem;
}
#res{
  display: none;
  background: #fff;
  margin: 0 auto;
  width: 15.3%;
}
#options{
  margin-top: inherit;
  margin-bottom: 2%;
  font-family:"Lato", sans-serif;
  font-size:20px;
  
}
#options:hover{
  
  cursor: pointer;
  color: #4299E1
}
.spaceResults{
  display:flex;
}
.icon{
  float: right;
  display: contents;
}
::placeholder{
  font-size: medium;
}
</style>