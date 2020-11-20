# 移动端问题汇总

### h5+app问题

1. 在谷歌浏览器访问后台请求的图片时，如果图片地址时http协议的，谷歌会自动跳转到https协议，造成图片显示异常问题，处理方法如下
   - ![1.png](https://i.loli.net/2020/11/20/TLhzrbFOSPwD5tk.png)
   - ![2.png](https://i.loli.net/2020/11/20/BFql3eNpXHOizVQ.png)

### 小程序问题

1. ucharts绘制canvas时，由于小程序自身问题，造成canvas层级过高，透出遮罩层处理方法

   - 把ucharts绘制的canvas转换成图片格式（png）

     ```js
     canvaLineA.addEventListener('renderComplete', () => {//监控图表渲染完成
     	setTimeout(function(){//延迟一定时间执行
     		uni.canvasToTempFilePath({//将图表转成图片
     			x: 0,
     			y: 0,
     			width: _self.cWidth*_self.pixelRatio,
     			height: _self.cHeight*_self.pixelRatio,
     			fileType:'png',
     			canvasId: 'canvasLineA',
     			success: function(res) {
     				_this.canvasLineAImgSrc=res.tempFilePath;
     				// console.log('这里面的代码执行了',res)
     			},
     			fail:function(res){
     			console.log('执行失败了',res)
     			}
     		},_this);
     	},100);
     });
     ```

     > 