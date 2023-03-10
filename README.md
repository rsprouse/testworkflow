## Code snippet

### Style 1: Make into a code block

By placing into a code block we get syntax highlighting on github. And if you need to make any changes to the html it will be a lot easier becasuse you can use straight html instead of representing code elements with html entities.

```html
<script src="assets/js/ex/exercises.js">
    <script src="assets/js/ex/vocal_tract_tour.js">

    <body onload="initialize()">

        <h1>A tour of the vocal tract</h1>
        <p>Fill in the blanks on this figure.</p>
        
        <span class="image fit"><img src="images/ex/ex1_1.png" width="400px"></span>
        
        <p>Fill in the name of number: <span id="question"></span>
          <input id="answerbox" type="text" onkeydown="if (event.keyCode == 13) check_answer()" placeholder="type answer here">
          <span id="feedback"></span></p>
        <p style="font-size:small">Correct: <span id="correct">0</span> ---- Run: <span id="run">0</span></p>
```

### Style 2: Make into a code block and correct

The following was also run through a syntax checker and errors were corrected.

```html
<!DOCTYPE html>
<html lang="en">
<head>
<title>Phonwork: A tour of the vocal tract</title>
<script src="assets/js/ex/exercises.js"></script>
<script src="assets/js/ex/vocal_tract_tour.js"></script>
</head>
<body onload="initialize()">

    <h1>A tour of the vocal tract</h1>
    <p>Fill in the blanks on this figure.</p>
    
    <span class="image fit"><img src="images/ex/ex1_1.png" width="400" alt="Vocal tract with numbered regions"></span>
    
    <p>Fill in the name of number: <span id="question"></span>
      <input id="answerbox" type="text" onkeydown="if (event.keyCode == 13) check_answer()" placeholder="type answer here">
      <span id="feedback"></span></p>

    <p style="font-size:small">Correct: <span id="correct">0</span> ---- Run: <span id="run">0</span></p>
</body>
</html>
```
