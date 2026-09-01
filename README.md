<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<title>Valentine</title>

<style>
    body {
        margin: 0;
        background: #f9e3e3;
        font-family: Georgia, serif;
        text-align: center;
    }

    .container {
        margin-top: 180px;
    }

    .picture {
        font-size: 80px;
        margin-bottom: 50px;
    }

    h1 {
        color: #d92d2d;
        font-family: monospace;
        font-size: 32px;
        margin-bottom: 35px;
    }

    button {
        border: none;
        border-radius: 40px;
        padding: 18px 40px;
        font-size: 22px;
        font-weight: bold;
        cursor: pointer;
        transition: 0.3s;
    }

    #yes {
        background: #f3b3c5;
        color: #9b3150;
    }

    #no {
        background: #fffafa;
        color: #806b68;
        margin-left: 10px;
    }

    #message {
        margin-top: 30px;
        color: #d92d2d;
        font-size: 24px;
        font-weight: bold;
    }
</style>
</head>

<body>

<div class="container">

    <div class="picture">
        🐻‍❄️💕
    </div>

    <h1 id="question">
        Dear, Will you be my Valentine?
    </h1>

    <button id="yes">Yes 💕</button>
    <button id="no">No</button>

    <div id="message"></div>

</div>

<script>

let noCount = 0;

const noButton = document.getElementById("no");
const yesButton = document.getElementById("yes");
const question = document.getElementById("question");
const message = document.getElementById("message");

noButton.addEventListener("click", function() {

    noCount++;

    if (noCount === 1) {
        question.innerText = "진짜?";
        message.innerText = "한 번만 다시 생각해봐 🥺";
    }

    else if (noCount === 2) {
        question.innerText = "정말로 No야?";
        message.innerText = "다시 선택해!";
    }

    else if (noCount === 3) {
        question.innerText = "마지막 기회!";
        message.innerText = "Yes를 눌러봐 💗";
    }

    else {
        question.innerText = "다시 선택해!";

        // No 버튼 작아지기
        noButton.style.transform = "scale(0.3)";

        // Yes 버튼 커지기
        yesButton.style.transform = "scale(1.3)";
    }
});


yesButton.addEventListener("click", function() {

    question.innerText = "YAY!! 💕";
    message.innerText = "나도 정말 좋아! 🥰";

    noButton.style.display = "none";
    yesButton.innerText = "💕💕💕";

});

</script>

</body>
</html>
