<template>
  <div id="app">
    <div class="tab">
      <span v-for='(item,index) in tab' :key='index' :class="{'active':num===index}" @click="Tabfn(index,item.every)">{{item.name}}</span>
    </div>
    <div class="main" :current='current'>
      <tab1></tab1>
    </div>
  </div>
</template>

<script>
import tab1 from './components/wei1'
import tab2 from './components/wei2'
import tab3 from './components/wei3'
export default {
  name: "App",
  data(){
    return {
      tab1:'tab1',
      tab2:'tab2',
      tab3:'tab3',
      current:'tab1',
      num:0,
      tab:[{
        name:"未使用",
        every:'tab1'
      },{
        name:"已使用",
        every:'tab2'
      },{
        name:"已过期",
        every:'tab3'
      }]
    }
  },
  methods:{
    Tabfn(index,item){
        this.num=index;
        this.current=item
    }
  
  },
  components:{tab1,tab2,tab3}
};
</script>

<style>
#app {
 width: 100%;
 height: 100%;
 display: flex;
 flex-direction: column;
}
.tab{
  width: 100%;
  height: 40px;
  display: flex;
  border-bottom: 1px solid #ccc;
}
.tab span{
  width: 33%;
  line-height: 40px;
  text-align: center;
}
.active{
  color: skyblue;
  border-bottom: 3px solid skyblue;
}
.main{
  flex: 1;
}
</style>
