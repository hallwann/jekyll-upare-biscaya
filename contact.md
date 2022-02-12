---
title: Contact us online
layout: page-default
---
<div class="page-header">
    <h1>{{ page.title }}</h1>
    <div class="headerdivider">
    </div>
</div>
<div class="row top30">
    <div class="col-md-6">
       <p><i class="icon-map-marker"></i> Address: No.89 Luyuan South st, Tongzhou District, Beijing.</p>
       <p><i class="icon-phone"></i> Phone1: (+8610) 6739 1947</p>
       <p><i class="icon-phone"></i> Phone2: (+0852)  6366 4860</p>
       <p><i class="icon-envelope"></i> Email: <a href="mailto:service@upare.com">service@upare.com</a></p>
    </div>
    <div class="col-md-6">
        <div class="box3">
            <div id="baiduMap" style="width:100%;height:328px;"></div>
        </div>
    </div>
</div>
<!-- CALL CONTACT FORM -->

<!-- baidu map start-->
<script type="text/javascript" src="//api.map.baidu.com/api?v=3.0&ak=FVY0ueRaPWS9MeRI9mnmgQbO"></script>
<script type="text/javascript">
    var map = new BMap.Map("baiduMap");
    map.centerAndZoom(new BMap.Point(116.67606750340146, 39.9349060820124), 20);  // 初始化地图,设置中心点坐标和地图级别
	//添加地图类型控件
	map.addControl(new BMap.MapTypeControl({
		mapTypes:[
            BMAP_NORMAL_MAP,
            BMAP_HYBRID_MAP
        ]}));	  
	map.setCurrentCity("北京");          // 设置地图显示的城市 此项是必须设置的
	map.enableScrollWheelZoom(true);     //开启鼠标滚轮缩放
	
	//创建小狐狸
	var pt = new BMap.Point(116.67609669833045, 39.93491943672401);
	var myIcon = new BMap.Icon("{{ site.asset }}/img/ico/apple-touch-icon-57-precomposed.png", new BMap.Size(50,50));
	var marker2 = new BMap.Marker(pt,{icon:myIcon});  // 创建标注
	map.addOverlay(marker2);              // 将标注添加到地图中
	marker2.setAnimation(BMAP_ANIMATION_BOUNCE);
	
</script>
<!-- baidu map end -->
