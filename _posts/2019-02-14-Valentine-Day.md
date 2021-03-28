---
title: Happy Valentine's Day
tags: Anniversary
---

回忆了一下，可能是在20年这个情人节，我制作了这个页面。但是之前那个博客，可能是由于换服务器，换域名让这个页面消失了。这次制作这个博客的时候，我的用github已经十分熟练，对服务器的操作也比较熟悉，更重要的是找到了一个比较便宜的域名。希望这个博客能够保留下来，至少源文件我已经放到了github上。

--------
下面这个玫瑰，是用纯代码绘制的，大概就是一堆数学公式吧。

--------
<div style="text-align: center"> 
    <canvas id="c"></canvas> 
</div>

<script type="text/javascript">
    var canvas = document.getElementsByTagName('canvas')[0];
    var context = canvas.getContext('2d'); 

    var a = context; 
    var b = document.body;
    var c = canvas;

    document.body.clientWidth; 
    var zBuffer = []; 
    var SIZE = 777;
    canvas.width = canvas.height = SIZE;
    var h = -350; 

    function surface(a, b, c) {  
        if (c > 60) {  
            return {   
                x : Math.sin(a * 7) * (13 + 5 / (.2 + Math.pow(b * 4, 4)))  - Math.sin(b) * 50,  
                y : b * SIZE + 50,   
                z : 625 + Math.cos(a * 7)   * (13 + 5 / (.2 + Math.pow(b * 4, 4))) + b * 400,  
                r : a * 1 - b / 2,  g : a  };  
            } 

        var A = a * 2 - 1;
        var B = b * 2 - 1; 

        if (A * A + B * B < 1) {
        if (c > 37) { 
            var j = c & 1;  
            var n = j ? 6 : 4;   
            var o = .5 / (a + .01) + Math.cos(b * 125) * 3 - a * 300;  
            var w = b * h;  
            return {   
                x : o * Math.cos(n) + w * Math.sin(n) + j * 610 - 390,  
                y : o * Math.sin(n) - w * Math.cos(n) + 550 - j * 350,  
                z : 1180 + Math.cos(B + A) * 99 - j * 300,  
                r : .4  - a  * .1   + Math.pow(1 - B * B, -h * 6)  * .15  - a  * b  * .4   + Math.cos(a + b)  / 5   + Math.pow(Math.cos((o * (a + 1) + (B > 0 ? w  : -w)) / 25), 30) * .1 * (1 - B * B),  g : o / 1e3 + .7 - o * w * 3e-6
            };  
        }

        if (c > 32) {  
            c = c * 1.16 - .15;  
            var o = a * 45 - 20;  
            var w = b * b * h;  
            var z = o * Math.sin(c) + w * Math.cos(c) + 620;  
            return {  
                x : o * Math.cos(c) - w * Math.sin(c),  
                y : 28 + Math.cos(B * .5) * 99 - b * b * b * 60 - z / 2  - h,  
                z : z,  
                r : (b * b * .3 + Math.pow((1 - (A * A)), 7) * .15 + .3)  * b,  
                g : b * .7  
            };  
        }

        var o = A * (2 - b) * (80 - c * 2);  
        var w = 99 - Math.cos(A) * 120 - Math.cos(b) * (-h - c * 4.9)  + Math.cos(Math.pow(1 - b, 7)) * 50 + c * 2;  
        var z = o * Math.sin(c) + w * Math.cos(c) + 700;  
        return {  
            x : o * Math.cos(c) - w * Math.sin(c),  
            y : B * 99 - Math.cos(Math.pow(b, 7)) * 50 - c / 3 - z  / 1.35 + 450,  z : z,  
            r : (1 - b / 1.2) * .9 + a * .1,  
            g : Math.pow((1 - b), 20) / 4 + .05  
        };  
        }  
    }   

    setInterval(function() {  
        for ( var i = 0; i < 10000; i++) {   
            var part = i % 46;   
            var c = part / .74;   
            var point = surface(Math.random(), Math.random(), c);  
            if (point) {  
                var z = point.z;  
                var x = parseInt(point.x * SIZE / z - h);  
                var y = parseInt(point.y * SIZE / z - h);  
                var zBufferIndex = y * SIZE + x;  
                if ((typeof zBuffer[zBufferIndex] === "undefined")  || (zBuffer[zBufferIndex] > z)) {  
                    zBuffer[zBufferIndex] = z;   
                    var r = -parseInt(point.r * h);  var g = -parseInt(point.g * h);  
                    var b = -parseInt(point.r * point.r * -80);   
                    context.fillStyle = "rgb(" + r + "," + g + "," + b  + ")";  
                    context.fillRect(x, y, 1, 1);  
                }  
            }  
        }  
    }, 0);  
</script>
--------

这是一个纯JS绘制的玫瑰花，每片叶子和花瓣都单独绘制，最后按照投影的规则展示出这个样子。都说工科生不懂浪漫，我也不知道这朵玫瑰能否给你丝丝惊喜。2年后的我，回看这段往事，发现，当初的笨笨的小孩，现在也会偷偷在给你的外卖里面点上一束玫瑰，给你惊喜。但是，这笨笨的小孩，也许就是你最初喜欢的样子吧。

情人节快乐，小宝，希望每天都是幸福的一天。

