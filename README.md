<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CardiPy - Project Overview</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f7f7f7;
      color: #333;
      line-height: 1.6;
      max-width: 900px;
      margin: 2rem auto;
      padding: 0 1rem;
    }
    h1, h2, h3 {
      text-align: center;
      color: #2c3e50;
    }
    p, li {
      font-size: 1rem;
    }
    pre {
      background: #eee;
      padding: 1em;
      overflow-x: auto;
    }
    nav {
      text-align: center;
      margin-bottom: 2rem;
    }
    nav a {
      margin: 0 1rem;
      text-decoration: none;
      color: #2980b9;
    }
    .section {
      margin-top: 3rem;
    }
  </style>
</head>
<body>

  <h1 id="title">CardiPy</h1>

  <p align="center">
    <img src="https://cdn-icons-png.flaticon.com/512/1178/1178933.png" alt="project-image" width="100">
  </p>

  <p id="description" align="center">
    A Python script boosted with cold coffee and Selenium. It clicks, it detects, it recognizes... but we won't tell you what.
    Let's just say that cards are involved and some form of automation is at work. Use at your own (mostly) risk.<br><br>
    <i>Disclaimer: No pixels were mistreated during testing.</i>
  </p>

  <nav>
    <a href="#structure">📁 Structure</a>
    <a href="#automation">🔁 Automatisation</a>
    <a href="#vision">🧠 Vision</a>
    <a href="#logic">🧮 Logique</a>
    <a href="#install">🛠️ Installation</a>
    <a href="#launch">🧪 Lancement</a>
  </nav>

  <div class="section" id="structure">
    <h2>📁 Structure du Projet</h2>
    <p>Le projet est divisé en trois grandes parties :</p>
    <ul>
      <li><a href="#automation">🔁 Automatisation (Selenium + UC)</a></li>
      <li><a href="#vision">🧠 Reconnaissance sur image</a></li>
      <li><a href="#logic">🧮 Prise de décision algorithmique</a></li>
    </ul>

    <pre><code>
CardiPy/
├── automation/          → Scripts Selenium
├── vision/              → Traitement d’image (OCR, OpenCV, etc.)
├── logic/               → Moteur de prise de décision
├── docs/                → Documentation technique (liée aux 3 modules)
│   ├── automation.md
│   ├── vision.md
│   └── logic.md
├── main.py              → Script principal orchestrant tout
├── requirements.txt
├── README.md / README.html
└── .gitignore
    </code></pre>
  </div>

  <div class="section" id="automation">
    <h2>🔁 Automatisation</h2>
    <p>Module utilisant <b>Selenium</b> et <b>undetected-chromedriver</b> pour interagir avec une interface web de manière automatisée.</p>
    <ul>
      <li>Navigation automatique (URL, scroll, clics)</li>
      <li>Détection de Cloudflare ou CAPTCHA</li>
      <li>Prise de captures d’écran depuis le DOM</li>
    </ul>
  </div>

  <div class="section" id="vision">
    <h2>🧠 Reconnaissance sur image</h2>
    <p>Traitement des captures d'écran pour extraire des informations visuelles.</p>
    <ul>
      <li>OCR avec <code>pytesseract</code></li>
      <li>Analyse de position via OpenCV</li>
      <li>Filtrage des images et matching d’éléments</li>
    </ul>
  </div>

  <div class="section" id="logic">
    <h2>🧮 Logique de Décision</h2>
    <p>Interprétation des données extraites pour prendre des décisions programmatiques.</p>
    <ul>
      <li>Conditions simples (if/else, seuils numériques)</li>
      <li>Planification d’actions à effectuer en fonction du contexte</li>
      <li>Historique et logique adaptative (à venir)</li>
    </ul>
  </div>

  <div class="section" id="install">
    <h2>🛠️ Installation</h2>
    <pre><code>
git clone https://github.com/ton-user/CardiPy.git
cd CardiPy
pip install -r requirements.txt
    </code></pre>
  </div>

  <div class="section" id="launch">
    <h2>🧪 Lancement rapide</h2>
    <pre><code>
python main.py
    </code></pre>
    <p>
      Pour plus de détails, voir les sections :
      <a href="#automation">Automatisation</a> |
      <a href="#vision">Reconnaissance</a> |
      <a href="#logic">Décision</a>
    </p>
  </div>

  <div class="section" id="disclaimer">
    <h2>⚠️ Disclaimer</h2>
    <p>
      Projet à usage personnel / éducatif uniquement. N'utilisez pas ce script sur des plateformes où l'automatisation est interdite.
    </p>
  </div>

</body>
</html>
