<template>
    <div class="container">
        <ul class="mh-menu">
			<li v-for="user in data" :key="user.login.uuid" v-on:click="toggle()">
				<a href="#"><span>{{ user.location.country }}</span> <span>{{ user.name.title+'. '+user.name.first+' '+user.name.last }}</span></a>
				<img :src="user.picture.large" :alt="'image_'+user.name.first"/>
				<!--<div :class="details_class">
					<div class="details">

					</div>
				</div>-->
			</li>
        </ul>
    </div>
	<button v-on:click="getdata()">Get New Users</button>
</template>

<script>
export default{
    name: "UserInfo",
	props:{
		getdata: Function,
		data: Array,
	},
	data(){
		return {
			show: false,
			details_class: ""
		}
	},
	method:{
		toggle(){
			this.show = !this.show;
			if(this.show){
				this.details_class = "details_show"
			}else{
				this.details_class = "details_hide"
			}
		}
	}
}
</script>

  
<style scoped>
/* CSS reset */
.details_hide{
	position: absolute;
	background: grey;
	width: 380px;
	height: 380px;
	left: 410px;
	top: -380px;
	opacity: 0;
	z-index: 2;
	-webkit-transition: top 0.4s ease-in-out, opacity 0.6s ease-in-out;
	-moz-transition: top 0.4s ease-in-out, opacity 0.6s ease-in-out;
	-o-transition: top 0.4s ease-in-out, opacity 0.6s ease-in-out;
	-ms-transition: top 0.4s ease-in-out, opacity 0.6s ease-in-out;
	transition: top 0.4s ease-in-out, opacity 0.6s ease-in-out;
}

.details_show{
	left: 410px; /*300*/
	top: 0px;
	opacity: 1;
}


body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,form,fieldset,input,textarea,p,blockquote,th,td { 
	margin:0;
	padding:0;
}
html,body {
	margin:0;
	padding:0;
	height: 100%;
}
table {
	border-collapse:collapse;
	border-spacing:0;
}
fieldset,img { 
	border:0;
}
address,caption,cite,code,dfn,th,var {
	font-style:normal;
	font-weight:normal;
}
ol,ul {
	list-style:none;
}
caption,th {
	text-align:left;
}
h1,h2,h3,h4,h5,h6 {
	font-size:100%;
	font-weight:normal;
}
q:before,q:after {
	content:'';
}
abbr,acronym { border:0;
}
section, header{
	display: block;
}
/* General Demo Style */
body{
	font-family: Cambria, Palatino, "Palatino Linotype", "Palatino LT STD", Georgia, serif;
	background: #fff;
	font-weight: 400;
	font-size: 15px;
	color: #3a2127;
	overflow-y: scroll;
}
a{
	color: #333;
	text-decoration: none;
}
.container{
	width: 100%;
	height: 100%;
	position: relative;
	text-align: center;
}
.clr{
	clear: both;
}
.container > header{
	padding: 20px 30px 20px 30px;
	margin: 0px 20px 10px 20px;
	position: relative;
	display: block;
	text-shadow: 1px 1px 1px rgba(0,0,0,0.2);
    text-align: center;
}
.container > header h1{
	position: relative;
	color: #498ea5;
	font-weight: 700;
	font-style: normal;
	font-size: 30px;
	padding: 0px 0px 5px 0px;
	text-shadow: 0px 1px 1px rgba(255,255,255,0.8);
}
.container > header h1 span{
	font-family: 'Alegreya SC', Georgia, serif;
	font-size: 20px;
	line-height: 20px;
	display: block;
	font-weight: 400;
	font-style: italic;
	color: #719dab;
	text-shadow: 1px 1px 1px rgba(0,0,0,0.1);
}
.container > header h2{
	font-size: 16px;
	font-style: italic;
	color: #2d6277;
	text-shadow: 0px 1px 1px rgba(255,255,255,0.8);
}
/* Header Style */
.codrops-top{
	line-height: 24px;
	font-size: 11px;
	background: rgba(0, 0, 0, 0.05);
	text-transform: uppercase;
	z-index: 9999;
	position: relative;
	box-shadow: 1px 0px 2px rgba(0,0,0,0.2);
}
.codrops-top a{
	padding: 0px 10px;
	letter-spacing: 1px;
	color: #333;
	text-shadow: 0px 1px 1px #fff;
	display: block;
	float: left;
}
.codrops-top a:hover{
	background: #fff;
}
.codrops-top span.right{
	float: right;
}
.codrops-top span.right a{
	float: left;
	display: block;
}
.codrops-demos{
    text-align:center;
	display: block;
	line-height: 30px;
	padding: 20px 0px;
}
.codrops-demos a{
    display: inline-block;
	margin: 0px 4px;
	padding: 0px 4px;
	color: #fff;
	line-height: 20px;	
	font-style: italic;
	font-size: 13px;
	border-radius: 3px;
	background: rgba(41,77,95,0.1);
	-webkit-transition: all 0.2s linear;
	-moz-transition: all 0.2s linear;
	-o-transition: all 0.2s linear;
	-ms-transition: all 0.2s linear;
	transition: all 0.2s linear;
}
.codrops-demos a:hover{
	background: rgba(41,77,95,0.3);
}
.codrops-demos a.current,
.codrops-demos a.current:hover{
	background: rgba(41,77,95,0.3);
}

