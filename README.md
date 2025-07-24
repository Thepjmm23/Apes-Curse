<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Apes Curse VR</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }
    body {
      line-height: 1.6;
      padding: 20px;
      max-width: 800px;
      margin: 0 auto;
      background-color: #f4f4f4;
    }
    header, section {
      margin-bottom: 2rem;
    }
    h1 {
      font-size: 2.5rem;
      margin-bottom: 0.5rem;
      color: #222;
    }
    h2 {
      font-size: 1.75rem;
      margin-bottom: 0.5rem;
      color: #333;
    }
    p, li {
      font-size: 1rem;
      margin-bottom: 0.75rem;
      color: #444;
    }
    ul {
      list-style: disc inside;
    }
    .button {
      display: inline-block;
      background-color: #28a745;
      color: #fff;
      padding: 0.75rem 1.5rem;
      text-decoration: none;
      border-radius: 4px;
      font-weight: bold;
      cursor: pointer;
      border: none;
    }
    .button:hover {
      background-color: #218838;
    }
    footer {
      text-align: center;
      font-size: 0.9rem;
      color: #666;
      padding-top: 1rem;
      border-top: 1px solid #ddd;
    }
    /* Modal styles */
    #termsModal {
      display: none;
      position: fixed;
      z-index: 9999;
      left: 0; top: 0;
      width: 100%; height: 100%;
      overflow: auto;
      background-color: rgba(0,0,0,0.6);
    }
    #termsContent {
      background-color: #fff;
      margin: 5% auto;
      padding: 20px;
      border-radius: 8px;
      max-width: 700px;
      max-height: 80vh;
      overflow-y: auto;
      box-shadow: 0 2px 10px rgba(0,0,0,0.3);
      white-space: pre-wrap;
    }
    #closeTerms {
      background-color: #cc0000;
      color: white;
      float: right;
      font-size: 1.2rem;
      font-weight: bold;
      border: none;
      padding: 4px 10px;
      border-radius: 4px;
      cursor: pointer;
      margin-bottom: 10px;
    }
    #closeTerms:hover {
      background-color: #990000;
    }
  </style>
</head>
<body>
  <header>
    <h1>Apes Curse VR</h1>
    <p>a game made by thepjmm23 on yt</p>
  </header>

  <section id="about">
    <h2>About the Game</h2>
    <p>
      Apes Curse VR is a gorilla tag fan game! you can get cosmetics and much more!
    </p>
  </section>

  <section id="features">
    <h2>Key Features</h2>
    <ul>
      <li>Shop with cosmetics</li>
      <li>good gameplay</li>
      <li>updates based on player feedback, bug fixes and more!</li>
    </ul>
  </section>

  <section id="download">
    <h2>Get the Game</h2>
    <p>
      Join the discord to install the game!
    </p>
    <ul>
      <li>Discord: <a href="https://discord.gg/aMnNNTZY2w">https://discord.gg/aMnNNTZY2w</a></li>
    </ul>
  </section>

  <section id="contact">
    <h2>Contact & Support</h2>
    <p>Found a bug? Want to help test new levels? Reach out:</p>
    <ul>
      <li>Discord: <a href="https://discord.gg/aMnNNTZY2w">https://discord.gg/aMnNNTZY2w</a></li>
    </ul>
  </section>

  <section id="terms">
    <button id="showTerms" class="button">View Terms of Use</button>
  </section>

  <footer>
    <p>© 2025 Apes Curse VR Fan Game – Created by Thepjmm23</p>
  </footer>

  <!-- Modal for Terms -->
  <div id="termsModal" aria-hidden="true" role="dialog" aria-labelledby="termsTitle" tabindex="-1">
    <div id="termsContent">
      <button id="closeTerms" aria-label="Close Terms of Use">✕ Close</button>
      <h2 id="termsTitle">Terms of Use</h2>
      <pre id="termsText">Loading terms...</pre>
    </div>
  </div>

  <script>
    const showTermsBtn = document.getElementById('showTerms');
    const termsModal = document.getElementById('termsModal');
    const closeTermsBtn = document.getElementById('closeTerms');
    const termsText = document.getElementById('termsText');

    showTermsBtn.addEventListener('click', () => {
      // Show modal
      termsModal.style.display = 'block';
      termsModal.setAttribute('aria-hidden', 'false');

      // Fetch terms from pastebin
      fetch('https://pastebin.com/raw/VKDC1cBT')
        .then(response => {
          if (!response.ok) throw new Error('Network response was not ok');
          return response.text();
        })
        .then(data => {
          termsText.textContent = data;
        })
        .catch(() => {
          termsText.textContent = 'Failed to load terms. Please try again later.';
        });
    });

    closeTermsBtn.addEventListener('click', () => {
      termsModal.style.display = 'none';
      termsModal.setAttribute('aria-hidden', 'true');
      termsText.textContent = 'Loading terms...';
    });

    // Close modal if user clicks outside the content
    window.addEventListener('click', e => {
      if (e.target === termsModal) {
        termsModal.style.display = 'none';
        termsModal.setAttribute('aria-hidden', 'true');
        termsText.textContent = 'Loading terms...';
      }
    });

    // Accessibility: close modal on Escape key
    window.addEventListener('keydown', e => {
      if (e.key === 'Escape' && termsModal.style.display === 'block') {
        termsModal.style.display = 'none';
        termsModal.setAttribute('aria-hidden', 'true');
        termsText.textContent = 'Loading terms...';
      }
    });
  </script>
</body>
</html>
