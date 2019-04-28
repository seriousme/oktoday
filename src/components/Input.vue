<template>
  <div>
    <form>
      <div class="form-group row mt-2">
        <label for="date" class="col-sm-2 col-form-label">Datum</label>
        <div class="col-sm-10">
          <input type="date" id="date" v-model="date" class="form-control">
        </div>
      </div>
      <div class="form-group row">
        <label for="mood" class="col-sm-2 col-form-label">Gevoel</label>
        <div class="col-sm-10">
          <div class="form-control">
            <div class="form-check form-check-inline ml-3">
              <input class="form-check-input" type="radio" v-model="mood" id="moodRadio1" value="1">
              <label class="form-check-label" for="moodRadio1">1</label>
            </div>
            <div class="form-check form-check-inline ml-3">
              <input class="form-check-input" type="radio" v-model="mood" id="moodRadio2" value="2">
              <label class="form-check-label" for="moodRadio2">2</label>
            </div>
            <div class="form-check form-check-inline ml-3">
              <input class="form-check-input" type="radio" v-model="mood" id="moodRadio3" value="3">
              <label class="form-check-label" for="moodRadio3">3</label>
            </div>
            <div class="form-check form-check-inline ml-3">
              <input class="form-check-input" type="radio" v-model="mood" id="moodRadio4" value="4">
              <label class="form-check-label" for="moodRadio4">4</label>
            </div>
            <div class="form-check form-check-inline ml-3">
              <input class="form-check-input" type="radio" v-model="mood" id="moodRadio5" value="5">
              <label class="form-check-label" for="moodRadio5">5</label>
            </div>
          </div>
        </div>
      </div>
      <div class="form-group row">
        <label for="mood" class="col-sm-2 col-form-label">Energie</label>
        <div class="col-sm-10">
          <div class="form-control">
            <div class="form-check form-check-inline ml-3">
              <input
                class="form-check-input"
                type="radio"
                v-model="energy"
                id="energyRd1"
                value="1"
              >
              <label class="form-check-label" for="energyRd1">1</label>
            </div>
            <div class="form-check form-check-inline ml-3">
              <input
                class="form-check-input"
                type="radio"
                v-model="energy"
                id="energyRd2"
                value="2"
              >
              <label class="form-check-label" for="energyRd2">2</label>
            </div>
            <div class="form-check form-check-inline ml-3">
              <input
                class="form-check-input"
                type="radio"
                v-model="energy"
                id="energyRd3"
                value="3"
              >
              <label class="form-check-label" for="energyRd3">3</label>
            </div>
            <div class="form-check form-check-inline ml-3">
              <input
                class="form-check-input"
                type="radio"
                v-model="energy"
                id="energyRd4"
                value="4"
              >
              <label class="form-check-label" for="energyRd4">4</label>
            </div>
            <div class="form-check form-check-inline ml-3">
              <input
                class="form-check-input"
                type="radio"
                v-model="energy"
                id="energyRd5"
                value="5"
              >
              <label class="form-check-label" for="energyRd5">5</label>
            </div>
          </div>
        </div>
      </div>
      <div class="form-group row">
        <label for="remark" class="col-sm-2 col-form-label">Opmerking</label>
        <div class="col-sm-10">
          <textarea class="form-control" id="remark" v-model="remark" rows="1"></textarea>
        </div>
      </div>

      <div class="d-flex justify-content-center">
        <button type="button" class="btn btn-info mt-2" v-on:click="save()">Opslaan</button>
      </div>
    </form>
  </div>
</template>

<script>
function initRecord() {
  return {
    date: new Date().toISOString().split("T")[0],
    mood: 3,
    energy: 3,
    remark: ""
  };
}

const data = initRecord();

export default {
  name: "Input",
  data: function() {
    return data;
  },
  methods: {
    save: function() {
      const initial = initRecord();
      const record = {};
      Object.keys(initial).map(key => (record[key] = this[key]));
      this.$emit("save", record);
      Object.keys(initial).map(key => (this[key] = initial[key]));
    }
  }
};
</script>

<style>
input[type="radio"] {
  opacity: 0;
  width: 0;
  height: 0;
}

label {
  border: 1px solid rgba(black, 0.15);
  box-sizing: border-box;
  /* display: block;*/
  height: 100%;
  width: 100%;
  /*padding: 10px 10px 10px 10px;*/
  margin-bottom: 10px !important;
  background-color: white;
  color: black;
  cursor: pointer;
  opacity: 0.5;
}
label:hover,
label:focus,
label:active {
  border: 1px solid rgba(black, 0.5);
}
input[type="radio"]:active ~ label {
  opacity: 1;
}

input[type="radio"]:checked ~ label {
  opacity: 1;
  border: 1px solid black;
  background-color: #17a2b8;
  color: white;
}
</style>
