# 🧠 Phase 2 — Traitement de l'image (reconnaissance de cartes)



## 🎯 Objectif

Extraire à partir d’une image (ex: capture.png) la position et l’identité des cartes visibles à l’écran pour chaque joueur.

Exemple de sortie :
```markdown
{
  "my_cards": ["as_pique", "10_trefle"],
  "player_1": ["valet_coeur", "roi_trefle"],
  "player_2": ["7_pique", "8_trefle"]
}
```


## 🧰 Technologies recommandées

| Tache  | Outil |
| ------------- |:-------------:|
| Chargement & découpe image	PIL (Pillow)      | OpenCV     |
| Comparaison d’images      | OpenCV (Template Matching)     |
| Alternative + puissante     | YOLOv5/YOLOv8 (détection objets)     |
| Annoter / entraîner	LabelImg	 |  Roboflow


## 🧭 Étapes détaillées du traitement

### **1. Charger l’image de capture**
```markdown
import cv2

image = cv2.imread("capture.png")
```

### **2. Charger les zones de détection**

On suppose que chaque joueur a une zone spécifique sur l’écran :

```markdown
// zones.json
{
  "my_cards": [[100, 600], [600, 700]],
  "player_1": [[100, 100], [600, 200]],
  "player_2": [[100, 300], [600, 400]]
}
```
```markdown
import json

with open("zones.json") as f:
    zones = json.load(f)
```
### **3. Découper chaque zone**

```markdown
def crop_zone(img, coord):
    x1, y1 = coord[0]
    x2, y2 = coord[1]
    return img[y1:y2, x1:x2]
```
### **4. Recherche des cartes par Template Matching**
```markdown
import os

def match_templates(zone_img, templates_dir, seuil=0.8):
    results = []
    for file in os.listdir(templates_dir):
        template = cv2.imread(os.path.join(templates_dir, file))
        res = cv2.matchTemplate(zone_img, template, cv2.TM_CCOEFF_NORMED)
        min_val, max_val, min_loc, max_loc = cv2.minMaxLoc(res)
        if max_val >= seuil:
            results.append({
                "carte": file.replace(".png", ""),
                "position": max_loc,
                "score": max_val
            })
    return results
```

### **5. Appliquer à chaque joueur**
```markdown
def detect_cartes(image_path="capture.png"):
    img = cv2.imread(image_path)
    with open("zones.json") as f:
        zones = json.load(f)

    data = {}
    for zone_name, coords in zones.items():
        cropped = crop_zone(img, coords)
        matches = match_templates(cropped, "templates/")
        data[zone_name] = [m["carte"] for m in matches]
    
    return data
```

## ✅ Résultat final (prêt pour la phase 3)

```markdown
{
  'my_cards': ['10_coeur', 'as_pique'],
  'player_1': ['8_trefle', 'roi_coeur'],
  'player_2': ['7_trefle']
}
```

