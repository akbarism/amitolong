<template>
  <div>
    <table border="1">
      <tr>
        <th>contoh soal</th>
        <th>pilihan</th>
      </tr>
      <tr>
        <td class="soal">ini soal pertama</td>
        <td>
          <select v-model="a" @change="selectA">
            <option :value="x" v-for="x in list" :key="x">{{ x }}</option>
          </select>
        </td>
      </tr>
      <tr>
        <td class="soal">ini soal kedua</td>
        <td>
          <select v-model="b" @change="selectB">
            <option :value="x" v-for="x in list" :key="x">{{ x }}</option>
          </select>
        </td>
      </tr>
      <tr>
        <td class="soal">ini soal ketiga</td>
        <td>
          <select v-model="c" @change="selectC">
            <option :value="x" v-for="x in list" :key="x">{{ x }}</option>
          </select>
        </td>
      </tr>
      <tr>
        <td class="soal">ini soal keempat</td>
        <td>
          <select v-model="d" @change="selectD">
            <option :value="x" v-for="x in list" :key="x">{{ x }}</option>
          </select>
        </td>
      </tr>
      <tr>
        <td class="soal">ini soal kelima</td>
        <td>
          <select v-model="e" @change="selectE">
            <option :value="x" v-for="x in list" :key="x">{{ x }}</option>
          </select>
        </td>
      </tr>
    </table>

    <div>
      <table border="1">
        <tr>
          <th>contoh soal</th>
          <th>pilihan</th>
        </tr>
        <tr>
          <td class="soal">ini soal pertama</td>
          <td>
            <input type="checkbox" id="checkbox1" @change="check" />
          </td>
        </tr>
        <tr>
          <td class="soal">ini soal kedua</td>
          <td>
            <input type="checkbox" id="checkbox2" @change="check" />
          </td>
        </tr>
        <tr>
          <td class="soal">ini soal ketiga</td>
          <td>
            <input type="checkbox" id="checkbox3" @change="check" />
          </td>
        </tr>
        <tr>
          <td class="soal">ini soal keempat</td>
          <td>
            <input type="checkbox" id="checkbox4" @change="check" />
          </td>
        </tr>
        <tr>
          <td class="soal">ini soal kelima</td>
          <td>
            <input type="checkbox" id="checkbox5" @change="check" />
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "contoh",
  data() {
    return {
      list: [1, 2, 3, 4, 5],
      p: 0,
      a: 0,
      b: 0,
      c: 0,
      d: 0,
      e: 0,
      temp: []
    };
  },
  //   mounted() {
  //     this.check();
  //   },
  methods: {
    check() {
      let checkbox1 = document.getElementById("checkbox1");
      let checkbox2 = document.getElementById("checkbox2");
      let checkbox3 = document.getElementById("checkbox3");
      let checkbox4 = document.getElementById("checkbox4");
      let checkbox5 = document.getElementById("checkbox5");
      let arrcheck = [checkbox1, checkbox2, checkbox3, checkbox4, checkbox5];
      let flasecheck = [];
      let countTrue = 0;
      for (let i = 0; i < arrcheck.length; i++) {
        let checke = arrcheck[i].checked === true;
        if (checke == true) {
          countTrue = countTrue + 1;
        } else {
          flasecheck.push(arrcheck[i]);
        }
      }
      if (countTrue >= 3) {
        for (let i = 0; i < flasecheck.length; i++) {
          flasecheck[i].disabled = true;
        }
      } else {
        for (let i = 0; i < flasecheck.length; i++) {
          flasecheck[i].disabled = false;
        }
      }
    },
    selectA() {
      this.temp.push(this.a);
      this.change();
    },
    selectB() {
      this.temp.push(this.b);
      this.change();
    },
    selectC() {
      this.temp.push(this.c);
      this.change();
    },
    selectD() {
      this.temp.push(this.d);
      this.change();
    },
    selectE() {
      this.temp.push(this.e);
      this.change();
    },
    change() {
      const vm = this;
      //   const arr = [vm.a, vm.b, vm.c, vm.d, vm.e];
      let listArr = [];
      for (let i = 0; i < vm.temp.length; i++) {
        listArr.push(vm.temp[i]);
        console.log(listArr);
        for (let j = vm.temp[i]; j < vm.temp.length; j++) {
          console.log(vm.temp);
          if (vm.temp[i] === vm.temp[j]) {
            alert("tidak  boleh angka yang sama");
          } else {
            listArr.push(vm.temp[j]);
            console.log(listArr);
          }
        }
      }
    }
  }
};
</script>

<style></style>
