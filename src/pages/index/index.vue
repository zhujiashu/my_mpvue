<template>
  <div @click="clickHandle" class="page-list">
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
        dataListST:dataListST.data
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
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped>
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
            height: 76rpx;
            overflow:hidden;
             text-overflow:ellipsis;
             display:-webkit-box;
              -webkit-box-orient:vertical;
              -webkit-line-clamp:2;
          }
      
</style>
