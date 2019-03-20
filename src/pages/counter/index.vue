<!--  -->
<template>
<div class=''>
    <div class="table-box">
        <div class="td-box">
            <div>异步时钟:</div>
            <div> 
                <input size="17" name="F" value="32.768" type="text">
             </div>
            <div>KHz</div>
        </div>
        <div class="td-box">
            <div>波特率：</div>
            <div><input size="17" name="Baud" value="2.4" type="text"></div>
            <div>KHz</div>
        </div>
        <div class="td-box">
            <div>数字（包括启动,校验,停止位）</div>
            <div> <input size="3" name="Bits" value="10" type="text"></div>
            <div>13</div>
        </div>
    </div>
    <div class="table-box">
        <div class="td-box"> 
            <div style="width:100%">
                <button style="width:150rpx;height:60rpx;font-size:14px;margin:4rpx auto">寄存值计算</button>
            </div>
        </div>    
    </div>
    <div class="table-box">
        <div class="td-box">
            <div>UxMCTL (调制寄存器)</div>
            <div> 
                <input size="17" name="F" value="" type="text">
             </div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
        <div class="td-box">
            <div>UxBR0 (波特率 LSW)</div>
            <div><input size="17" name="Baud" value="" type="text"></div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
        <div class="td-box">
            <div>UxBR1 (波特率 MSW)</div>
            <div> <input size="3" name="Bits" value="" type="text"></div>
            <div></div>
        </div>
    </div>
    <div class="table-box">
             <div class="td-box"> 
            <div style="width:100%;text-align:center">
                误码百分比
            </div>
        </div>  
    </div>
    <div class="table-box">
          <div class="td-box">
            <div></div>
            <div> 
                TX
             </div>
            <div>RX</div>
        </div>
        <div class="td-box">
            <div>Bit 0</div>
            <div><input size="17" name="Baud" value="" type="text"></div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
        <div class="td-box">
            <div>Bit 1</div>
            <div> <input size="3" name="Bits" value="" type="text"></div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>     <div class="td-box">
            <div>Bit 2</div>
            <div> 
                <input size="17" name="F" value="" type="text">
             </div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
        <div class="td-box">
            <div>Bit 3</div>
            <div><input size="17" name="Baud" value="" type="text"></div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
        <div class="td-box">
            <div>Bit 4</div>
            <div> <input size="3" name="Bits" value="" type="text"></div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>     <div class="td-box">
            <div>Bit 5</div>
            <div> 
                <input size="17" name="F" value="" type="text">
             </div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
        <div class="td-box">
            <div>Bit 6</div>
            <div><input size="17" name="Baud" value="" type="text"></div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
        <div class="td-box">
            <div>Bit 7</div>
            <div> <input size="3" name="Bits" value="" type="text"></div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
           <div class="td-box">
            <div>Bit 8</div>
            <div> <input size="3" name="Bits" value="" type="text"></div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
          <div class="td-box">
            <div>Bit 9</div>
            <div> <input size="3" name="Bits" value="" type="text"></div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
          <div class="td-box">
            <div>Bit 10</div>
            <div> <input size="3" name="Bits" value="" type="text"></div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
          <div class="td-box">
            <div>Bit 11</div>
            <div> <input size="3" name="Bits" value="" type="text"></div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
          <div class="td-box">
            <div>Bit 12</div>
            <div> <input size="3" name="Bits" value="" type="text"></div>
            <div><input size="3" name="Bits" value="" type="text"></div>
        </div>
         
    </div>

</div>
</template>

<script>
//这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
//例如：import 《组件名称》 from '《组件路径》';

export default {
//import引入的组件需要注入到对象中才能使用
components: {},
data() {
//这里存放数据
return {

};
},
//监听属性 类似于data概念
computed: {},
//监控data中的数据变化
watch: {},
//方法集合
methods: {

},
//生命周期 - 创建完成（可以访问当前this实例）
created() {

},
//生命周期 - 挂载完成（可以访问DOM元素）
mounted() {

},
}
</script>
<style  scoped>
.table-box{
    width: 100%;
    font-size: 14px;
}
.td-box{
    width: 100%;
    display: flex;
}
.td-box div{
    width: 25%;
    border: 1rpx solid #eee;
    justify-content: center;
    align-items: center;
    text-align: left;
    line-height: 50rpx;
    padding: 4rpx;

}
.td-box div:first-child{
    width: 50%;
}
.td-box div input{
    border: 1rpx solid #eee;
}
</style>