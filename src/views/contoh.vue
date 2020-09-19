<template>
  <div>
    <table border="1">
      <tr>
        <th>contoh soal</th>
        <th>pilihan</th>
      </tr>
      <tr v-for="item in items" :key="item.id">
        <td class="soal">ini soal pertama</td>
        <td>
          <select @change="change">
            <option value="0">pilih</option>
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
            <option value="4">4</option>
            <option value="5">5</option>
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
        <tr v-for="item in items" :key="item.id">
          <td class="soal">ini soal pertama</td>
          <td>
            <input type="checkbox" :id="item.id" @change="check(item.id)" />
          </td>
        </tr>
        <!-- <tr>
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
        </tr> -->
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "contoh",
  data() {
    return {
      items: [{ id: 1 }, { id: 2 }, { id: 3 }, { id: 4 }, { id: 5 }],
      a: 0,
      temp: {
        a: 0,
        b: 0,
        c: 0,
        d: 0,
        e: 0
      },
      ckbx: []
    };
  },
  //   mounted() {
  //     this.check();
  //   },
  methods: {
    change() {
      //jadi gue mau ngecek kelimanya jangan ada angka yang sama gitu mi
    },
    check(item) {
      let checkbox1 = document.getElementById(item);

      const vm = this;
      vm.ckbx.push(checkbox1);
      // console.log(vm.ckbx);
      let flasecheck = [];
      let countTrue = 0;
      for (let i = 0; i < vm.ckbx.length; i++) {
        let checke = vm.ckbx[i].checked === true;
        console.log(vm.ckbx);
        if (checke == true) {
          countTrue = countTrue + 1;
        } else {
          flasecheck.push(vm.ckbx[i]);
          console.log(flasecheck);
        }
        console.log(countTrue);
      }
      if (countTrue >= 1) {
        for (let i = 0; i < flasecheck.length; i++) {
          flasecheck[i].disabled = true;
          console.log(flasecheck[i]);
        }
      } else {
        for (let i = 0; i < flasecheck.length; i++) {
          flasecheck[i].disabled = false;
        }
      }
    }
  }
};
</script>

<style></style>
