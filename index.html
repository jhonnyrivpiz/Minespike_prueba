<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Minespike Game</title>
<style>
  body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f9;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
  }
  .game-container {
    display: grid;
    gap: 2px;
  }
  .cell {
    width: 30px;
    height: 30px;
    background-color: #ddd;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    border: 1px solid #bbb;
    font-size: 18px;
    font-weight: bold;
  }
  .cell.revealed {
    background-color: #fff;
    cursor: default;
  }
  .cell.mine {
    background-color: red;
  }
  .cell.flagged {
    background-color: yellow;
  }
  .game-info {
    margin-bottom: 10px;
    text-align: center;
  }
</style>
</head>
<body>

<div class="game-info">
  <button onclick="resetGame()">Reset Game</button>
  <span id="mine-count">Mines: 10</span>
</div>
<div class="game-container" id="game-container"></div>

<script>
const rows = 10, cols = 10, mineCount = 10;
let board = [], minePositions = new Set();

function createBoard() {
  const container = document.getElementById('game-container');
  container.style.gridTemplateRows = `repeat(${rows}, 30px)`;
  container.style.gridTemplateColumns = `repeat(${cols}, 30px)`;
  container.innerHTML = '';
  board = Array.from({ length: rows }, () => Array(cols).fill(null));

  for (let r = 0; r < rows; r++) {
    for (let c = 0; c < cols; c++) {
      const cell = document.createElement('div');
      cell.classList.add('cell');
      cell.dataset.row = r;
      cell.dataset.col = c;
      cell.addEventListener('click', handleClick);
      cell.addEventListener('contextmenu', handleRightClick);
      container.appendChild(cell);
      board[r][c] = { element: cell, isMine: false, revealed: false, flagged: false, adjacentMines: 0 };
    }
  }

  placeMines();
  calculateAdjacentMines();
}

function placeMines() {
  let placedMines = 0;
  while (placedMines < mineCount) {
    const r = Math.floor(Math.random() * rows);
    const c = Math.floor(Math.random() * cols);
    const pos = `${r},${c}`;
    if (!minePositions.has(pos)) {
      minePositions.add(pos);
      board[r][c].isMine = true;
      placedMines++;
    }
  }
}

function calculateAdjacentMines() {
  const directions = [
    [-1, -1], [-1, 0], [-1, 1],
    [0, -1],          [0, 1],
    [1, -1], [1, 0], [1, 1]
  ];

  for (let r = 0; r < rows; r++) {
    for (let c = 0; c < cols; c++) {
      if (board[r][c].isMine) continue;

      let count = 0;
      for (const [dr, dc] of directions) {
        const nr = r + dr, nc = c + dc;
        if (nr >= 0 && nr < rows && nc >= 0 && nc < cols && board[nr][nc].isMine) {
          count++;
        }
      }
      board[r][c].adjacentMines = count;
    }
  }
}

function handleClick(e) {
  const cell = e.target;
  const row = parseInt(cell.dataset.row), col = parseInt(cell.dataset.col);
  const data = board[row][col];

  if (data.revealed || data.flagged) return;

  revealCell(row, col);

  if (data.isMine) {
    endGame(false);
  } else if (checkWin()) {
    endGame(true);
  }
}

function revealCell(row, col) {
  const data = board[row][col];
  if (data.revealed) return;

  data.revealed = true;
  data.element.classList.add('revealed');

  if (data.adjacentMines > 0) {
    data.element.textContent = data.adjacentMines;
  } else {
    const directions = [
      [-1, -1], [-1, 0], [-1, 1],
      [0, -1],          [0, 1],
      [1, -1], [1, 0], [1, 1]
    ];

    for (const [dr, dc] of directions) {
      const nr = row + dr, nc = col + dc;
      if (nr >= 0 && nr < rows && nc >= 0 && nc < cols) {
        revealCell(nr, nc);
      }
    }
  }
}

function handleRightClick(e) {
  e.preventDefault();
  const cell = e.target;
  const row = parseInt(cell.dataset.row), col = parseInt(cell.dataset.col);
  const data = board[row][col];

  if (data.revealed) return;

  data.flagged = !data.flagged;
  data.element.classList.toggle('flagged');

  updateMineCount(data.flagged ? -1 : 1);
}

function updateMineCount(change) {
  const mineCountElement = document.getElementById('mine-count');
  const currentCount = parseInt(mineCountElement.textContent.split(': ')[1]);
  mineCountElement.textContent = `Mines: ${currentCount + change}`;
}

function checkWin() {
  for (let r = 0; r < rows; r++) {
    for (let c = 0; c < cols; c++) {
      const data = board[r][c];
      if (!data.isMine && !data.revealed) return false;
    }
  }
  return true;
}

function endGame(won) {
  for (let r = 0; r < rows; r++) {
    for (let c = 0; c < cols; c++) {
      const data = board[r][c];
      if (data.isMine) data.element.classList.add('mine');
      data.element.style.pointerEvents = 'none';
    }
  }

  setTimeout(() => alert(won ? "You win!" : "Game over!"), 100);
}

function resetGame() {
  minePositions.clear();
  createBoard();
}

createBoard();
</script>

</body>
</html>
