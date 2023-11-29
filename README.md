# mental_health
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Online Mental Health Checkup</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background-image: url('mental_health_background_image.jpg'); /* Replace with your background image URL */
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
    }
    .container {
      width: 80%;
      margin: 50px auto;
      padding: 20px;
      background-color: rgba(255, 255, 255, 0.8);
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    }
    h1, h3 {
      text-align: center;
    }
    form {
      max-width: 600px;
      margin: 0 auto;
    }
    .question {
      margin-bottom: 20px;
    }
    label {
      display: block;
      margin-bottom: 5px;
      font-weight: bold;
    }
    input[type="radio"] {
      margin-right: 5px;
    }
    input[type="submit"] {
      padding: 10px 20px;
      background-color: #007bff;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Online Mental Health Checkup</h1>
    <form id="mentalHealthForm">
      <div class="question">
        <label for="q1">How often do you feel overwhelmed or stressed?</label>
        <input type="radio" name="q1" value="1"> Rarely<br>
        <input type="radio" name="q1" value="2"> Sometimes<br>
        <input type="radio" name="q1" value="3"> Often<br>
      </div>
      <div class="question">
        <label for="q2">Do you experience difficulties in sleeping or insomnia?</label>
        <input type="radio" name="q2" value="1"> No<br>
        <input type="radio" name="q2" value="2"> Occasionally<br>
        <input type="radio" name="q2" value="3"> Yes<br>
      </div>
      <!-- Add more questions -->
      <div class="question">
        <label for="q3">How often do you feel anxious or worried?</label>
        <input type="radio" name="q3" value="1"> Rarely<br>
        <input type="radio" name="q3" value="2"> Sometimes<br>
        <input type="radio" name="q3" value="3"> Often<br>
      </div>
      <!-- Add more questions -->
      <div class="question">
        <label for="q4">Do you have sudden mood swings or emotional outbursts?</label>
        <input type="radio" name="q4" value="1"> No<br>
        <input type="radio" name="q4" value="2"> Occasionally<br>
        <input type="radio" name="q4" value="3"> Yes<br>
      </div>
      <!-- Add more questions -->
      <div class="question">
        <label for="q5">How often do you feel fatigued or lacking in energy?</label>
        <input type="radio" name="q5" value="1"> Rarely<br>
        <input type="radio" name="q5" value="2"> Sometimes<br>
        <input type="radio" name="q5" value="3"> Often<br>
      </div>
      <!-- Add more questions -->
      <div class="question">
        <label for="q6">Do you have trouble concentrating or making decisions?</label>
        <input type="radio" name="q6" value="1"> No<br>
        <input type="radio" name="q6" value="2"> Occasionally<br>
        <input type="radio" name="q6" value="3"> Yes<br>
      </div>
      <!-- Add more questions -->
      <div class="question">
        <label for="q7">Have you experienced any major life changes or stressors recently?</label>
        <input type="radio" name="q7" value="1"> No<br>
        <input type="radio" name="q7" value="2"> Somewhat<br>
        <input type="radio" name="q7" value="3"> Yes<br>
      </div>
      <!-- Add more questions -->
      <div class="question">
        <label for="q8">Do you feel socially isolated or disconnected?</label>
        <input type="radio" name="q8" value="1"> No<br>
        <input type="radio" name="q8" value="2"> Sometimes<br>
        <input type="radio" name="q8" value="3"> Often<br>
      </div>
      <!-- Add more questions -->
      <div class="question">
        <label for="q9">How often do you experience intrusive or negative thoughts?</label>
        <input type="radio" name="q9" value="1"> Rarely<br>
        <input type="radio" name="q9" value="2"> Sometimes<br>
        <input type="radio" name="q9" value="3"> Often<br>
      </div>
      <!-- Add more questions -->
      <div class="question">
        <label for="q10">Do you engage in activities that you used to enjoy?</label>
        <input type="radio" name="q10" value="1"> Yes, regularly<br>
        <input type="radio" name="q10" value="2"> Occasionally<br>
        <input type="radio" name="q10" value="3"> Rarely<br>
      </div>
      <!-- Add more questions -->
      <input type="submit" value="Submit">
    </form>
    <div id="result" style="display: none;">
      <h3>Your Mental Health Score:</h3>
      <p id="score"></p>
      <h3>Suggestions:</h3>
      <p id="suggestions"></p>
    </div>
  </div>

  <script>
    document.getElementById('mentalHealthForm').addEventListener('submit', function(event) {
      event.preventDefault();
      
      // Calculate the total score based on selected radio button values
      let totalScore = 0;
      const form = document.getElementById('mentalHealthForm');
      const formData = new FormData(form);
      for (const entry of formData.entries()) {
        totalScore += parseInt(entry[1]);
      }
      
      // Display the result and suggestions based on the score
      const resultDiv = document.getElementById('result');
      const scoreDiv = document.getElementById('score');
      const suggestionsDiv = document.getElementById('suggestions');
      
      scoreDiv.textContent = `${totalScore} out of 30`; // Adjust the maximum score based on the number of questions
      resultDiv.style.display = 'block';
      
      // Provide suggestions based on the score range
      if (totalScore <= 10) {
        suggestionsDiv.textContent = "You seem to be doing well, but consider taking steps to maintain good mental health.";
      } else if (totalScore <= 20) {
        suggestionsDiv.textContent = "You might be experiencing some stress. Practice self-care and seek support if needed.";
      } else {
        suggestionsDiv.textContent = "You might be facing significant mental health challenges. Seek professional help and support.";
      }
    });
  </script>
</body>
</html>
