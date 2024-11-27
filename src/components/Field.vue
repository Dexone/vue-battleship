<template>
  abcdefihij
  <div v-for="(value, name) in ships" :id=name @mousedown="mouseDown(name)"
    style="width: 50px; height: 50px; background-color: rgb(255, 3, 3); position: absolute;">{{ name }}</div>

  <!-- <div id="p112" @mousedown="mouseDown()"
    style="position: absolute; width: 50px; height: 50px; background-color: rgb(255, 3, 3); ">p112</div> -->

  <!-- <table style="margin-top: 100px;">
    <tr v-for="value in field">
      <td v-for="v in value" style="width: 50px; height: 50px; background-color: black; color: white;">{{ v }}</td>
    </tr>
  </table> -->


  <!-- <table  >
    <tr v-for="(n, index) in field">
      <td  @mouseup="test(n-1+v)" v-for="v in 10" v-if="n % 10 == 0" :id="n -1 + v" style="width: 50px; height: 50px; background-color: black; color: white;">{{ n -1 + v }}</td>
    </tr>
  </table> -->

  <table>
    <tr v-for="n in 100">
      <td v-for="v in 10" v-if="n % 10 == 0" :id="n - 11 + v"
        style="width: 50px; height: 50px; background-color: black; color: white;">{{ field[n - 11 + v] }}</td>
    </tr>
  </table>


  <!-- <li v-for="index in 10" :key="index">{{ products[page * 10 + index] }}</li> -->

  <!-- 
  <div v-for="(n, index) in field" >{{ n }}</div> -->
</template>

<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})
// const ships = ref(['p11', 'p12', 'p13'])
const ships = ref({ 'p11': [1, 'y'], 'p12': [1, 'y'], 'p13': [1, 'y'] })


function mouseDown(item) { //при нажатии лкм
  let elem = document.getElementById(item)
  document.onmousemove = function moveAt(e) { //при движении мыши
    elem.style.left = e.pageX - elem.offsetWidth / 2 + 'px';
    elem.style.top = e.pageY - elem.offsetHeight / 2 + 'px';
  }

  document.onmouseup = function () { //при отпускании лкм
    document.onmousemove = null;

  }
}

function test(item) {
  console.log(item)
}


// const field = ref([])

// let count = 0
// for(let a = 0; a<10; a++){
// field.value.push([])
//   for(let b = 0; b<10; b++){
// field.value[a].push(count)
// count ++
// // field.value[a][b] = document.getElementById()
//   }

// }


const field = ref([])


for (let a = 0; a < 100; a++) {
  field.value.push([a])
  // field.value[a][b] = document.getElementById()
}
console.log(field)


// field.value[2][5] = 1


</script>


<style scoped></style>
