<template>
  <div>
    <div class="card bg-1 mb-3" style="max-width: 120rem">
      <div class="card-header">ข้อมูลลูกค้า</div>
      <div class="card-body">
        <form>
          <div class="row">
            <div class="col">
              <input
                type="text"
                class="form-control"
                placeholder="ชื่อ"
                v-model="Name"
              />
            </div>
            <div class="col">
              <input
                type="text"
                class="form-control"
                placeholder="เบอร์โทรศัพท์."
                v-model="Tel"
              />
            </div>
          </div>
        </form>

        <div class="row justify-content-end">
          <h4 class="col-lg-4">ยอดรวม : {{ Total }} บาท</h4>
          <button type="button " class="btn btn-outline-success mr-3" @click="sum()">
            ซื้อ
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    Total: Number,
    Data: Array
  },
  data() {
    return {
      Name: "",
      Tel: ""
    };
  },
  methods: {
    sum() {
      alert(
        "Name : " +
          this.Name +
          " Tel. : " +
          this.Tel +
          " Total : " +
          this.Total +
          " ฿"
      );
    }
  }
};
</script>

<style scoped>
.bg-1 {
  background-color: rgba(32, 31, 31, 0.952);
  color: rgb(255, 255, 255);
}
</style>
