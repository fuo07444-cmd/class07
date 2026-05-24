<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script src="src/script.js"></script>
  </head>
  <body onload="init()">
    <canvas id="canvas" width="700" height="400"></canvas>
  </body>
</html>
function init() {
  let canvas = document.getElementById("canvas");
  let ctx = canvas.getContext("2d");

  // ===== フランス国旗 =====
  let fX = 50;
  let fY = 80;
  let fW = 180;
  let fH = 120;
  let stripe = fW / 3;

  // 黒い縁取り
  ctx.fillStyle = "#000000";
  ctx.fillRect(fX - 1, fY - 1, fW + 2, fH + 2);

  // 青
  ctx.fillStyle = "#0000FF";
  ctx.fillRect(fX, fY, stripe, fH);

  // 白
  ctx.fillStyle = "#FFFFFF";
  ctx.fillRect(fX + stripe, fY, stripe, fH);

  // 赤
  ctx.fillStyle = "#FF0000";
  ctx.fillRect(fX + stripe * 2, fY, stripe, fH);

  // ===== モルディブ国旗 =====
  let mX = 300;
  let mY = 80;
  let mW = 180;
  let mH = 120;

  // 黒い縁取り
  ctx.fillStyle = "#000000";
  ctx.fillRect(mX - 1, mY - 1, mW + 2, mH + 2);

  // 赤い外枠（見本通りの太さ）
  ctx.fillStyle = "#D00000";
  ctx.fillRect(mX, mY, mW, mH);

  // 緑の内側（赤枠より少し内側）
  let margin = 13;
  ctx.fillStyle = "#007E3A";
  ctx.fillRect(mX + margin, mY + margin, mW - margin * 2, mH - margin * 2);

  // 白い三日月（細く右向き）
  let cx = mX + mW / 2;
  let cy = mY + mH / 2;
  let outerR = 35;
  let innerR = 30;

  // 外側の白い円
  ctx.beginPath();
  ctx.arc(cx, cy, outerR, 0, Math.PI * 2);
  ctx.fillStyle = "#FFFFFF";
  ctx.fill();

  // 内側の緑の円（右へずらして細い三日月に）
  ctx.beginPath();
  ctx.arc(cx + 15, cy, innerR, 0, Math.PI * 2);
  ctx.fillStyle = "#007E3A";
  ctx.fill();
}
