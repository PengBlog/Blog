---
title: 404
layout: false
comments: false
permalink: /404
---
<!DOCTYPE html>
{% raw %}
<html>
	<head><meta name="generator" content="Hexo 3.9.0">
		<meta charset="UTF-8">
		<title>404 Not Found：该页无法显示</title>
		<style>
			#game {
				width: 100%;
				margin-top: 32px;
				text-align: center;
			}
			#msg {
				width: 100%;
				text-align: center;
				font-size: 70px;
				font-family: PingFang SC, Helvetica Neue, Hiragino Sans GB, Segoe UI, Microsoft YaHei, sans-serif
				font-weight: bold;
				color: #4f565f;
			}
		</style>

		<style>
			#clock{font-family: 'Share Tech Mono', monospace;color: #ffffff;text-align: center;position: absolute;left: 50%;top: 80%;-webkit-transform: translate(-50%, -50%);transform: translate(-50%, -50%);color: #0f3362;text-shadow: 0 0 20px #bad9fb, 0 0 20px rgba(10, 175, 230, 0);}
			#clock .time{letter-spacing: 0.05em;font-size:30px;}
			#clock .date{letter-spacing:0.1em;font-size:30px;}
			#clock .text{letter-spacing: 0.1em;font-size:12px;}
		</style>

	</head>
	<body>
		<script src="https://blog.hometosoton.tk/js/phaser.min.js"></script>
		<script src="https://blog.hometosoton.tk/js/catch-the-cat.min.js"></script>
		<script src="https://blog.hometosoton.tk/js/time.js"></script>
		<div id="game"></div>
		<script>
			window.game = new CatchTheCatGame({
				w: 9,
				h: 9,
				r: 20,
				backgroundColor: 0xffffff,
				parent: 'game',
				statusBarAlign: 'center',
				credit: 'kimiye'
			});
		</script>

		<div id="clock">
    <p class="time">{{ time }}</p>
    <p class="text">{{ date }}</p>
		<p class="text">{<a href="https://blog.hometosoton.tk">返回</a>}</p>
		</div>

		<script>
			var clock = new Vue({
			    el: '#clock',
			    data: {
			        time: '',
			        date: ''
			    }
			});
			var week = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'];
			var timerID = setInterval(updateTime, 1000);
			updateTime();
			function updateTime() {
			    var cd = new Date();
			    clock.time = zeroPadding(cd.getHours(), 2) + ':' + zeroPadding(cd.getMinutes(), 2) + ':' + zeroPadding(cd.getSeconds(), 2);
			    clock.date = zeroPadding(cd.getFullYear(), 4) + '-' + zeroPadding(cd.getMonth()+1, 2) + '-' + zeroPadding(cd.getDate(), 2) + ' ' + week[cd.getDay()];
			};
			function zeroPadding(num, digit) {
			    var zero = '';
			    for(var i = 0; i < digit; i++) {
			        zero += '0';
			    }
			    return (zero + num).slice(-digit);
			}
		</script>
	</body>
</html>
{% endraw %}
