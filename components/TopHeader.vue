<template>
  <div>
    <div class="container">
      <h3>Where in the world?</h3>
      <button class="toggle"><fa icon="moon" />Dark Mode</button>
    </div>
    <div class="container">
      <div class="form-control">
        <i><fa icon="search" /></i>
        <input type="text" placeholder="Search For Country..." />
      </div>
      <div class="dropDownCon">
        <div class="dropDown">
          <p>Filter By Region</p>
          <button><fa icon="chevron-down" /></button>
        </div>
        <div class="drop">
          <p>Africa</p>
          <p>America</p>
          <p>Asia</p>
          <p>Europe</p>
          <p>Oceania</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>