button {
	background-color: rgba(51, 51, 51, 0.05);
	border-radius: 8px;
	border-width: 0;
	color: #333333;
	cursor: pointer;
	display: inline-block;
	font-family: "Haas Grot Text R Web", "Helvetica Neue", Helvetica, Arial, sans-serif;
	font-size: 14px;
	font-weight: 500;
	line-height: 20px;
	list-style: none;
	margin-top: 7vh;
	padding: 10px 12px;
	text-align: center;
	transition: all 200ms;
	vertical-align: baseline;
	white-space: nowrap;
	user-select: none;
	-webkit-user-select: none;
	touch-action: manipulation;
}

.mh-menu{
	height: 385px;
	width: 900px;   /*600*/
	margin: 20px auto;
	position: relative;
}
.mh-menu li{
	width: 400px; /*00*/
}
.mh-menu li a{
	display: block;
	width: 382px; /*280*/
	padding: 0px 10px;
	text-align: right;
	position: relative;
	z-index: 10;
	background: #fff;
	height: 97px;
	border-right: 1px solid #ddd;
	background: rgba(255,255,255, 0.8);
}
.mh-menu li:hover a{
	background: rgba(255,255,255, 1);
}
.mh-menu li a span{
	display:block;
}
.mh-menu li a span:first-child{
	font-weight: 700;
	font-size: 16px;
	color: #ddd;
	padding-top: 10px;
	font-family: 'Alegreya SC', Georgia, serif;
}
.mh-menu li a span:nth-child(2){
	font-weight: 400;
	font-style: italic;
	font-size: 28px;
	font-family: 'Alegreya SC', Georgia, serif;
	-webkit-transition: color 0.2s linear;
	-moz-transition: color 0.2s linear;
	-o-transition: color 0.2s linear;
	-ms-transition: color 0.2s linear;
	transition: color 0.2s linear;
}
.mh-menu li:nth-child(1):hover span:nth-child(2){
	color: #ae3637;
}
.mh-menu li:nth-child(2):hover span:nth-child(2){
	color: #c3d243;
}
.mh-menu li:nth-child(3):hover span:nth-child(2){
	color: #d38439;
}
.mh-menu li:nth-child(4):hover span:nth-child(2){
	color: #8e7463;
}
.mh-menu li img{
	position: absolute;
	width: 380px;
	height: 380px;
	z-index: 1;
	left: 0px;
	top: 0px;
	opacity: 0;
	-webkit-transition: left 0.4s ease-in-out, opacity 0.6s ease-in-out;
	-moz-transition: left 0.4s ease-in-out, opacity 0.6s ease-in-out;
	-o-transition: left 0.4s ease-in-out, opacity 0.6s ease-in-out;
	-ms-transition: left 0.4s ease-in-out, opacity 0.6s ease-in-out;
	transition: left 0.4s ease-in-out, opacity 0.6s ease-in-out;
}
.mh-menu li:hover img{
	left: 410px; /*300*/
	opacity: 1;
}
</style>
