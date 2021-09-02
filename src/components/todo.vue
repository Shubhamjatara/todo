<template>
  <div>
    <h1>TODO LIST APP</h1>
    <div class="outerdiv">
      <input id="take_input" type="text"  placeholder="Enter Tasks" required/>
      <div><button class="btn" v-on:click="add_item">Add Task</button></div>
      <div>
        <div class="data" v-for="item in arr" :key="item.msg">
          <div class="item">{{ item.msg }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "todo",
  data() {
    return {
      arr: [],
    };
  },
  methods: {
    add_item: function () {
      let value = document.getElementById("take_input").value;
      if(value == ""){alert("Enter Task"); return;}
      this.arr.push({ msg: value });
    },
   },



};
</script>

<style >
.outerdiv {
  width: 500px;
  height: 500px;
  margin: 0 auto 0 auto;
}

#take_input {
  width: 300px;
}


.btn {
  background-color: transparent;
  border: 0.5px solid crimson;
  color: crimson;
  width: 80px;
  height: 30px;
  cursor: pointer;
}
div {
  margin: 10px 0 10px 0;
  text-align: center;
  width: 100%;
}

.data {
  display: flex;
  justify-content: center;
  align-items: center;
}
/* .data div {
  width: 200px;
  line-break: anywhere;
  word-wrap: break-word;
} */
</style>
