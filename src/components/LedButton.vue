<template>
<div class="card text-center bg-light d-flex mx-auto shadow rounded text-align" style="width: 18rem; align: center; display:block;">
  <div class="card-body">
    <h5 class="card-title">Toggle Led</h5>
      <button @click="toggleClick" id="ledButton" type="button" class="btn btn-primary btn-lg bg-success no-focus-outline" style="width: 50%; height: 80%; outline: none;">On</button>
    </div>
</div>
</template>

<script>
let led = 1;
export default {
  name: 'LedButton',
  props: {
    msg: String
  },
  methods: {
    toggleClick: () => {
      
      console.log("Request sent");
      var url = "http://192.168.0.9/led";
      var xhr = new XMLHttpRequest();
      xhr.open("POST", url)
      xhr.setRequestHeader("Content-Type", "application/json;charset=UTF-8");
      xhr.setRequestHeader("Access-control-allow-origin", "http://192.168.0.2/led");
      xhr.open("POST", url, true);
      if (led == 1) {
        led = 0; 
        document.getElementById("ledButton").classList.remove("bg-success");
        document.getElementById("ledButton").classList.add("bg-danger");
        document.getElementById("ledButton").innerHTML = "OFF";
      }
      else if (led == 0) {
        led = 1;
        document.getElementById("ledButton").classList.add("bg-success");
        document.getElementById("ledButton").classList.remove("bg-danger");
        document.getElementById("ledButton").innerHTML = "ON";
      }
      xhr.send(JSON.stringify({state:led}))
    },
  }
}

</script>

<style>
.btn:focus {
  border-color: inherit;
  -webkit-box-shadow: none;
  box-shadow: none;
}
</style>
