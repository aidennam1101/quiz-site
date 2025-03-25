# quiz-site
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>이번 주 블로그 퀴즈!</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: #f9f9f9;
      padding: 30px;
      color: #333;
      max-width: 700px;
      margin: auto;
    }
    h1 {
      text-align: center;
      color: #4CAF50;
    }
    .question {
      margin-bottom: 20px;
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    }
    button {
      background-color: #4CAF50;
      color: white;
      border: none;
      padding: 10px 20px;
      margin-top: 20px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
    }
    .result {
      margin-top: 30px;
      background: #e7ffe7;
      border-left: 5px solid #4CAF50;
      padding: 15px;
      font-weight: bold;
    }
    .hidden { display: none; }
    label { display: block; margin: 8px 0; }
  </style>
</head>
<body>

  <h1>🧠 이번 주 블로그 퀴즈!</h1>
  <p style="text-align:center">이번 주 내가 올린 글들, 얼마나 기억하고 있나요? 총 5문제! 맞춰보세요 🎯</p>

  <form id="quizForm">
    <div class="question">
      <p>1. 인간형 로봇은 몇 년 안에 상용화될 것으로 예상되나요?</p>
      <label><input type="radio" name="q1" value="a"> 10년 후</label>
      <label><input type="radio" name="q1" value="b"> 20년 후</label>
      <label><input type="radio" name="q1" value="c"> 몇 년 안</label>
    </div>

    <div class="question">
      <p>2. 일본 정부가 쌀 부족으로 비축미를 풀게 된 가장 큰 원인은?</p>
      <label><input type="radio" name="q2" value="a"> 수출 과잉</label>
      <label><input type="radio" name="q2" value="b"> 폭염과 공급 불안</label>
      <label><input type="radio" name="q2" value="c"> 쌀 소비 감소</label>
    </div>

    <div class="question">
      <p>3. 상파울루 카니발에서 파워레인저로 위장했던 사람들의 정체는?</p>
      <label><input type="radio" name="q3" value="a"> 연기자</label>
      <label><input type="radio" name="q3" value="b"> 소매상</label>
      <label><input type="radio" name="q3" value="c"> 경찰</label>
    </div>

    <div class="question">
      <p>4. 세계에서 가장 오염된 도시 대부분은 어느 대륙에 있나요?</p>
      <label><input type="radio" name="q4" value="a"> 유럽</label>
      <label><input type="radio" name="q4" value="b"> 아시아</label>
      <label><input type="radio" name="q4" value="c"> 아프리카</label>
    </div>

    <div class="question">
      <p>5. 캐나다에서 테슬라 차량이 공격받은 주요 배경은?</p>
      <label><input type="radio" name="q5" value="a"> 정비 문제</label>
      <label><input type="radio" name="q5" value="b"> 무역 갈등과 엘론 머스크에 대한 반감</label>
      <label><input type="radio" name="q5" value="c"> 주차 공간 문제</label>
    </div>

    <button type="button" onclick="checkAnswers()">제출하고 결과 확인하기 🔍</button>
  </form>

  <div id="result" class="result hidden"></div>

  <script>
    const correctAnswers = ['c', 'b', 'c', 'b', 'b'];

    function checkAnswers() {
      const form = document.getElementById('quizForm');
      const resultBox = document.getElementById('result');
      let score = 0;
      correctAnswers.forEach((answer, index) => {
        const q = form[`q${index+1}`];
        if (q.value === answer) score++;
      });
      resultBox.classList.remove('hidden');
      resultBox.innerHTML = `✅ 당신의 점수는 <strong>${score}/5</strong> 입니다! ${score === 5 ? '완벽해요! 💯' : '조금 아쉽네요! 😅 다시 도전해보세요!'}`;
    }
  </script>
</body>
</html>
