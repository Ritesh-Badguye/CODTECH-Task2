/*javascript code*/

const quizData = [
  {
    question: "What is the capital of France?",
    a: "Berlin",
    b: "Madrid",
    c: "Paris",
    d: "Lisbon",
    correct: "c"
  },
  {
    question: "Who is the CEO of Tesla?",
    a: "Jeff Bezos",
    b: "Elon Musk",
    c: "Bill Gates",
    d: "Tony Stark",
    correct: "b"
  },
  {
    question: "What is the most used programming language in 2023?",
    a: "Java",
    b: "C",
    c: "Python",
    d: "JavaScript",
    correct: "c"
  }
];

let currentQuestion = 0;
let score = 0;

const quizContainer = document.getElementById('quiz');
const previousButton = document.getElementById('previous');
const nextButton = document.getElementById('next');
const submitButton = document.getElementById('submit');
const resultsContainer = document.getElementById('results');

loadQuiz();

function loadQuiz() {
  const currentQuizData = quizData[currentQuestion];

  quizContainer.innerHTML = `
    <div class="question">${currentQuizData.question}</div>
    <label>
      <input type="radio" name="answer" value="a">
      ${currentQuizData.a}
    </label>
    <label>
      <input type="radio" name="answer" value="b">
      ${currentQuizData.b}
    </label>
    <label>
      <input type="radio" name="answer" value="c">
      ${currentQuizData.c}
    </label>
    <label>
      <input type="radio" name="answer" value="d">
      ${currentQuizData.d}
    </label>
  `;
}

function getSelected() {
  const answers = document.getElementsByName('answer');
  let selectedAnswer;
  answers.forEach(answer => {
    if (answer.checked) {
      selectedAnswer = answer.value;
    }
  });
  return selectedAnswer;
}

function showResults() {
  quizContainer.innerHTML = '';
  resultsContainer.innerHTML = `You scored ${score} out of ${quizData.length}`;
}

previousButton.addEventListener('click', () => {
  if (currentQuestion > 0) {
    currentQuestion--;
    loadQuiz();
  }
});

nextButton.addEventListener('click', () => {
  const selectedAnswer = getSelected();
  if (selectedAnswer) {
    if (selectedAnswer === quizData[currentQuestion].correct) {
      score++;
    }
    currentQuestion++;
    if (currentQuestion < quizData.length) {
      loadQuiz();
    } else {
      showResults();
    }
  }
});

submitButton.addEventListener('click', () => {
  showResults();
});
