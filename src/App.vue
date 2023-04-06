<script>
import data from '../data.json'
export default {
  name: 'App',
  data() {
    return {
      dayData: data
    }
  }
}
</script>

<template>
  <main>
    <div class="balance-container">
      <div>
        <p class="pbal">My Balance</p>
        <h2>$921.48</h2>
      </div>
      <div>
        <div class="circle"></div>
      </div>
    </div>

    <div class="data-container">
      <h1>Spending - Last 7 days</h1>
      <div class="graph">
        <div v-for="data in dayData" class="data-part" :key="data.id">
          <p class="daily-spent">${{ data.amount }}</p>
          <div class="data-bar" :style="{height: data.amount * 1.2 + '%'}"></div>
          <p class="day">{{ data.day }}</p>
        </div>
      </div>
      <div class="divider"></div>
      <div class="mtotal">
        <div>
          <p class="monthP">Total this month</p>
          <h2 class="total-monthly">$478.33</h2>
        </div>
        <div>
          <h2 class="mpercent">+2.4%</h2>
          <p class="monthP">from last month</p>
        </div>
      </div>
    </div>
  </main>
</template>

