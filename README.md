# TestChatGPT
Environnement pour tester les fonctionnalités de Codex.

## Démo : petite calculatrice JavaScript

1. Ouvrir le fichier `index.html` dans votre navigateur.
2. Cliquer sur les boutons pour saisir une expression.
3. Utiliser `=` pour calculer, et `C` pour remettre à zéro.

Exemples :
- `(7+3)*2`
- `12/4+1.5`

---

## Outil Python : description de dataset confidentiel (CSV/XLSX)

Le script `analyze_dataset.py` génère un fichier JSON décrivant la structure d'un dataset sans inclure les valeurs brutes.

### Ce qui est inclus dans la description
- Nom du fichier et format (`csv` ou `xlsx`)
- Nombre de lignes et de colonnes
- Pour chaque colonne :
  - Nom
  - Type inféré
  - Type sémantique estimé (`texte`, `entier`, `nombre décimal`, `date/heure`, `email`, `URL`, etc.)
  - Indicateur `valeurs_vides_possibles` (oui/non)
  - Champ `description_contenu_colonne` laissé vide pour que l'utilisateur le remplisse manuellement

> Le script n'exporte pas les données brutes du fichier source.

### Installation

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### Utilisation

```bash
python analyze_dataset.py chemin/vers/fichier.csv -o dataset_description.json
```

Options utiles :
- `--encoding` pour l'encodage CSV (défaut `utf-8`)
- `--separator` pour le séparateur CSV (défaut `,`)

### Exemple d'utilisation avec séparateur `;`

```bash
python analyze_dataset.py donnees.csv --separator ';' -o description.json
```
