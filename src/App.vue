<template lang="html">
  <div id="app">
    <div class="head">
      <p class="time">{{ presentTime }}</p>
    </div>
    <div v-for="(item, idx) in items" :key="idx" class="gauge-container">
      <div class="gauge-chart">
        <div class="gauge-text">
          <div class="f_mname">
            {{ item.mid }}
          </div>
          <div class="f_p">
            {{ item.process }}
          </div>
        </div>
        <vue-svg-gauge
          :start-angle="-110"
          :end-angle="110"
          :value="item.value"
          :separator-step="0"
          :min="0"
          :max="item.max"
          gauge-color="#347AB0"
          :scale-interval="0.1"
        />
        <div class="progress-wrap">
          <div>{{ item.value }} / {{ item.max }}</div>
          <div>{{ item.fTime }}</div>
        </div>
        <div class="gauge-wrap">
          <div class="f_end">
            {{ item.timer }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
//import Vue from 'vue'
import { VueSvgGauge } from "vue-svg-gauge";

export default {
  components: {
    VueSvgGauge
  },
  data() {
    return {
      presentTime: "2020-03-14 12:00:00",
      items: [
        {
          value: 100,
          max: 100,
          mid: "Puma280",
          idx: 1,
          process: "CS98D25H49-01-2",
          timer: "가공완료",
          fTime: "0 시간 6 분"
        },
        {
          value: 4,
          max: 100,
          mid: "PumaV400",
          idx: 2,
          process: "O0229",
          timer: "04:34",
          fTime: "84 시간 40 분"
        },
        {
          value: 459,
          max: 500,
          mid: "Lynx220C",
          idx: 3,
          process: "D580007-02-F",
          timer: "01:33",
          fTime: "2 시간 36 분"
        },
        {
          value: 70,
          max: 100,
          mid: "Puma240",
          idx: 4,
          process: "WGR150D35H24-02-1",
          timer: "00:10",
          fTime: "1 시간 31 분"
        },
        {
          value: 12,
          max: 100,
          mid: "Lynx220CL",
          idx: 5,
          process: "CS98D25H49-02-02",
          timer: "02:34",
          fTime: "5 시간 0 분"
        },
        {
          value: 100,
          max: 200,
          mid: "Lynx220SY",
          idx: 6,
          process: "JIG-CD",
          timer: "READY",
          fTime: "23 시간 48 분"
        }
      ]
    };
  }
};
</script>

<style scoped>
.time {
  padding: 20px 0;
  font-size: 20px;
  text-align: center;
  background: #f2f2f2;
}
.gauge-container {
  /* padding: 0 50px; */
}
.gauge-chart {
  position: relative;
  float: left;
  width: 25%;
  padding: 30px 35px;
  /* border-bottom: 1px solid #eee; */
}
vue-svg-gauge {
  padding: 20px;
}
.progress-wrap {
  position: absolute;
  top: 55%;
  left: 50%;
  transform: translate(-50%);
  text-align: center;
  font-size: 1.3rem;
}
.gauge-wrap {
  text-align: center;
  font-weight: 400;
}
.gauge-text {
  margin-bottom: 10px;
  text-align: center;
  line-height: 1.4;
}
.f_mname {
  font-size: 1.5rem;
  font-weight: bold;
}
.f_p {
  color: #a6a6a6;
  font-size: 1.3rem;
}
.f_end {
  font-size: 1.5rem;
}

@media (max-width: 1200px) {
  .gauge-chart {
    width: 33.33%;
  }
  .progress-wrap {
    font-size: 1.2rem;
  }
  .f_mname {
    font-size: 1.3rem;
    font-weight: bold;
  }
  .f_p {
    color: #a6a6a6;
    font-size: 1.2rem;
  }
  .f_end {
    font-size: 1.3rem;
  }
}
@media (max-width: 1200px) {
  .progress-wrap {
    font-size: 1rem;
  }
  .f_mname {
    font-size: 1.2rem;
    font-weight: bold;
  }
  .f_p {
    color: #a6a6a6;
    font-size: 1rem;
  }
  .f_end {
    font-size: 1.2rem;
  }
}
@media (max-width: 768px) {
  .gauge-chart {
    width: 50%;
  }
}
@media (max-width: 600px) {
  .gauge-chart {
    width: 100%;
    border-bottom: 1px solid #eee;
  }
  .progress-wrap {
    font-size: 1.3rem;
  }
  .f_mname {
    font-size: 1.5rem;
    font-weight: bold;
  }
  .f_p {
    color: #a6a6a6;
    font-size: 1.3rem;
  }
  .f_end {
    font-size: 1.5rem;
  }
}
@media (max-width: 375px) {
  .gauge-chart {
    padding: 10px 15px;
  }
}
</style>
