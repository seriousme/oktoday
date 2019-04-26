<template>
  <div class="container" style="max-width: 800px">
    <nav class="navbar navbar-expand-lg navbar-dark bg-info">
      <a class="navbar-brand" href="#">OK Today</a>

      <ul class="navbar-nav mr-auto"></ul>
      <ul class="navbar-nav">
        <li class="nav-item active">
          <a class="nav-link" href="#">Invoer</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Overzicht</a>
        </li>
      </ul>
    </nav>
    <div class="justify-content-center">
      <form>
        <fieldset class="form__options">
          <legend class="form__question">Datum</legend>
          <input type="date" id="date" name="date" value="2019-04-26">
        </fieldset>
        <fieldset class="form__options">
          <legend class="form__question">Gevoel</legend>
          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="mood" id="moodRadio1" value="1">
            <label class="form-check-label" for="moodRadio1">1</label>
          </div>
          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="mood" id="moodRadio2" value="2">
            <label class="form-check-label" for="moodRadio2">2</label>
          </div>
          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="mood" id="moodRadio3" value="3">
            <label class="form-check-label" for="moodRadio3">3</label>
          </div>
          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="mood" id="moodRadio4" value="4">
            <label class="form-check-label" for="moodRadio4">4</label>
          </div>
          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="mood" id="moodRadio5" value="5">
            <label class="form-check-label" for="moodRadio5">5</label>
          </div>
        </fieldset>
        <fieldset class="form__options">
          <legend class="form__question">Energie</legend>
          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="energy" id="energyRadio1" value="1">
            <label class="form-check-label" for="energyRadio1">1</label>
          </div>
          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="energy" id="energyRadio2" value="2">
            <label class="form-check-label" for="energyRadio2">2</label>
          </div>
          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="energy" id="energyRadio3" value="3">
            <label class="form-check-label" for="energyRadio3">3</label>
          </div>
          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="energy" id="energyRadio4" value="4">
            <label class="form-check-label" for="energyRadio4">4</label>
          </div>
          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="energy" id="energyRadio5" value="5">
            <label class="form-check-label" for="energyRadio5">5</label>
          </div>
        </fieldset>
        <fieldset class="form__options">
          <legend class="form__question">Opmerking</legend>
          <textarea class="form-control" id="remark" rows="2"></textarea>
        </fieldset>
        <div>
          <button type="submit" class="btn btn-info mt-3">Opslaan</button>
        </div>
      </form>

      <div class="card d-none">
        <div class="card-body">
          <h5 class="card-title">Overzicht</h5>
          <div class="card-text">
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
        </div>
      </div>
    </div>
  </div>
</template>
<style>
</style>
