# Creative Look pour Mac — bêta

Creative Look est un panneau de looks cinéma pour DaVinci Resolve Studio, ici en **version Mac**. En un double-clic,
il pose un look sur ta power grade. Tu règles ensuite l'intensité, l'expo et le contraste sans quitter la page Color.

> **Première bêta Mac.** Le panneau tourne depuis des semaines sur Windows, mais cette version Mac est toute neuve :
> tu fais partie des premiers à l'essayer. Dis-nous ce qui marche et ce qui coince (onglet Issues).

## En bref

- **Il te faut** : un Mac (Apple Silicon ou Intel) avec DaVinci Resolve **Studio**. La version gratuite n'a pas
  les Workflow Integrations.
- **À télécharger** : uniquement `CreativeLook-…-beta-mac.zip`, dans **Releases** (colonne de droite).
- **À ignorer** : « Source code (zip) » et « Source code (tar.gz) ». GitHub les ajoute tout seul sous chaque
  version ; ils ne contiennent que cette page, pas le plugin.
- **À fournir toi-même** : ta power grade. Aucune n'est livrée (voir « Ta power grade » plus bas).
- **Sur Windows ?** Ce n'est pas la bonne page : la bêta Windows est sur
  [creative-look-beta](https://github.com/procreativenadir-png/creative-look-beta).

### Dans l'archive

| Fichier | À faire |
|---|---|
| `Installer Creative Look.command` | **le seul à double-cliquer**, pour installer comme pour mettre à jour |
| dossier `Creative Look` | n'y touche pas : l'installeur le copie au bon endroit |
| `AJOUTER TA POWER GRADE.txt` | où déposer ta power grade et comment le panneau la choisit |
| `LISEZ-MOI.txt` | le mode d'emploi en version courte |
| `Désinstaller Creative Look.command` | seulement pour retirer le panneau |

## Installer ou mettre à jour

1. Dans la colonne de droite de cette page, ouvre **Releases**, puis télécharge le fichier
   `CreativeLook-…-beta-mac.zip` de la dernière version.
2. Ferme DaVinci Resolve.
3. Double-clique sur l'archive pour la décompresser, puis double-clique sur **Installer Creative Look.command**.
   Le Terminal s'ouvre et demande le mot de passe de ta session Mac : rien ne s'affiche pendant que tu le tapes,
   c'est normal. Valide avec Entrée.
4. Ouvre Resolve Studio, puis **Workspace > Workflow Integrations > Creative Look**.

L'installeur copie le panneau dans le dossier des plugins de Resolve
(`/Library/Application Support/Blackmagic Design/DaVinci Resolve/Workflow Integration Plugins/`). Il y ajoute le
module qui relie le panneau à Resolve, pris dans ton installation de Resolve. Pour mettre à jour, refais la même
chose avec la nouvelle archive. Tes favoris, tes recettes et tes power grades sont conservés.

### Si le Mac refuse d'ouvrir l'installeur

Le panneau n'est pas encore signé par Apple, donc le Mac bloque l'installeur au premier double-clic
(« Apple n'a pas pu vérifier… » ou « développeur non identifié »).

- Ouvre **Réglages Système > Confidentialité et sécurité**. Tout en bas, clique sur **Ouvrir quand même**, puis
  relance l'installeur.
- Ou bien ouvre le **Terminal**, tape `bash` suivi d'un espace, glisse l'installeur dans la fenêtre, puis Entrée.

### Si l'installeur ne trouve pas le module de Resolve

Il le cherche dans les exemples pour développeurs que Resolve installe. S'il dit « WorkflowIntegration.node
introuvable », écris-nous dans Issues. En attendant, tu peux poser un fichier `WorkflowIntegration.node` à côté de
l'installeur : il le prendra en priorité.

## Ta power grade

Le panneau applique ta power grade, puis pose le look sur un node précis. Il reconnaît les nodes par leur nom
(clic droit sur un node > Node Label) :

| Nom du node | Ce que le panneau y met |
|---|---|
| `LUT` | le look (obligatoire) |
| `Exp` | l'exposition et l'équilibre automatique |
| `Look` | le contraste (sans ce node, il va dans `Exp`) |
| `WB` | la balance des blancs automatique |
| `Film Look` | l'émulation pellicule (power grade film : CST de sortie en Cineon Film Log) |

Pour l'utiliser :

1. Exporte ta power grade depuis la Gallery (.drx).
2. Dans le panneau, choisis « … » > **Utiliser ma power grade**.
3. Pour vérifier, choisis « … » > **Diagnostic de la power grade**. Il dit ce que le panneau trouve sur le plan
   courant.

## L'essentiel

- **Survol** d'une vignette : aperçu du look dans Resolve. **Double-clic** : appliquer.
- **Onglets du bas** : Look (intensité, densité, peau, cinémascope), Expo & contraste, Équilibre, Portée.
- **Densité film** et **Peau protégée** : chaque clic passe au niveau suivant (léger, moyen, fort, coupé).
- **A/B** : compare sur le plan le look posé (A) et celui sélectionné dans la grille (B). Appliquer garde le B.
- **Portée > Scènes** : le panneau regroupe les plans par scène, avec une couleur de clip par scène. Ensuite, un
  look appliqué sur un plan va sur toute sa scène.
- **Vue mosaïque** : l'icône en grille 3 × 3, en haut.
- **Mode Film** : seuls les looks essentiels, adaptés à l'émulation pellicule pour garder leur couleur.
- **Recettes** : « … » > Recettes, pour enregistrer tes réglages sous un nom, ou exporter et importer recettes et
  favoris.
- **Sur Mac, le panneau est une fenêtre libre** : place-la où tu veux à côté de Resolve, elle garde sa place.

### Raccourcis

Ils marchent aussi quand Resolve est au premier plan. Ils commencent tous par **Cmd+Option+Maj** :

| Touche | Action |
|---|---|
| 1 à 9 | favoris |
| ← → | look précédent / suivant |
| ↑ ↓ | intensité |
| Page haut / Page bas (fn+↑ / fn+↓ sur un portable) | expo ±0,5 |
| Début / Fin (fn+← / fn+→ sur un portable) | expo ±0,1 |
| A | équilibrer |
| M | raccorder |
| B | avant / après |
| C | comparer A/B |
| Z | annuler |

## Donner un retour

Ouvre l'onglet **Issues**, clique sur **New issue**, puis choisis **Un problème** ou **Une idée**.

Pour un problème, joins le rapport de support :

1. Dans le panneau, choisis « … » > **Préparer un rapport pour le support**.
2. Le Finder s'ouvre sur un fichier texte, sur ton Bureau (ou dans Documents, ou dans le dossier de Creative Look
   si le Mac refuse l'accès au Bureau).
3. Glisse-le dans l'issue.

Le rapport contient les versions de Resolve, de macOS et du panneau, ses réglages, les noms des nodes du plan et la
fin du journal. Il ne contient aucune image. Il contient en revanche des chemins de fichiers, qui peuvent inclure
ton nom d'utilisateur.

Ce qui nous aide le plus pour cette première bêta Mac : l'installation s'est-elle bien passée, le panneau
s'ouvre-t-il, les looks se posent-ils sur le plan, les raccourcis répondent-ils.

## Limites connues

- Pas encore d'aimantation : sur Windows, le panneau se colle au bord de Resolve ; sur Mac, c'est une fenêtre libre.
- Pas encore signé par Apple : d'où le blocage au premier double-clic (voir plus haut).
- Les barres cinémascope recadrent le clip. L'Output Blanking prendra le relais quand Resolve 21.1 le permettra.
- Le détail des versions est dans [CHANGELOG.md](CHANGELOG.md).
