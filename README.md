# TriviaGame
Trivia game assignment using jQuery and setIntervals. We use radio buttons, store those values and display the number
of correct/incorrect/unanswered on the HTML page. We pass the values when we submit or time runs out to the final DoneTrivia 
HTML page to display the values of the quiz.

## Table of contents
Technologies Used
Applications Used
Screenshots of homework progress
Code Snippets

## Technologies Used
HTML
Javascript/jQuery
Markdown

## Applications Used
GitHub
ChromeDev tools
Visual Studio Code
Chrome browser

## Screenshots of homework progress

![Code progression Final](https://github.com/krishnaaddala/TriviaGame/blob/master/assets/images/triviaGameStart.png "Trivia Game Start")

![Code progression Final](https://github.com/krishnaaddala/TriviaGame/blob/master/assets/images/triviaQuiz.png "Trivia Quiz section")

![Code progression Final](https://github.com/krishnaaddala/TriviaGame/blob/master/assets/images/finalDoneImage.png "Final Done Trivia Page")

## Gif walkthrough

![](https://github.com/krishnaaddala/TriviaGame/blob/master/assets/images/triviaGame.gif)

## Code Snippets

```var triviaQuestions = [{
    question: "Superman makes his first appearance in 'Action Comics' #1, Vol. 1. What is the cover date (month and year)?",
    answerArr: ["1937", "1939", "1938", "1940"],
    correctChoice: "1938"
}
  ```

  ```function decrement() {
        if(interval >=0 ) {
            $("#timeRemaining").html("<h2>"+"Time Remaining: " + interval + "</h2>");
        }
        else {
            clearInterval(interval);
            console.log(clearInterval)
            checkAnswers();

        }
        interval--;
    }
  ```

  ```$function checkAnswers(){
    for(var i = 0 ; i < triviaQuestions.length ; i++) {
//storing radio buttons value in jQuery
        var elem = "input[name=answer" + (i+1) +"]:checked";
        increment($(elem).val(), triviaQuestions[i].correctChoice);
    }
    //this queryString passes the answered vs incorrect vs unanswered values from above to the DoneTrivia HTML file
    var queryString = "?ans=" +correctAnswers +"&unans="+unAnswered+"&inAns="+incorrectAnswers;
    window.location.href = "DoneTrivia.html" + queryString;
}
  ```
  ```function gameCompleted(){
var queryString = decodeURIComponent(window.location.search);
    queryString = queryString.substring(1);
    var queries = queryString.split("&");
    $("#correctAnswer").html("Correct Answers : " + queries[0].split('=')[1]);
    $('#incorrectAnswer').html("Incorrect Answers : " + queries[2].split('=')[1]);
    $('#unAnswered').html("Unanswered : " + queries[1].split('=')[1]);
}
  ```
Git commands:

```git status
    git add .
    git commit -m "message"
    git push origin master
    ```