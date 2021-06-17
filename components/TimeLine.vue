<template>
  <v-app>
    <v-container timeline-container>
      <v-timeline align-top>
        <v-timeline-item v-for="(item, index) in info" :key="index" large>
          <template v-slot:icon>
            <v-avatar class="timeline-avatar">
              <!-- <img src="https://i.pravatar.cc/64" /> -->
              <img src="@/assets/img/check-in-circle.png" />
            </v-avatar>
          </template>
          <template v-slot:opposite>
            <span class="timeline-stage">{{ item.stage }}</span>
          </template>
          <v-card :class="index % 2 == 0 ? 'elevation-2 border-left' : 'elevation-2 border-right'">
            <v-card-title class="timeline-title">
              {{ item.title }}
            </v-card-title>
            <v-card-text class="timeline-desc text-h4">
              {{ item.description }}
            </v-card-text>
          </v-card>
        </v-timeline-item>
      </v-timeline>
    </v-container>
  </v-app>
</template>
<script>
const ROADMAP_PHASE_LIST = [
  {
    title: "Stage 1",
    description: "PRESALE",
    stage: "JUNE",
  },
  {
    title: "Stage 2",
    description: "PRESALE\nPANCAKESWAP\nCOINGECKO\nCOINMARKETCAP",
    stage: "JULY",
  },
  {
    title: "Stage 3",
    description: "PUBLIC SALE DEX",
    stage: "AUG",
  },
  {
    title: "Stage 4",
    description: "AKUMA DEFI BETA",
    stage: "SEP",
  },
  {
    title: "Stage 5",
    description: "AKUMA DEFI V1.0.0\nAKUMA NFT BETA",
    stage: "OCT",
  },
  {
    title: "Stage 6",
    description: "AKUMA NFT V1.0.0",
    stage: "NOV",
  },
  {
    title: "Stage 7",
    description: "AKUMA DASHBOARD V1.0.0",
    stage: "DEC",
  },
];
export default {
  data() {
    return {
      info: ROADMAP_PHASE_LIST,
    };
  },
};
</script>
<style>
.theme--light.v-application {
  background-color: unset !important;
}
.v-timeline:before {
  width: 4px;
  background: white !important;
}
.theme--light.v-card {
  background-color: #ed8800;
}
.v-timeline-item__opposite {
  align-self: start !important;
}

.timeline-avatar {
  background-color: black;
  border: 2px solid white;
}
.timeline-avatar img {
  width: 75%;
  height: 75%;
}

.timeline-container {
  padding: 20px;
}
.timeline-container:before {
  content: "";
  width: 20px;
  height: 20px;
  display: inline-block;
  border-radius: 50%;
  position: absolute;
  left: calc(50% - 9px);
  z-index: 100;
  top: 0px;
  background-color: white;
}
.timeline-container:after {
  content: "";
  width: 20px;
  height: 20px;
  display: inline-block;
  border-radius: 50%;
  position: absolute;
  left: calc(50% - 9px);
  z-index: 100;
  bottom: 0px;
  background-color: white;
}
.timeline-stage {
  font-size: 44px;
  color: #ed8800;
  line-height: 1;
}
.timeline-title {
  color: white;
  font-size: 20px;
}
.timeline-desc {
  white-space: pre-line;
  color: black !important;
  font-weight: bold !important;
}
.timeline-desc:first-line {
  line-height: 0;
}

.border-left {
  border-left: 1px solid white;
}
.border-right {
  border-right: 1px solid white;
}
</style>
