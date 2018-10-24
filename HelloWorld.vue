<template>
  <text class="message">
<text id="header">
<div class="sou">
	<!-- this is my project_Demo2 -->
    		<span>搜索</span>
    	</div>
</text>
<text id="mymain">
<section v-for="(temp,index) in list" :key='index'>
    		<h2>
    			<span>{{temp[0].classify}}&ensp;({{temp.length}})</span>
    			<i>更多&ensp;></i>
    		</h2>
    		<ul>
    			<li v-for="(value,ind) in temp" :key='ind'>
						<image style="width:170px;height:200px" :src="'http://vue.wclimb.site/images/'+value.img"></image>
    				<h5 >{{value.name}}</h5>
    				<p><span>{{value.star}}</span></p>
    			</li>
    		</ul>
    	</section>

</text>
<text id="footer">
		 <router-link to="/tab1">首页</router-link>

<text>我的</text>
</text>

  </text>
	
</template>
<script>
import axios from 'axios';
export default {
  name: 'helloword',
  components: {
    
  },
  data () {
    return {
      list:[]
      }
    },methods:{

      

  }, created(){
  	//使用axios请求数据并使用钩子函数进行初始化渲染
  	axios.get('http://vue.wclimb.site/vi/list').then((res)=>{
      this.list=res.data.data;
      console.log(this.list)
	  })
  }
}
</script>
<style>

div.weex-root {
    min-height: 100%;
    width: 100%;
    padding: 0;
    margin: 0;
    height: 100%;
}
.sou{
		width: 84%;
    height: 0.5rem;
    margin-left: 0.9rem;
		margin-top: 0.05rem;
		background: #fff;
		text-align: center;
		border-radius: 0.1rem;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.sou img{
		width:0.2rem;
		height: 0.2rem;
		margin-right: 0.05rem;
	}

	.sou span{
		font-size: 0.1rem;
		color: #333;
	}
.message{
margin: 0;
padding: 0;
width: 100%;
height: 100%;
display: flex;
flex-direction: column

}
#header{

  width: 100%;
  height: 0.6rem;
  background: #0fce0f;


}
#mymain{
  width: 100%;
  flex: 1;
  background: orange;
  overflow-y: scroll;
}

#footer{

  width: 100%;
height: 0.8rem;
background: #0fce0f;
display: flex;
flex-direction: row;
justify-content: space-around;



}
#footer text{

	text-align: center;
	line-height: 0.8rem;

}
#footer text:active{

color: red;

}

section{
		background: #f2f2f2;
	}
  section h2 {
		height: 0.55rem;
		margin: 0;
		display: flex;
		align-items: center;
		justify-content: space-between;
		background-size: 0.03rem 0.22rem;
	}
  section h2 span{
		font-size: 0.19rem;
		color:#666;
		margin-left: 0.15rem;
		font-weight: bolder;
	}
  section h2 i{
		font-size: 0.12rem;
		color: #0fce0f;
		font-weight: normal;
		margin-right: 0.22rem;
		font-style: normal;
	}
  section ul{
		height: 5.5rem;
		display: flex;
		overflow-y: hidden;
		overflow-x: scroll;
		margin-bottom: 0.12rem;
		background: #fff;
		
	}
  section ul::-webkit-scrollbar{
		display: none;
	}
  section ul li{
		list-style: none;
		width: 3.6rem;
		margin: 0.1rem;
	}
  section ul li img.img{
		display: block;
		width: 1.2rem;
		height: 0.7rem;
	}
  section ul li h5{
		font-size: 0.15rem;
		color: #666;
		line-height: 0.3rem;
	}
  section ul li p{
		font-size: 0.09rem;
		color: #666;
		margin-top: -0.1rem;
		display: flex;
	}
  section ul li p img{
		width: 0.75rem;
		height: 0.14rem;
		margin-right: 0.05rem;
	}

	
</style>


