# EditREADME


####html
<!DOCTYPE html>
<html>
<head>
  <title>Word Counter</title>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <div class="container">
    <h1>Word Counter</h1>
    <textarea id="input-text" placeholder="Enter your text here"></textarea>
    <button onclick="countWords()">Count Words</button>
    <div id="word-count"></div>
  </div>
  <script src="script.js"></script>
</body>
</html>


########css
.container {
    text-align: center;
    margin-top: 100px;
  }
  
  h1 {
    font-size: 24px;
  }
  
  textarea {
    width: 400px;
    height: 200px;
    margin: 20px auto;
    resize: none;
  }
  
  button {
    padding: 10px 20px;
    font-size: 16px;
  }
  
  #word-count {
    margin-top: 20px;
    font-size: 18px;
    text-align: left;
  }
  
  
  ###########js
  function countWords() {
    var text = document.getElementById('input-text').value;
    var words = text.toLowerCase().match(/\b\w+\b/g);
    var wordCount = {};
  
    for (var i = 0; i < words.length; i++) {
      var word = words[i];
      if (wordCount[word]) {
        wordCount[word]++;
      } else {
        wordCount[word] = 1;
      }
    }
  
    var sortedWords = [];
    for (var word in wordCount) {
      sortedWords.push([word, wordCount[word]]);
    }
  
    sortedWords.sort(function(a, b) {
      return b[1] - a[1];
    });
  
    var wordCountElement = document.getElementById('word-count');
    wordCountElement.innerHTML = '';
  
    for (var i = 0; i < sortedWords.length; i++) {
      var word = sortedWords[i][0];
      var count = sortedWords[i][1];
      var wordElement = document.createElement('p');
      wordElement.innerHTML = word + ': ' + count;
      wordCountElement.appendChild(wordElement);
    }
  }
