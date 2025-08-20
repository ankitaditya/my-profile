<template>
  <div class="edu-block">
    <div class="edu-title">
      <span class="degree">B.Tech, Computer Science & Engineering</span>
      <span class="institute">Dr. K.N. Modi Institute of Engineering & Technology, Modinagar</span>
    </div>
    <div class="edu-details">
      <span>2016 – 2020</span>
      <span>CGPA: 7.6/10</span>
    </div>
  </div>
</template>
<style scoped>
.edu-block {
  background: #232323;
  border-radius: 16px;
  padding: 1.5em;
  box-shadow: 0 1px 8px 0 #9e7fff22;
  display: flex;
  flex-direction: column;
  gap: 0.7em;
}
.edu-title {
  font-size: 1.1rem;
  font-weight: 700;
  color: #9e7fff;
  margin-bottom: 0.3em;
  display: flex;
  flex-direction: column;
  gap: 0.2em;
}
.institute {
  color: #38bdf8;
  font-weight: 500;
  font-size: 1rem;
}
.edu-details {
  color: #a3a3a3;
  font-size: 1rem;
  display: flex;
  gap: 2em;
}
</style>
