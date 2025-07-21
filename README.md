<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>?12aaa@a1</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html, body {
      height: 100%;
      font-family: 'Courier New', Courier, monospace;
      background: black;
    }

    #bg-video {
      position: fixed;
      top: 0;
      left: 0;
      min-width: 100%;
      min-height: 100%;
      object-fit: cover;
      z-index: -2;
      filter: brightness(0.3) contrast(1.2) saturate(1.1);
    }

    #overlay {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: rgba(0, 0, 0, 0.6);
      z-index: -1;
    }

    #ui {
      position: relative;
      z-index: 10;
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      color: #e0e0e0;
      padding: 20px;
      text-align: center;
    }

    h1 {
      margin-bottom: 20px;
      font-size: 2em;
      text-shadow: 0 0 5px #f0f0f0;
    }

    #output {
      background-color: rgba(0, 0, 0, 0.7);
      border: 1px solid #444;
      border-radius: 5px;
      padding: 15px;
      margin-bottom: 20px;
      width: 90%;
      max-width: 600px;
      min-height: 100px;
      white-space: pre-wrap;
    }

    #input-area {
      display: flex;
      width: 90%;
      max-width: 600px;
    }

    #query {
      flex: 1;
      padding: 10px;
      border: none;
      border-radius: 4px 0 0 4px;
      font-size: 16px;
      background: #222;
      color: #fff;
    }

    #ask-btn {
      padding: 10px 15px;
      background: #444;
      color: white;
      border: none;
      cursor: pointer;
      border-radius: 0 4px 4px 0;
      font-weight: bold;
    }

    #ask-btn:hover {
      background: #666;
    }
  </style>
</head>
<body>

  <video id="bg-video" autoplay muted loop playsinline>
    <source src="a.mp4" type="video/mp4" />
    Your browser does not support the video tag.
  </video>
  <div id="overlay"></div>


  <div id="ui">
    <h1>돕는 사람</h1>
    <div id="output">Ask your question...</div>

    <div id="input-area">
      <input type="text" id="query" placeholder="Search..." autofocus />
      <button id="ask-btn">Enter</button>
    </div>
  </div>

  <script>
    const queryInput = document.getElementById("query");
    const askBtn = document.getElementById("ask-btn");
    const output = document.getElementById("output");

    const responses = {
        no: "Suit yourself. you are a hero.",
        giveup: "thank you for the research purpose or test subject.",
        help: "Do you stil believe on humanity? why bother going this far.[giveup/no]",
        mae: "chained tortured",
        furukawas: "[REDACTED]",
        alternative: "Congratulations. We're on the end game now try your best to help them all while you can.",
        end: "Your decision, The ending you will get. ",
        How_to_end: "Changes the fate of someone who already certain incoming.",
        aoi: "Next test subject",
        locations: "Manila - Cebu - Taipe City - edogawa - tokyo - [REDACTED]",
        who: "Don't go too far.",
        testsubject: "18,211",
        spencer: "135.212795",
        yuki: "139.675698",
      asa: "AsA [REDACTED] curiosity killed the cat",
      ghost: "[REDACTED]",
      shadow: "Shadow failed the test.",
      reillie: "Reillie: Incoming failure.",
      charles: "Charles: Incoming failure.",
      miku: "Miku: [DECEASED] — [THREAT] Neutralized after eliminating 31 personnel.",
      moei: "Moei: Impending death detected. Fate remains uncertain..."
    
      
    };

    askBtn.addEventListener("click", () => {
      const input = queryInput.value.trim().toLowerCase();
      queryInput.value = "";
      queryInput.focus();

      if (!input) {
        output.textContent = "The confusion waits for a real answer...";
        return;
      }

      if (responses[input]) {
        output.textContent = responses[input];
        return;
      }

      output.textContent = `Searching the archives for: "${input}"...\n\n[file://???.txt]\nStatus: CLASSIFIED`;
    });

    queryInput.addEventListener("keypress", (e) => {
      if (e.key === "Enter") {
        askBtn.click();
      }
    });
  </script>
</body>
</html>
