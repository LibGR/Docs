# Exemple complet des extensions Markdown

------------------------------------------------------------------------

## 1. Tables

  Nom         Âge Ville
  --------- ----- -----------
  Alice        25 Paris
  Bob          30 Lyon
  Charlie      35 Marseille

------------------------------------------------------------------------

## 2. Listes avec définitions

Python
:   Langage de programmation polyvalent.

Markdown
:   Langage de balisage léger.

------------------------------------------------------------------------

## 3. Notes de bas de page

Voici une phrase avec une note[^1].

------------------------------------------------------------------------

## 4. Admonitions

!!! info "Astuce" Ceci est une admonition avec du contenu important.

??? tip "Cliquer pour voir plus" Ceci est une admonition dépliable avec
`pymdownx.details`.

------------------------------------------------------------------------

## 5. Emphase intelligente

*italique*, **gras**, et même ***gras+italique***.\
*pymdownx.betterem* rend ça plus fiable.

------------------------------------------------------------------------

## 6. Code et coloration

``` python
def bonjour(nom):
    print(f"Bonjour {nom}")
```

``` yaml
# Exemple YAML avec coloration
site_name: "Mon site"
theme: material
```

### Inline code highlight

Ceci est du code en ligne `print("Hello")`.

------------------------------------------------------------------------

## 7. Superfences avec Mermaid

``` mermaid
graph TD
  A[Début] --> B{Choix ?}
  B -->|Oui| C[Continuer]
  B -->|Non| D[Arrêt]
```

------------------------------------------------------------------------

## 8. Snippets

--8\<-- "includes/mon_snippet.md"

*(affiche le contenu du fichier `includes/mon_snippet.md`)*

------------------------------------------------------------------------

## 9. Onglets

=== "Python" `python     print("Bonjour")` === "JavaScript"
`javascript     console.log("Bonjour")`

------------------------------------------------------------------------

## 10. Mathématiques

Formule inline : $E = mc^2$\
Formule bloc :

$$
\int_0^\infty e^{-x} dx = 1
$$

------------------------------------------------------------------------

## 11. Table des matières

\[\[toc\]\]

[^1]: Ceci est une note de bas de page.
