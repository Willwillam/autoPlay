# autoPlay
JS实现轮播图

<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
	<title>Document</title>
	<style>
  *{margin:0;
    padding:0;
    list-style:none;}
  .wrap{height:170px;
        width:490px;
        margin:60px auto;
        overflow: hidden;
        position: relative;
        margin:100px auto;}
  .wrap ul{position:absolute;} 
  .wrap ul li{height:170px;}
  .wrap ol{position:absolute;
           right:5px;
           bottom:10px;}
  .wrap ol li{height:20px; width: 20px;
              background:#ccc;
              border:solid 1px #666;
              margin-left:5px;
              color:#000;
              float:left;
              line-height:center;
              text-align:center;
              cursor:pointer;}
  .wrap ol .on{background:#E97305;
               color:#fff;}

  </style>
  <script type="text/javascript">
  window.onload=function(){
    var wrap=document.getElementById('wrap'),
        pic=document.getElementById('pic').getElementsByTagName('li'),
        list=document.getElementById('list').getElementsByTagName('li'),
        index=0,
        k=0,
        timer=null;
    clearInterval(timer);
    timer=setInterval(autoplay,1500);
    function autoplay(){
        index++;
        if(index>=list.length){
            index=0;
        }
        option(index);
    }
 function option(curindex){
        for(i=0;i<list.length;i++){
            list[i].className='';
            pic[i].style.display='none';
        }
            list[curindex].className="on";
            pic[curindex].style.display="block"; 
            index=curindex;    
 }    
      // 定义并调用自动播放函数
    for(var j=0;j<list.length;j++){
        list[j].id=j;
        list[j].onmouseover=function(){
            clearInterval(timer);
          option(this.id);
        }
      
        list[j].onmouseout=function(){
         timer=setInterval(autoplay,1500);
        }
    }
    
      // 定义图片切换函数
     
     // 鼠标划过整个容器时停止自动播放

     // 鼠标离开整个容器时继续播放至下一张
    
     // 遍历所有数字导航实现划过切换至对应的图片
   }

  </script>	
</head>
<body>
  <div class="wrap" id='wrap'>
    <ul id="pic">
      <li class="display:block"><img src="http://img.mukewang.com/54111cd9000174cd04900170.jpg" alt=""></li>
      <li><img src="http://img.mukewang.com/54111dac000118af04900170.jpg" alt=""></li>
      <li><img src="http://img.mukewang.com/54111d9c0001998204900170.jpg" alt=""></li>
      <li><img src="http://img.mukewang.com/54111d8a0001f41704900170.jpg" alt=""></li>
      <li><img src="http://img.mukewang.com/54111d7d00018ba604900170.jpg" alt=""></li>    
    </ul>
    <ol id="list">
      <li class="on">1</li>
      <li>2</li>
      <li>3</li>
      <li>4</li>
      <li>5</li>
    </ol>
  </div>
</body>
</html>
