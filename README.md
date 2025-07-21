<h1 align="center" id="title">CardiPy</h1>

<p align="center">
  <img src="https://cdn-icons-png.flaticon.com/512/1178/1178933.png" alt="project-image" width="100">
</p>

<p align="center">
  A Python script boosted with cold coffee and Selenium. It clicks, it detects, it recognizes... but we won't tell you what.  
  Let's just say that cards are involved and some form of automation is at work. Use at your own (mostly) risk.  
  _Disclaimer: No pixels were mistreated during testing._
</p>

---

## 🔗 Navigation rapide

- [📁 Structure](#-structure-du-projet)
- [🔁 Automatisation (Selenium)](#-automatisation)
- [🧠 Reconnaissance sur image](#-reconnaissance-sur-image)
- [🧮 Prise de décision algorithmique](#-logique-de-décision)
- [🛠️ Installation](#️-installation)
- [🧪 Lancement](#-lancement-rapide)
- [⚠️ Disclaimer](#️-disclaimer)

---

## 📁 Structure du Projet

Le projet est divisé en trois grandes parties :

- [🔁 Automatisation](https://github.com/sapeurpac/CardiPy/blob/main/automation)
- [🧠 Reconnaissance sur image](#-reconnaissance-sur-image)
- [🧮 Prise de décision algorithmique](#-logique-de-décision)

```plaintext
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
├── README.md
└── .gitignore
```

---

## 🔁 Automatisation

Module utilisant **Selenium** et **undetected-chromedriver** pour interagir avec une interface web de manière automatisée.

Fonctionnalités :
- Navigation automatique (URL, scroll, clics)
- Détection de Cloudflare ou CAPTCHA
- Prise de captures d’écran depuis le DOM

---

## 🧠 Reconnaissance sur image

Traitement des captures d'écran pour extraire des informations visuelles :

- OCR avec `pytesseract`
- Analyse de position via OpenCV
- Matching d’éléments / détection d'icônes

---

## 🧮 Logique de Décision

Interprétation des données extraites pour prendre des décisions programmatiques :

- Conditions simples (if/else, seuils numériques)
- Séquencement logique d’actions
- Logique adaptative ou historique (prévu)

---

## 🛠️ Installation

```bash
git clone https://github.com/ton-user/CardiPy.git
cd CardiPy
pip install -r requirements.txt
```

---

## 🧪 Lancement rapide

```bash
python main.py
```

Pour plus de détails, voir :
[🔁 Automatisation](#-automatisation) | [🧠 Vision](#-reconnaissance-sur-image) | [🧮 Logique](#-logique-de-décision)

---

## ⚠️ Disclaimer

Projet à usage personnel / éducatif uniquement.  
**N'utilisez pas ce script sur des plateformes où l'automatisation est interdite.**
