#使用百度地图拾取坐标

----------

　　利用百度官方提供的坐标拾取工具做了简单的改造和封装，更方便的集成到项目中（百度官方的坐标拾取工具[http://api.map.baidu.com/lbsapi/getpoint/index.html](http://api.map.baidu.com/lbsapi/getpoint/index.html)）
  	
 - 项目中使用
	
    

		//HTML部分
    	<div>
	    	<div>gps地址:<span id="gpsAddr"></span></div>
	    	<div>坐标：<span id="location"></span></div>
	    	<div><input type="button" id="selectBtn" value="地图选点"></div>
    	</div>

		//引入js，调用初始化方法即可
    	<script src="js/selectLocation.js"></script>
    	<script type="text/javascript">
	    	SelectLocation.init({
		    	id:'selectBtn', //打开地图窗口按钮的ID
		    	url:'bdMap.html',   //地图页面的地址
		    	//width:'1024',//打开地图窗口的宽度,可不传
		    	//height:'800',//打开地图窗口的高度,可不传
		    	//top:'50',//打开地图窗口距显示器顶部的距离,可不传
		    	//left:'100',  //打开地图窗口显示器左边的距离,可不传
		    	callback:function(selectedLocation){
			    	var gpsAddr = document.getElementById('gpsAddr');
			    	var location = document.getElementById('location');
			    	
			    	gpsAddr.innerHTML = selectedLocation.gpsAddr;
			    	location.innerHTML = selectedLocation.location;
		    	}
	    	});
    	</script>


