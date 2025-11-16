# 100-000-squares-of-advertisements-and-opinions.-One-only-costs-0.5-dollars.
You can share any advertisements and opinions you want to share here. Make pictures and put them on the grid. Of course, the bigger the grid, the more people will see it.
<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<title>我的格子廣告網站</title>
<style>
  body { font-family: Arial; text-align: center; background-color: #f9f9f9; }
  h1 { margin-top: 20px; }
  .grid { 
    display: grid; 
    grid-template-columns: repeat(10, 60px); 
    grid-gap: 2px; 
    justify-content: center; 
    margin-top: 20px;
  }
  .cell {
    width: 60px; height: 60px; border: 1px solid #333; 
    display: flex; align-items: center; justify-content: center; 
    cursor: pointer; background-color: #eee;
    overflow: hidden;
  }
  .cell.sold { background-color: gold; }
  .cell img { width: 100%; height: 100%; object-fit: cover; }
</style>
</head>
<body>

<h1>我的格子廣告網站</h1>
<p>每格 10 元，點擊格子可以「購買」</p>

<div class="grid" id="grid"></div>

<script>
const grid = document.getElementById('grid');
const rows = 10;
const cols = 10;

// 建立格子
for (let i = 0; i < rows*cols; i++) {
  const cell = document.createElement('div');
  cell.className = 'cell';
  cell.textContent = i+1; // 格子編號

  // 點擊事件：模擬購買
  cell.onclick = () => {
    if (!cell.classList.contains('sold')) {
      cell.classList.add('sold'); // 改顏色
      cell.textContent = ""; // 清除編號
      // 放置廣告圖片
      const img = document.createElement('img');
      img.src = "https://via.placeholder.com/60"; // 可換成自己的圖片網址
      cell.appendChild(img);
      alert(`你「購買」了格子 ${i+1}！`);
    }
  };
  grid.appendChild(cell);
}
</script>

</body>
</html>
