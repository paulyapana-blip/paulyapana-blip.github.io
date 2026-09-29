# paulyapana-blip.github.io
Parallel Postulate Activity #02
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>History of the Parallel Postulate</title>

<style>
    * {
        box-sizing: border-box;
    }

    body {
        margin: 0;
        font-family: Arial, sans-serif;
        background: #f3f5f9;
        color: #222;
    }

    .container {
        max-width: 700px;
        margin: auto;
        padding: 25px 15px;
    }

    .card {
        background: white;
        border-radius: 18px;
        padding: 30px;
        box-shadow: 0 5px 20px rgba(0,0,0,0.08);
    }

    h1 {
        margin-top: 0;
    }

    .subtitle {
        color: #666;
    }

    .progress {
        height: 8px;
        background: #ddd;
        border-radius: 20px;
        margin: 20px 0;
        overflow: hidden;
    }

    .progress-bar {
        height: 100%;
        width: 0%;
        background: #3157d5;
        transition: 0.3s;
    }

    .question {
        font-size: 21px;
        font-weight: bold;
        margin: 25px 0;
    }

    .option {
        width: 100%;
        padding: 15px;
        margin: 10px 0;
        background: white;
        border: 2px solid #ddd;
        border-radius: 12px;
        text-align: left;
        cursor: pointer;
        font-size: 16px;
        transition: 0.2s;
    }

    .option:hover {
        border-color: #3157d5;
        background: #f4f6ff;
    }

    .option.selected {
        border-color: #3157d5;
        background: #e9edff;
    }

    button.main-btn {
        border: none;
        background: #3157d5;
        color: white;
        padding: 13px 22px;
        border-radius: 10px;
        font-size: 16px;
        cursor: pointer;
    }

    .navigation {
        display: flex;
        justify-content: space-between;
        margin-top: 25px;
        gap: 10px;
    }

    .navigation button {
        padding: 12px 20px;
        border-radius: 10px;
        border: 1px solid #ccc;
        background: white;
        cursor: pointer;
    }

    .score {
        font-size: 45px;
        font-weight: bold;
        text-align: center;
        margin: 20px 0;
    }

    .review {
        margin-top: 20px;
    }

    .review-item {
        padding: 15px;
        border: 1px solid #ddd;
        border-radius: 10px;
        margin: 10px 0;
    }

    .correct {
        color: green;
    }

    .wrong {
        color: #c62828;
    }

    @media (max-width: 500px) {
        .card {
            padding: 20px;
        }

        .question {
            font-size: 18px;
        }
    }
</style>
</head>

<body>

<div class="container">

<div class="card">

<!-- INTRO -->
<div id="intro">

<p><strong>MATH 207 • MODERN GEOMETRY</strong></p>

<h1>History of the Parallel Postulate</h1>

<p class="subtitle">
Test your knowledge about the seven historical figures
and their contributions to the study of the Parallel Postulate.
</p>

<button class="main-btn" onclick="startQuiz()">
Start the Challenge
</button>

</div>


<!-- QUIZ -->
<div id="quiz" style="display:none;">

<div style="display:flex; justify-content:space-between;">
<span id="questionNumber"></span>
<span id="answered"></span>
</div>

<div class="progress">
<div id="progressBar" class="progress-bar"></div>
</div>

<div id="question" class="question"></div>

<div id="options"></div>

<div class="navigation">

<button onclick="previousQuestion()">
Previous
</button>

<button onclick="nextQuestion()">
Next
</button>

</div>

</div>


<!-- RESULT -->
<div id="result" style="display:none;">

<h1>Challenge Complete!</h1>

<div id="finalScore" class="score"></div>

<p id="message" style="text-align:center;"></p>

<div id="review" class="review"></div>

<div style="text-align:center; margin-top:25px;">

<button class="main-btn" onclick="restartQuiz()">
Try Again
</button>

</div>

</div>

</div>

</div>


<script>

