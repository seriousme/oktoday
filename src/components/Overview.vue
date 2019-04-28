<template>
  <div>
    <table class="table table-striped">
      <thead class="thead-dark">
        <tr>
          <td scope="col">Datum</td>
          <td scope="col">Gevoel</td>
          <td scope="col">Energie</td>
          <td scope="col">Opmerking</td>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>25 April 2019</td>
          <td>4</td>
          <td>3</td>
          <td>Zonnige dag</td>
        </tr>
        <tr>
          <td>24 April 2019</td>
          <td>3</td>
          <td>4</td>
          <td></td>
        </tr>
        <tr>
          <td>23 April 2019</td>
          <td>2</td>
          <td>3</td>
          <td>Regenachtige dag</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
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
