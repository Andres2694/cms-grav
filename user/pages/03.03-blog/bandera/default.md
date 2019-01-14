---
title: Bandera
---

En este apartado utilizamos codigo sgv y canvas para construir una bandera
* Codigo Svg
 <svg xmlns="http://www.w3.org/2000/svg" width="400" height="600">
      <rect width="150" height="100" style="fill:rgb(255,255,255);stroke-width:none;stroke:rgb(0,0,0)" />
      <g transform="translate(37,17)">
        <polygon points="25,2.5 10,49.5 47.5,19.5 2.5,19.5 40,49.5" style="fill:blue;stroke:none;stroke-width:2;fill-rule:nonzero;"/>
        </g>
      <rect x="150" y="0" width="150" height="100" style="fill:rgb(255,0,0);stroke-width:none;stroke:rgb(0,0,0)"/>
        <rect x="0" y="100" width="150" height="100" style="fill:rgb(0,0,255);stroke-width:none;stroke:rgb(0,0,0)"/>
        <rect x="150" y="100" width="150" height="100" style="fill:rgb(255,255,255);stroke-width:none;stroke:rgb(0,0,0)"/>
        <g transform="translate(190,120)">
        <polygon points="25,2.5 10,49.5 47.5,19.5 2.5,19.5 40,49.5" style="fill:red;stroke:none;stroke-width:2;fill-rule:nonzero;"/>
        </g>
        Sorry, your brow ser does not support inline SVG. 
    
*   Codigo Canvas:
var canvas = document.getElementById("canvas");
var ctx = canvas.getContext("2d");
drawFlag();
drawStar(100,70,5,30,15,'blue');
drawStar(300,217,5,30,15,'red');
function drawFlag() {
  ctx.fillStyle = "rgb(255,0,0)";
  ctx.fillRect(200, 0, 200, 150);
  ctx.fillStyle = "rgb(0,0,255)";
  ctx.fillRect(0, 150, 200, 150);

}
 function drawStar(posicionx,posiciony,puntas,radioexterno,radiointerno,color){
      var rot=Math.PI/2*3;
      var x=posicionx;
      var y=posiciony;
      var step=Math.PI/puntas;
      var colorstar=color;

      ctx.beginPath();
      ctx.moveTo(posicionx,posiciony-radioexterno)
      for(i=0;i < puntas;i++){
        x=posicionx+Math.cos(rot)*radioexterno;
        y=posiciony+Math.sin(rot)*radioexterno;
        ctx.lineTo(x,y)
        rot+=step

        x=posicionx+Math.cos(rot)*radiointerno;
        y=posiciony+Math.sin(rot)*radiointerno;
        ctx.lineTo(x,y)
        rot+=step
      }
      ctx.lineTo(posicionx,posiciony-radioexterno);
      ctx.closePath();
      ctx.lineWidth=5;
      ctx.strokeStyle=colorstar;
      ctx.stroke();
      ctx.fillStyle=colorstar;
      ctx.fill();
    }
          
          