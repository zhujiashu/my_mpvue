<template>
  <div @click="clickHandle" class="page-list">
    <router-link to='../counter/main'></router-link>
        <van-collapse  :value="activeNames" @change="onChange">
        <van-collapse-item  name="0">
           <view slot="title" style="display:flex;align-items: center; justify-content:space-between">最近使用
             <img src="../../../static/NEW.png"  style="width:33px;height:15px;"/>
          </view>
           <div class="swiper-home">
            <scroll-view scroll-x="true" style="width: 100%">
                <view class="swiper-item" v-for="(item,index) in dataListST" :key="index" >
                   <div style="overflow:hidden; text-overflow:ellipsis;display:-webkit-box; -webkit-box-orient:vertical;-webkit-line-clamp:2; ">
                      {{item.name}}
                   </div>
                </view>
            </scroll-view>
            </div>
        </van-collapse-item>
    </van-collapse>

    <van-collapse  :value="activeNames" @change="onChange">
        <van-collapse-item  v-for="(item,index) in dataList" :key="index" :name="index" >
          <view slot="title" style="display:flex;align-items: center; justify-content:space-between">{{item.name}} 
            <img src="../../../static/NEW.png" v-if="item.cornerStatus == '3'" style="width:33px;height:15px;"/>
          </view>
          <div class="tools-list">
            <button class="open-type tool-item" v-for="(items,itemsindex) in item.tools" :key="itemsindex" plain  data-id="17" :data-href="items.url">
            <img class="tool-icon" :src="items.imgUrl" alt="">
            <p class="tool-text">{{items.name}}</p>
          </button>
          </div>

        </van-collapse-item>
    </van-collapse>

 <picker-view
        indicator-style="height: 42px;"
        style="width: 100%; height: 300px;margin:5px 0px ;background-color:#fff"
        :value="value"
        @change="bindChange"
     >
     <!-- 第一环 -->
    <picker-view-column class="sh-box">
      <view v-for="(item,index) in colorsList" :key="index"  class="colorBox" :style="'background-color:'+ item.color " ><span :style="item.name == '白色'? 'color:'+'#000':'color:'+'#fff'">{{item.name}}</span></view>
    </picker-view-column>
    <!-- 第二环 -->
     <picker-view-column class="sh-box">
      <view v-for="(item,index) in colorsList" :key="index" class="colorBox" :style="'background-color:'+ item.color"><span :style="item.name == '白色'? 'color:'+'#000':'color:'+'#fff'">{{item.name}}</span></view>
    </picker-view-column>
    <!-- 第三环 -->
     <picker-view-column class="sh-box">
      <view v-for="(item,index) in colorsList" :key="index" class="colorBox" :style="'background-color:'+ item.color"><span :style="item.name == '白色'? 'color:'+'#000':'color:'+'#fff'">{{item.name}}</span></view>
    </picker-view-column>
    <!-- 第四环 -->
    <picker-view-column class="sh-box">
      <view v-for="(item,index) in colorsList" :key="index" class="colorBox" :style="'background-color:'+ item.color"><span :style="item.name == '白色'? 'color:'+'#000':'color:'+'#fff'">{{item.name}}</span></view>
    </picker-view-column>
    <!-- 第五环 -->
    <picker-view-column class="sh-box">
      <view v-for="(item,index) in colorsList" :key="index" class="colorBox" :style="'background-color:'+ item.color" ><span :style="item.name == '白色'? 'color:'+'#000':'color:'+'#fff'">{{item.name}}</span></view>
    </picker-view-column>
     </picker-view>

  </div>
</template>

<script>
import card from '@/components/card'
import dataList from '../../../data.json'
import dataListST from '../../../dataListST.json'
export default {
  data () {
    return {
        name: 'name1',
        activeNames: ['1'],
        dataList:dataList.data,
        dataListST:dataListST.data,
   
    colorsList:[
        {name:'黑色',id:0,color:'#000000'},
        {name:'棕色',id:1,color:'#785549'},
        {name:'红色',id:2,color:'#e0232c'},
        {name:'橙色',id:3,color:'#fb8e25'},
        {name:'黄色',id:4,color:'#fed431'},
        {name:'绿色',id:5,color:'#34992d'},
        {name:'蓝色',id:6,color:'#21abf1'},
        {name:'紫色',id:7,color:'#6442b4'},
        {name:'灰色',id:8,color:'#9e9e9e'},
        {name:'白色',id:9,color:'#ffffff'},
        {name:'金色',id:10,color:'#cda139'},
        {name:'银色',id:11,color:'#bdbdbe'}
        ]


    }
  },

  components: {
    card
  },

  methods: {
    onChange(event) {
  console.log(event)
      this.activeNames= event.mp.detail
    
  },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
    },
    
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped>
 .sh-box{
    margin: 0 4rpx;
  }
  .colorBox{
    width: 50px;
    height: 42px;
    font-size: 13px;/*px*/
    text-align: center;
    color: #fff;
    line-height: 50px;
  }
  .page-list {
    background-color: #10202E;
    color: #93A1B4;
    border-top: none;
  }
.swiper-home{
        width: 100%;
        height: 162rpx;
        box-sizing: border-box;
        display: flex;
        white-space: nowrap;
        
    }
            .swiper-item{
            width: 216rpx;
            height: 100%;
            display: inline-block;
        }
        .tools-list {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-wrap: wrap;
        background-color: #10202E;
        }
         .tool-item {
          padding: 0 10rpx;
          flex: 1;
          border-right: 1rpx solid #51555B;
          border-bottom: 1rpx solid #51555B;
          height: 240rpx;
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          min-width: 200rpx;
        }
              .tool-icon {
            margin-top: 25rpx;
            width: 70rpx;
            height: 70rpx;
          }
          .tool-text {
            font-size: 14px;
            margin-top: 25rpx;
            text-align: center;
            color: rgba(255, 255, 255, .8);
            width: 70px;
            line-height: 35px;
                display: -webkit-box;
                overflow: hidden;
                text-overflow: ellipsis;
                word-break: break-all;
                -webkit-box-orient: vertical;
                -webkit-line-clamp: 2;
          }
      
</style>
