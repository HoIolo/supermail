<template>
  <div class="tab-control">
      <div v-for="(item,index) in titles" :key="index" :class="{active: index === currentIndex}" class="tab-control-item" @click="itemClick(index)">
          <span>{{item}}</span>
        </div>
  </div>
</template>

<script>
export default {
    props: {
        titles: {
            type: Array,
            default() {
                return []
            }
        }
    },
    data() {
        return {
            currentIndex: 0
        }
    },
    methods: {
        itemClick(index) {
            this.currentIndex = index
            this.$emit('tabClick',index)
        }   
    }
}
</script>

<style>
.tab-control {
    display: flex;
    text-align: center;
    font-size: 15px;
    background-color: #fff;
}
.tab-control-item {
    flex: 1;
}
.tab-control-item span {
    line-height: 40px;
    padding: 5px;
}
.active {
    color: pink;
}
.active span {
    border-bottom: 3px solid pink;
}
</style>