const questions = [

{
question:
"Who was an early commentator on Euclid who examined and discussed the foundations of the Parallel Postulate?",

options:
[
"Proclus",
"Wallis",
"Legendre",
"Farkas Bolyai"
],

answer: 0
},

{
question:
"What was John Wallis interested in regarding the Parallel Postulate?",

options:
[
"The relationship between geometry and assumptions about parallels",
"The invention of coordinate geometry",
"The measurement of Earth",
"The construction of regular polygons"
],

answer: 0
},

{
question:
"What was Girolamo Saccheri's major approach to the Parallel Postulate?",

options:
[
"He tried to prove it by examining alternative hypotheses",
"He rejected all of Euclid's postulates",
"He used calculus to measure parallel lines",
"He studied only circles"
],

answer: 0
},

{
question:
"Which three hypotheses did Saccheri investigate for the angles of his quadrilateral?",

options:
[
"Right, acute, and obtuse",
"Equal, unequal, and zero",
"Positive, negative, and zero",
"Parallel, perpendicular, and intersecting"
],

answer: 0
},

{
question:
"What geometric idea did Legendre connect closely with the Parallel Postulate?",

options:
[
"The sum of the angles of a triangle",
"The circumference of a circle",
"The area of a square",
"The number of sides of a polygon"
],

answer: 0
},

{
question:
"What did Lambert and Taurinus investigate that helped develop thinking about alternative geometries?",

options:
[
"Geometries based on different assumptions about parallel lines",
"Only the properties of circles",
"The use of algebra in arithmetic",
"The history of Greek mathematics"
],

answer: 0
},

{
question:
"Farkas Bolyai is historically connected to the development of non-Euclidean geometry partly because he was the father of whom?",

options:
[
"János Bolyai",
"Euclid",
"John Wallis",
"Adrien-Marie Legendre"
],

answer: 0
},

{
question:
"Why did mathematicians spend centuries investigating the Parallel Postulate?",

options:
[
"They questioned whether it could be proven from the other assumptions of Euclidean geometry",
"They thought geometry had no practical use",
"They wanted to remove all axioms from mathematics",
"They wanted to replace mathematics with physics"
],

answer: 0
},

{
question:
"What important idea emerged from attempts to challenge or replace the Parallel Postulate?",

options:
[
"Different consistent assumptions can lead to different geometries",
"All geometries must have exactly the same rules",
"The Parallel Postulate has no connection to geometry",
"Euclidean geometry was completely incorrect"
],

answer: 0
},

{
question:
"Which statement is equivalent to the Parallel Postulate in Euclidean geometry?",

options:
[
"The angles of every triangle add up to 180°",
"Every triangle has four sides",
"Two intersecting lines never meet",
"Every quadrilateral is a rectangle"
],

answer: 0
}

];


let currentQuestion = 0;

let userAnswers = new Array(questions.length).fill(null);


function startQuiz() {

document.getElementById("intro").style.display = "none";

document.getElementById("quiz").style.display = "block";

showQuestion();

}


function showQuestion() {

const q = questions[currentQuestion];

document.getElementById("questionNumber").textContent =
"Question " + (currentQuestion + 1) +
" of " + questions.length;

document.getElementById("answered").textContent =
"Answered: " +
userAnswers.filter(x => x !== null).length +
"/" + questions.length;

document.getElementById("progressBar").style.width =
((currentQuestion + 1) / questions.length * 100) + "%";

document.getElementById("question").textContent =
q.question;


const optionsContainer =
document.getElementById("options");

optionsContainer.innerHTML = "";


q.options.forEach((option, index) => {

const button = document.createElement("button");

button.className = "option";

button.textContent =
String.fromCharCode(65 + index) +
". " +
option;


if (userAnswers[currentQuestion] === index) {

button.classList.add("selected");

}


button.onclick = function() {

userAnswers[currentQuestion] = index;

showQuestion();

};


optionsContainer.appendChild(button);

});

}


function nextQuestion() {

if (userAnswers[currentQuestion] === null) {

alert("Please choose an answer first.");

return;

}


if (currentQuestion < questions.length - 1) {

currentQuestion++;

showQuestion();

}

else {

submitQuiz();

}

}


function previousQuestion() {

if (currentQuestion > 0) {

currentQuestion--;

showQuestion();

}

}


function submitQuiz() {

let score = 0;


questions.forEach((question, index) => {

if (userAnswers[index] === question.answer) {

score++;

}

});


let percentage =
Math.round((score / questions.length) * 100);


document.getElementById("quiz").style.display = "none";

document.getElementById("result").style.display = "block";


document.getElementById("finalScore").textContent =
score + " / " + questions.length +
" (" + percentage + "%)";


let message;


if (percentage === 100) {

message =
"Excellent! You mastered the History of the Parallel Postulate.";

}

else if (percentage >= 80) {

message =
"Great work! You have a strong understanding of the topic.";

}

else if (percentage >= 60) {

message =
"Good effort! Review the historical contributions once more.";

}

else {

message =
"Keep studying! Review the seven mathematicians and try again.";

}


document.getElementById("message").textContent =
message;


showReview();

}


function showReview() {

const review =
document.getElementById("review");

review.innerHTML = "<h2>Answer Review</h2>";


questions.forEach((question, index) => {

const item =
document.createElement("div");

item.className = "review-item";


const isCorrect =
userAnswers[index] === question.answer;


item.innerHTML =

"<strong>Question " +
(index + 1) +
"</strong><br>" +

(isCorrect
? "<span class='correct'>✓ Correct</span>"
: "<span class='wrong'>✗ Review</span>") +

"<br>" +

"Correct answer: " +

String.fromCharCode(65 + question.answer) +

". " +

question.options[question.answer];


review.appendChild(item);

});

}


function restartQuiz() {

currentQuestion = 0;

userAnswers =
new Array(questions.length).fill(null);


document.getElementById("result").style.display =
"none";

document.getElementById("intro").style.display =
"block";

}

</script>

</body>
</html>
