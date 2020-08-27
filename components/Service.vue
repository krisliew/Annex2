<template>
  <section id="Service">
    <div class="container">
      <h1>Services</h1>
      <p>We provide wide range of services</p>

      <div class="row">
        <div class="featureRow">
          <div class="circle2">
            <v-icon name="industry" scale="3.5" />
          </div>
          <h3 class="glow">Instrument Installation</h3>
          <br />
          <p class="lead mb-0">
            Our service includes electrical and instrument control circuit
            design and engineering, cable laying and termination
          </p>
        </div>
        <div class="featureRow">
          <div class="circle2"><v-icon name="tools" scale="3.5" /></div>
          <h3 class="glow">Factory electrical maintenance</h3>
          <br />
          <p class="lead mb-0">
            Service switchgear and motor. Service & Calibrate all types of local
            gauges, flow, level and temperature transmitters.
          </p>
        </div>
        <div class="featureRow">
          <div class="circle2"><v-icon name="plug" scale="3.5" /></div>
          <h3 class="glow">Electrical wiring</h3>
          <br />
          <p class="lead mb-0">
            Installation of complete wiring system and rewiring for industrial
            level.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
section {
  height: 100vh;
  background-color: #f6f8fc;
}
.container h1 {
  text-align: center;
}
/*------- Key Feature Section---------*/
.featurePic {
  display: inline-block;
  width: 60px;
  height: auto;
  margin: 10px;
}
.glow,
.circle,
.circle2 {
  text-align: center;
}
.glow {
  margin-top: 10px;
  font-size: 18px;
  color: #384047;
  -webkit-animation: glow 1s ease-in-out infinite alternate;
  -moz-animation: glow 1s ease-in-out infinite alternate;
  animation: glow 1s ease-in-out infinite alternate;
}
@keyframes glow {
  from {
    text-shadow: 0 0 4px #fff;
  }
  to {
    text-shadow: 0 0 15px #ff8c00;
  }
}
.circle {
  margin-top: 20px;
  margin-left: auto;
  margin-right: auto;
  display: block;
  height: 90px;
  width: 90px;
  border-radius: 50%;
  border-color: darkgreen;
  border-style: solid;
  border-width: 2px;
  text-align: center;
  background: #fff;
  line-height: 1.7em;
}
.circle2 {
  margin-top: 20px;
  margin-left: auto;
  margin-right: auto;
  display: block;
  height: 90px;
  width: 90px;
  text-align: center;
  line-height: 1.7em;
}
.circle img {
  display: inline-block;
}
.featureRow {
  max-width: 300px;
  display: inline-block;
  margin-left: auto;
  margin-right: auto;
}
.featureRow p {
  font-size: 1.2em;
  text-align: justify;
}
@media (max-width: 991px) {
  .featureRow {
    max-width: 80%;
  }
}
</style>
