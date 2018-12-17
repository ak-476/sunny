<template>
  <div class="hello">
    <ul class="prize-list">
      <li v-for="(item, index) in prizeList" :class="{work: index === workIndex}" @click="checkList(item)">
        <span>
          <img :src="item.imgBgUrl" alt="">
        </span>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data() {
      return {
        msg: 'Welcome to Your Vue.js App',
        prizeList: [{
          id: 2018121701,
          name: '001',
          imgBgUrl: '/static/images/banner.jpg'
        }, {
          id: 2018121702,
          name: '002',
          imgBgUrl: '/static/images/banner.jpg'
        }, {
          id: 2018121703,
          name: '003',
          imgBgUrl: '/static/images/banner.jpg'
        }, {
          id: 2018121704,
          name: '004',
          imgBgUrl: '/static/images/banner.jpg'
        }, {
          id: 2018121705,
          name: '005',
          imgBgUrl: '/static/images/banner.jpg'
        }, {
          id: 2018121706,
          name: '006',
          imgBgUrl: '/static/images/banner.jpg'
        }, {
          id: 2018121707,
          name: '007',
          imgBgUrl: '/static/images/banner.jpg'
        }, {
          id: 2018121708,
          name: '008',
          imgBgUrl: '/static/images/banner.jpg'
        }, {
          id: 2018121709,
          name: '009',
          imgBgUrl: '/static/images/banner.jpg'
        }],
        timer: null,
        workIndex: 0
      }
    },
    mounted() {
      this.workIndex = 0;
      this.timer = setInterval(() => {
        this.workIndex++;
        if(this.workIndex > 9) {
          this.workIndex = 0;
        }
      }, 2800)
    },
    methods: {
      checkList() {
        clearInterval(this.timer);
        this.workIndex = null;
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  .hello {
    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;
    top: 0;
    background: url("./../assets/images/bg.jpg") center center no-repeat;
    background-size: 100% 100%;
    .prize-list {
      position: absolute;
      top: 20.8%;
      left: 4.3%;
      right: 3.8%;
      bottom: 2.4%;
      background: rgba(0, 0, 0, 0.7);

      li {
        float: left;
        width: 33.33333333%;
        height: 33.33333333%;
        position: relative;
        span {
          display: inline-block;
          position: absolute;
          left: 5px;
          top: 5px;
          right: 5px;
          bottom: 5px;
          img {
            width: 100%;
            height: 100%;
          }
        }

        &.work {
          animation: prizeDo .8s ease infinite alternate;
        }
      }
    }
  }

  @keyframes prizeDo {
    0% {
      transform: rotateZ(-20deg);
    }
    10% {
      transform: rotateZ(0deg);
    }
    20%{
      transform: rotateZ(20deg);
    }
    30%{
      transform: rotateZ(0deg);
    }
    100% {
      transform: rotateZ(0deg);
    }
  }


</style>
