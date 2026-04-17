# myprojet

Projet universitaire realise dans le cadre du CSMI (Universite de Strasbourg).

## Contexte du cours

Ce depot regroupe les elements d'un travail de groupe autour de deux axes:

- programmation systeme en C;
- presentation academique sur l'Extreme Programming (XP).

Le projet combine du code source executable et un support de presentation LaTeX/Beamer.

## Auteurs

- P. S. Karami
- O. Saba
- A. Dieng
- A. Wade

## Objectif

Ce depot contient:

- un programme de copie de fichiers (`cprep`) avec gestion d'un buffer configurable;
- un programme de demonstration (`wade`) qui affiche les arguments et l'environnement d'execution;
- une presentation Beamer sur l'Extreme Programming (`projet.tex`).

## Livrables

- `cprep.c`: programme C de copie de fichiers vers un repertoire destination, avec conservation des permissions et dates de modification.
- `wade.c`: programme C de demonstration affichant le PID, les arguments et les variables d'environnement.
- `projet.tex`: support de presentation Beamer sur l'Extreme Programming.
- `.github/workflows/msbuild.yml`: integration continue (GitHub Actions) pour verifier la compilation C.

## Structure du depot

- `cprep.c`
- `wade.c`
- `projet.tex`
- `.github/workflows/msbuild.yml`
- `.gitignore`

## Prerequis

- GCC (ou Clang)
- Environnement Unix/Linux (ou WSL)

## Compilation

```bash
mkdir -p build
gcc -std=c11 -Wall -Wextra -pedantic cprep.c -o build/cprep
gcc -std=c11 -Wall -Wextra -pedantic wade.c -o build/wade
```

## Utilisation

### Programme `cprep`

Syntaxe:

```bash
./build/cprep <taille_buffer> <repertoire_destination> <fichier1> [fichier2 ...]
```

Exemple:

```bash
./build/cprep 1024 sauvegarde fichier1.txt fichier2.txt
```

### Programme `wade`

Syntaxe:

```bash
./build/wade [arguments...]
```

Exemple:

```bash
./build/wade hello world
```

## CI

Le workflow GitHub Actions compile automatiquement `cprep.c` et `wade.c` sur chaque `push` et `pull_request` vers la branche `main`.

## Presentation LaTeX

Pour compiler la presentation `projet.tex` (si TeX Live est installe):

```bash
pdflatex projet.tex
```

## Notes

Le projet contient un fichier `.gitignore` adapte aux artefacts de compilation C et aux dossiers d'IDE.
