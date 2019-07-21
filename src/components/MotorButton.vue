<template>
<div class="card text-center d-flex mx-auto bg-light shadow rounded" style="width: 18rem; display:block;">
  <div class="card-body">
    <h5 class="card-title">Move Motor</h5>
      <button id="ledButton" type="button" class="btn btn-primary no-focus-outline" style="width: 40%; height: 80%; outline: none; margin-right: 2.5px;">Left</button>
      <button v-touch:start="tests" v-touch:end="tests" id="ledButton" type="button" class="btn btn-primary no-focus-outline" style="width: 40%; height: 80%; outline: none; margin-left: 2.5px;">Right</button>
    </div>
</div>
</template>

<script>

export default {
  name: 'MotorButton',
  methods: {
    moveMotorLeft: (dir) => {
      var url = "http://192.168.0.9/motor";
      var xhr = new XMLHttpRequest();
      xhr.open("POST", url)
      xhr.setRequestHeader("Content-Type", "application/json;charset=UTF-8");
      xhr.setRequestHeader("Access-control-allow-origin", "http://192.168.0.2/led");
      xhr.open("POST", url, true);
      xhr.send(JSON.stringify({button:"left"}))
  },
  moveMotorRight: (dir) => {
      var url = "http://192.168.0.9/motor";
      var xhr = new XMLHttpRequest();
      xhr.open("POST", url)
      xhr.setRequestHeader("Content-Type", "application/json;charset=UTF-8");
      xhr.setRequestHeader("Access-control-allow-origin", "http://192.168.0.2/led");
      xhr.open("POST", url, true);
      xhr.send(JSON.stringify({button:"right"}))
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
