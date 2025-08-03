# Crick-umpire
Mcc laws
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>MCC Cricket Laws Assistant</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #f3f8ff;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .container {
      background: white;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 0 20px rgba(0,0,0,0.1);
      width: 100%;
      max-width: 600px;
      text-align: center;
    }

    input[type="text"] {
      width: 80%;
      padding: 12px;
      margin: 15px 0;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 6px;
    }

    button {
      background-color: #006400;
      color: white;
      padding: 10px 20px;
      font-size: 16px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
    }

    button:hover {
      background-color: #00a000;
    }

    #responseBox {
      margin-top: 20px;
      text-align: left;
      background-color: #eff9ff;
      padding: 15px;
      border-radius: 8px;
    }

    #answerArea {
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>MCC Cricket Laws Assistant</h1>

    <input
      type="text"
      id="queryInput"
      placeholder="Ask a question about cricket laws..."
    />
    <button onclick="handleQuery()">Ask</button>

    <div id="responseBox">
      <p><strong>Answer:</strong></p>
      <div id="answerArea">Waiting for your question...</div>
    </div>
  </div>

  <script>
    const mccDatabase = {
      "underarm": "According to Law 21.1, underarm bowling is not permitted unless agreed before the match. If not agreed, it’s a No Ball.",
      "follow on": "Under Law 14, the follow-on can be enforced if the team batting first leads by 200+ runs in a 5-day match.",
      "fit pitch": "Law 7 states that the umpires decide whether the pitch is fit for play.",
      "substitute": "According to Law 24, a substitute may field but cannot bowl, bat or keep wicket.",
      "saliva": "As per 2022 updates to the Laws, polishing the ball using saliva is no longer permitted.",
      "scorer": "Under Law 3, scorers are responsible for recording runs, wickets, and overs, working in coordination with umpires.",
      "boundary": "Law 19 governs boundaries. A boundary is scored when the ball touches or crosses the boundary line on the ground or in the air."
    };

    function handleQuery() {
      const input = document.getElementById("queryInput").value.toLowerCase();
      const answerArea = document.getElementById("answerArea");

      let found = false;

      for (const key in mccDatabase) {
        if (input.includes(key)) {
          answerArea.innerText = mccDatabase[key];
          found = true;
          break;
        }
      }

      if (!found) {
        answerArea.innerText = "Sorry, I couldn't find a law matching your question. Try rephrasing or using keywords like 'underarm', 'follow on', etc.";
      }
    }
  </script>
</body>
</html>
