<template>
    <div>
      <ul class="running-line-container">
        <li class="running-line" v-for="(item, index) in runningLine" :key="index"><b>{{ item }}</b></li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    name: 'RunningLine',
    data() {
      return {
        runningLine: [],
        invis: "\u00A0\u00A0\u00A0" // Using non-breaking space entity
      };
    },
    mounted() {
      this.runningLine.push(`Taipei ${this.invis} Paris ${this.invis} London ${this.invis} Tokyo ${this.invis} Beijing ${this.invis} Moscow ${this.invis} Berlin ${this.invis} Rome ${this.invis} New Delhi ${this.invis} Brasília ${this.invis} Cairo ${this.invis} Ottawa ${this.invis} Stockholm ${this.invis} Ankara ${this.invis} Madrid ${this.invis} Buenos Aires`);
    }
  };
  </script>
  
  
  <style scoped>
  .running-line-container {
    width: 500px;
    margin-top: 0px;
    margin-bottom: 40px;
    list-style-type: none;
    display: flex;
    background-color: rgba(0, 0, 0, 0.5);
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: right;
    overflow: hidden;
  }
  
  .running-line {
    display: inline-block;
    white-space: nowrap;
    animation: marquee 20s linear infinite;
    font-size: 2em;
    text-transform: uppercase;
    color:rgba(135, 255, 147, 0.5)
    
  }
  
  @keyframes marquee {
    0% {
      transform: translateX(100%);
    }
    100% {
      transform: translateX(-50%);
    }
  }
  
  .running-line:nth-child(1) {
    animation-delay: 0s; /* Delay for the first item */
    
  }

  
  
  </style>
  