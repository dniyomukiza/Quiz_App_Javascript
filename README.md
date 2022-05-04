# Quiz_App_Javascript
//Selectors
let questionContainer = document.getElementById('questionContainer');
let optionSection = document.getElementsByTagName('li');
let numberContainer = document.getElementById('Numbering');
let nextButton = document.getElementById('next');
let checkScore =  document.getElementById('checkScore');
let scoreContainer = document.getElementById('scoreContainer');
let counter = 1;
let score = 0;
let questions = [
    firstQuestion = {question:'Which of these is a correct phone number to contact us?',
   options:['513-315-9110','513-325-9110','533-315-9110','593-315-9110'],
   answer: '513-315-9110'
},
secondQuestion = {question:'Which of these is a correct email fo reservations??',
options:['reserve@pmp.com','reservations@ppm.com','reservations@pmp.com','reservation@pmp.com'],
answer: 'reservations@pmp.com'
},
thirdQuestion = {question:'Which of these is our right physical address?',
options:['44 Main St','47 Main St','56 Main St','51 Main St'],
answer: '47 Main St'
},
]
window.addEventListener('load',displayFirstQuestion)
function displayFirstQuestion(){
    questionContainer.innerText = questions[0].question;
    numberContainer.innerText = counter;
    for (let i = 0;i < optionSection.length; i++){
optionSection[i].innerText = questions[0].options[i];
    }
}
//event listener for next button
nextButton.addEventListener('click', nextQuestion);
function nextQuestion(){
    if(counter == 1){
        questionContainer.innerText = questions[1  ].question;
        for (let i = 0;i < optionSection.length; i++){
            optionSection[i].innerText = questions[1 ].options[i];
                }
                counter++;
                numberContainer.innerText = counter;
    }
    else if(counter == 2){
        questionContainer.innerText = questions[2].question;
        for (let i = 0;i < optionSection.length; i++){
            optionSection[i].innerText = questions[2].options[i];
                }
                counter++;
                numberContainer.innerText = counter;
    }
    for(let i = 0; i < optionSection.length;i++){
        optionSection[i].style.backgroundColor = 'lightgray';
    }
}
function changeColor(x){
for(let i = 0; i < optionSection.length;i++){
  optionSection[i].style.backgroundColor = 'lightgray';
  optionSection[x].style.backgroundColor = 'skyblue';
}
}
for(let i = 0; i< optionSection.length; i++){
    optionSection[i].addEventListener('click', addScore);
;
function addScore(){
    if(counter == 1 &&  optionSection[i].innerText == questions[0].answer){
        score += 5;
    }
    else if(counter == 2 &&  optionSection[i].innerText == questions[1].answer){
        score += 5; 
    }
    else if(counter == 3 &&  optionSection[i].innerText == questions[2].answer){
        score += 5; 
    }
}
}
checkScore.addEventListener('click',showScore);
function showScore(){
scoreContainer.innerText = `Score: ${score}`;
}
