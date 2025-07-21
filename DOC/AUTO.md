# 🧭 Phase 1 — Automatisation avec Selenium (pilotage du site)



## 🧱 1. Initialisation de l’environnement

- **✅ Lancer Chrome avec undetected_chromedriver** ou un profil avec des options réalistes
- **✅ Paramètres anti-détection :**
- - User-Agent réaliste
- - Désactivation des flags de bot comme webdriver
- - Chargement de cookies ou session si nécessaire
- - Délai randomisé entre les actions
```markdown
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
import undetected_chromedriver as uc
import random
import time

def init_driver():
    options = uc.ChromeOptions()
    options.add_argument("--disable-blink-features=AutomationControlled")
    options.add_argument(f'user-agent=Mozilla/5.0 ...')
    driver = uc.Chrome(options=options)
    return driver
```


## 🗺️ 2. Accès au site de jeu

#### Lancer l'URL du site (driver.get("https://www.exemple.com"))
- **Accepter les cookies** / **pop-ups** si nécessaire

- **Vérifier que l’utilisateur est connecté** ou effectuer une connexion automatisée



## 🔍 3. Analyse DOM / Extraction d’éléments

Identifier via XPath, CSS selector ou JS les éléments d’intérêt :

- **Boutons** ("Jouer", "Valider", "Continuer", etc.)

- **Zones de texte**

- **Informations affichées à l’écran**

- **Informations dynamiques** en JS (ex : score, identifiants des cartes)

### ⚙️ Extraction possible :

- via driver.find_element().text

- via driver.execute_script() si nécessaire pour des objets JS

    Exemple JS :

```markdown
info = driver.execute_script("return window.gameData.playerHand;")
```

# 🕹️ 4. Simulation d’actions humaines

- **Cliquer** sur les boutons du jeu

- **Naviguer** dans l’interface

- **Attendre** les bons chargements (ex : WebDriverWait)

- **Délai aléatoire** entre les **actions** pour simuler l’humain :

```markdown
time.sleep(random.uniform(1.2, 2.5))
```

# 📸 5. Attente d’un événement clé

Exemple : attendre que l’interface affiche les cartes ou que le tour commence.

Possible avec :

  - **WebDriverWait** sur un élément visible

  - **Analyse JS** du DOM

 - **Chronomètre fixe si c’est toujours le même temps**


# 🖼️ 6. Prendre une capture de l’écran à un instant précis
```markdown
driver.save_screenshot("capture.png")
```

Possibilité de **crop directement** avec PIL si nécessaire (en local, pas via Selenium).


----
____

****[Init Chrome] → [Charger le site] → [Interagir] → [Attendre état] → [Screenshot]****

----


