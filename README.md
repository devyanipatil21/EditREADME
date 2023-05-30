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
