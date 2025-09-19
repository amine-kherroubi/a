# Template LaTeX pour Mémoire de Fin d'Études - ESI

Ce template LaTeX est conçu pour la rédaction des mémoires de fin d'études à l'École nationale Supérieure d'Informatique (ESI) d'Alger.

## 📁 Structure du Projet

```
esi-memoir-template/
├── main.tex                 # Fichier principal
├── config/                  # Configuration LaTeX
│   ├── packages.tex         # Packages requis
│   ├── settings.tex         # Paramètres généraux
│   ├── commands.tex         # Commandes personnalisées
│   └── metadata.tex         # Métadonnées du document
├── frontmatter/            # Pages préliminaires
│   ├── titlepage.tex       # Page de garde
│   ├── dedication.tex      # Dédicace
│   ├── acknowledgments.tex # Remerciements
│   ├── abstracts.tex       # Résumés (FR/EN)
│   ├── tableofcontents.tex # Tables des matières
│   └── acronyms.tex        # Liste des acronymes
├── chapters/               # Chapitres du mémoire
│   ├── 00-introduction.tex # Introduction générale
│   ├── 01-presentation.tex # Présentation de l'organisme
│   ├── 02-study.tex        # Étude de l'existant
│   ├── 03-needs.tex        # Analyse des besoins
│   ├── 04-design.tex       # Analyse et conception
│   ├── 05-development.tex  # Développement et réalisation
│   ├── 06-results.tex      # Résultats et évaluation
│   └── 07-conclusion.tex   # Conclusion générale
├── backmatter/             # Matières finales
│   ├── bibliography.tex     # Bibliographie
│   ├── bibliography.bib     # Base de données bibliographiques
│   └── appendices.tex      # Annexes
├── images/                 # Images et figures (à créer)
├── compile.sh              # Script de compilation (Unix/Linux/Mac)
├── Makefile               # Makefile pour compilation
└── README.md              # Ce fichier
```

## 🚀 Installation Rapide

### Prérequis

- Distribution LaTeX complète (TeX Live, MiKTeX, ou MacTeX)
- Éditeur LaTeX (TeXstudio, TeXmaker, Overleaf, VS Code avec extension LaTeX, etc.)

### Étapes d'Installation

1. **Cloner ou télécharger le template**
   ```bash
   git clone [url-du-repo]
   cd esi-memoir-template
   ```

2. **Créer le dossier images** (pour vos figures)
   ```bash
   mkdir images
   ```

3. **Personnaliser les métadonnées** dans `config/metadata.tex` :
   - Titre du mémoire
   - Votre nom
   - Noms des encadrants
   - Membres du jury
   - Dates

## 📝 Compilation

### Méthode 1 : Avec le script bash (Linux/Mac)
```bash
chmod +x compile.sh
./compile.sh        # Compilation complète
./compile.sh quick  # Compilation rapide
./compile.sh clean  # Nettoyer les fichiers temporaires
```

### Méthode 2 : Avec Make
```bash
make          # Compilation complète
make quick    # Compilation rapide
make clean    # Nettoyer
make view     # Ouvrir le PDF
```

### Méthode 3 : Commandes manuelles
```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

### Méthode 4 : Avec un IDE
- **TeXstudio/TeXmaker** : Ouvrir `main.tex` et utiliser "Quick Build"
- **VS Code** : Installer l'extension LaTeX Workshop
- **Overleaf** : Importer le projet complet

## ✏️ Guide d'Utilisation

### 1. Personnalisation Initiale

Modifiez `config/metadata.tex` pour définir :
```latex
\newcommand{\documentTitle}{Votre titre ici}
\newcommand{\documentAuthor}{Votre nom}
\newcommand{\supervisorESI}{Nom de l'encadrant ESI}
\newcommand{\companyName}{Nom de l'entreprise}
```

### 2. Rédaction des Chapitres

Chaque chapitre est un fichier séparé dans le dossier `chapters/`. Modifiez directement ces fichiers pour ajouter votre contenu.

### 3. Ajout de Figures

Placez vos images dans le dossier `images/` et utilisez :
```latex
\begin{figure}[h]
    \centering
    \includegraphics[width=0.8\textwidth]{nom_image.png}
    \caption{Description de la figure}
    \label{fig:label_unique}
\end{figure}
```

### 4. Gestion de la Bibliographie

Ajoutez vos références dans `backmatter/bibliography.bib` :
```bibtex
@book{cle_unique_2024,
    author = {Nom, Prénom},
    title = {Titre du livre},
    publisher = {Éditeur},
    year = {2024}
}
```

Citez dans le texte avec `\cite{cle_unique_2024}`.

### 5. Acronymes

Définissez vos acronymes dans `frontmatter/acronyms.tex` :
```latex
\acro{API}{Application Programming Interface}
```

Utilisez dans le texte : `\ac{API}` (première fois : forme complète, ensuite : abréviation)

## 🎨 Personnalisation Avancée

### Couleurs ESI

Les couleurs officielles sont définies dans `config/settings.tex` :
- `ESIBlue` : Bleu officiel ESI
- `ESIGray` : Gris secondaire

### Commandes Personnalisées

Des commandes utiles sont disponibles dans `config/commands.tex` :
- `\mychapter{Titre}` : Chapitre non numéroté dans la table des matières
- `\figref{label}` : Référence à une figure
- `\tabref{label}` : Référence à un tableau
- `\code{texte}` : Mise en forme de code inline

## 🐛 Résolution des Problèmes Courants

### Erreur "No citation commands found"
Cette erreur BibTeX est normale si vous n'avez pas encore de citations. Le template inclut `\nocite{*}` pour éviter cette erreur.

### Images non trouvées
Assurez-vous que :
1. Le dossier `images/` existe
2. Les images sont dans ce dossier
3. L'extension est correcte dans `\includegraphics`

### Caractères arabes non affichés
Le template utilise UTF-8. Si les caractères arabes ne s'affichent pas correctement, vérifiez l'encodage de votre éditeur.

## 📚 Ressources Utiles

- [Documentation LaTeX](https://www.latex-project.org/help/documentation/)
- [Overleaf LaTeX Tutorial](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes)
- [Guide UML en LaTeX](https://www.overleaf.com/learn/latex/LaTeX_Graphics_using_TikZ)

## 📄 Licence

Ce template est fourni tel quel pour un usage académique à l'ESI.

## 🤝 Contribution

Les suggestions et améliorations sont les bienvenues ! N'hésitez pas à :
- Signaler des bugs
- Proposer des améliorations
- Partager vos retours d'expérience

## 📧 Support

Pour toute question concernant ce template, consultez d'abord cette documentation. Pour des questions spécifiques à LaTeX, les forums comme [TeX StackExchange](https://tex.stackexchange.com/) sont d'excellentes ressources.

---

**Bon courage pour la rédaction de votre mémoire !** 🎓