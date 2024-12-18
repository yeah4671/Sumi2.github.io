

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>안과밖</title>
  <style>
    @font-face {
      font-family: 'DungGeunMo';
      src: url('https://fastly.jsdelivr.net/gh/projectnoonnu/noonfonts_six@1.2/DungGeunMo.woff') format('woff');
      font-weight: normal;
      font-style: normal;
    }

    body {
      margin: 0;
      overflow: hidden;
      font-family: 'DungGeunMo', Arial, sans-serif; /* 기본 폰트 적용 */
    }

    #grid-container {
      display: grid;
      grid-template-columns: repeat(auto-fill, 50px); /* 격자 크기 */
      grid-template-rows: repeat(auto-fill, 50px);
      width: 100vw;
      height: 100vh;
      background-color: #f0f0f0;
      position: relative;
    }

    .grid-item {
      border: 1px solid #ccc;
      width: 50px;
      height: 50px;
      box-sizing: border-box;
      background-color: white;
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 20px;
      user-select: none;
    }

    .grid-item.active {
      background-color: #e0f7fa;
      border-color: #84ff00;
    }

    .editable-area {
      position: absolute;
      background-color: white;
      border: 2px dashed #84ff00;
      z-index: 2;
      pointer-events: auto;
      overflow: hidden;
    }

    .editable {
      width: 100%;
      height: 100%;
      padding: 10px;
      outline: none;
      border: none;
      background-color: transparent;
      font-size: 16px;
      font-family: 'DungGeunMo', Arial, sans-serif; /* 텍스트 입력 폰트 적용 */
      resize: none;
      white-space: pre-wrap; /* 줄 바꿈이 필요할 때 줄바꿈을 적용하도록 */
      word-wrap: break-word; /* 긴 단어가 잘리지 않게 처리 */
    }

    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.3);
      z-index: 1;
      pointer-events: auto;
      display: none;
    }
  </style>
</head>
<body>
  <div id="grid-container"></div>
  <div class="overlay" id="overlay"></div>

  <script>
    const gridContainer = document.getElementById('grid-container');
    const overlay = document.getElementById('overlay');
    const gridSize = 50; // 격자 크기
    const gridItems = [];
    const activeCells = new Set(); // 활성화된 셀 저장
    let isClosed = false; // 닫힌 영역 생성 여부

    // 랜덤 이모티콘 리스트
    const emojis = ['🌴', '🐩', '🐾', '🌈', '🏠', '🌱', '🌷', '🌳', '🚘', '🚲'];

    // 격자 생성
    function createGrid() {
      const cols = Math.ceil(window.innerWidth / gridSize);
      const rows = Math.ceil(window.innerHeight / gridSize);

      for (let i = 0; i < cols * rows; i++) {
        const gridItem = document.createElement('div');
        gridItem.className = 'grid-item';
        gridItem.dataset.index = i;
        gridContainer.appendChild(gridItem);
        gridItems.push(gridItem);

        // 클릭으로 활성화 처리
        gridItem.addEventListener('click', () => {
          if (isClosed) return; // 이미 닫힌 상태라면 클릭 불가

          gridItem.classList.add('active');
          activeCells.add(gridItem);

          // 닫힌 영역 체크
          if (checkClosedArea()) {
            createEditableArea();
          }
        });
      }
    }

    // 닫힌 영역 체크
    function checkClosedArea() {
      return activeCells.size >= 4; // 활성화된 셀이 최소 4개 이상이어야 닫힌 영역 생성
    }

    // 텍스트 입력 가능한 영역 생성
    function createEditableArea() {
      isClosed = true; // 닫힌 상태로 전환
      overlay.style.display = 'block'; // 나머지 화면 비활성화

      // 닫힌 영역의 위치와 크기 계산
      const positions = Array.from(activeCells).map((cell) => cell.getBoundingClientRect());
      const top = Math.min(...positions.map((pos) => pos.top));
      const left = Math.min(...positions.map((pos) => pos.left));
      const bottom = Math.max(...positions.map((pos) => pos.bottom));
      const right = Math.max(...positions.map((pos) => pos.right));
      const width = right - left;
      const height = bottom - top;

      // 텍스트 입력 영역 생성
      const editableArea = document.createElement('div');
      editableArea.className = 'editable-area';
      editableArea.style.top = `${top}px`;
      editableArea.style.left = `${left}px`;
      editableArea.style.width = `${width}px`;
      editableArea.style.height = `${height}px`;

      const editableDiv = document.createElement('textarea');
      editableDiv.className = 'editable';
      editableDiv.addEventListener('input', handleTextReplacement); // 텍스트 대체 처리
      editableArea.appendChild(editableDiv);

      gridContainer.appendChild(editableArea);
    }

    // 텍스트 대체 처리
    function handleTextReplacement(event) {
      const target = event.target;
      target.value = target.value.replace(/안/g, '▪️').replace(/밖/g, '✴︎');
    }

    // 비활성화된 격자에서 랜덤 이모티콘 표시
    function showRandomEmojis() {
      const unactivatedCells = gridItems.filter((item) => !item.classList.contains('active'));
      const randomCount = Math.min(20, unactivatedCells.length); // 최대 20개 이모티콘 표시
      const randomIndexes = new Set();

      // 랜덤 인덱스 선택
      while (randomIndexes.size < randomCount) {
        const randomIndex = Math.floor(Math.random() * unactivatedCells.length);
        randomIndexes.add(randomIndex);
      }

      // 랜덤으로 이모티콘 설정
      unactivatedCells.forEach((cell, index) => {
        if (randomIndexes.has(index)) {
          const randomEmoji = emojis[Math.floor(Math.random() * emojis.length)];
          cell.textContent = randomEmoji;
        } else {
          cell.textContent = '';
        }
      });
    }

    // 5초마다 랜덤 이모티콘 표시
    setInterval(showRandomEmojis, 5000);

    // 비활성화된 영역 클릭 방지
    overlay.addEventListener('click', () => {
      alert('활성화된 영역 안에서만 작업이 가능합니다.');
    });

    // 초기화
    createGrid();
  </script>
</body>
</html>

