<!DOCTYPE html>
<html>
  <head>
    <title>Lirik Lagu</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        background-color: #86a6c8;
        margin: 0;
        padding: 20px;
      }
      .lyrics-container {
        background-color: #081f2a;
        padding: 20px;
        border-radius: 5px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      }
      h1 {
        text-align: center;
        color: #fffefe;
      }
      p {
        font-size: 16px;
        line-height: 1.5;
        color: #fffefe;
      }
    </style>
  </head>
  <body>
    <div class="lyrics-container">
      <h1>🙌🙌🙌🙌🙌🙌</h1>
      <p id="lyrics"></p>
    </div>

    <script>
      const lyrics = `She's been my queen\nSince we were sixteen\nWe want the same things\nWe dream the same dreams\nAlright\bAlright`;

      const displayLyrics = (
        text,
        elementId,
        charDelay = 50,
        lineDelay = 50,
        specialDelay = 3200
      ) => {
        const element = document.getElementById(elementId);
        let index = 0;

        const displayNextChar = () => {
          if (index < text.length) {
            if (text[index] === "\n") {
              element.innerHTML += "<br>";
              setTimeout(displayNextChar, lineDelay); // Jeda antar baris
            } else if (text[index] === "\b") {
              element.innerHTML += "<br>";
              setTimeout(displayNextChar, specialDelay); // Jeda khusus
            } else {
              element.innerHTML += text[index];
              setTimeout(displayNextChar, charDelay); // Jeda antar karakter
            }
            index++;
          }
        };

        displayNextChar();
      };

      window.onload = () => {
        displayLyrics(lyrics, "lyrics");
      };
    </script>
  </body>
</html>
