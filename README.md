# CPP-Module-03

![C++](https://img.shields.io/badge/C++-98-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Top language](https://img.shields.io/github/languages/top/NicolasBaudoin/CPP-Module-03?style=flat-square)
![Last commit](https://img.shields.io/github/last-commit/NicolasBaudoin/CPP-Module-03?style=flat-square)

> Inheritance.

Quatrième module du parcours C++ à 42. Une hiérarchie de robots (`ClapTrap`) pour explorer l'héritage simple et multiple. Tout le code suit la norme **C++98**, classes en **Orthodox Canonical Form**.

---

- [Règles générales](#règles-générales)
- [Exercice 00 — Aaaaand... OPEN!](#exercice-00--aaaaand-open)
- [Exercice 01 — Serena, my love!](#exercice-01--serena-my-love)
- [Exercice 02 — Repetitive work](#exercice-02--repetitive-work)
- [Exercice 03 — Now it's weird!](#exercice-03--now-its-weird)
- [Rendu et évaluation](#rendu-et-évaluation)

## Règles générales

- Compiler avec `c++` et les flags `-Wall -Wextra -Werror`, compatible `-std=c++98`
- Dossiers d'exercices : `ex00`, `ex01`, ..., `exn`
- Classes en **Orthodox Canonical Form** (sauf mention contraire)
- STL interdite avant les Modules 08/09 ; `using namespace` et `friend` interdits

---

## Exercice 00 — Aaaaand... OPEN!

| | |
|---|---|
| **Dossier** | `ex00/` |
| **Fichiers à rendre** | `Makefile`, `main.cpp`, `ClapTrap.{h, hpp}`, `ClapTrap.cpp` |
| **Interdit** | Aucun |

Classe `ClapTrap` avec attributs privés :

- `name` (constructeur), `hitPoints` (10), `energyPoints` (10), `attackDamage` (0)

Méthodes publiques :

- `void attack(const std::string& target);` — le `target` perd `<attackDamage>` PV
- `void takeDamage(unsigned int amount);`
- `void beRepaired(unsigned int amount);`

Attaquer/réparer coûte **1 point d'énergie**. Rien ne se passe si PV ou énergie sont à 0. Chaque méthode (et les constructeurs/destructeur) doit afficher un message explicite. Fournir ses propres tests.

---

## Exercice 01 — Serena, my love!

| | |
|---|---|
| **Dossier** | `ex01/` |
| **Fichiers à rendre** | Fichiers précédents + `ScavTrap.{h, hpp}`, `ScavTrap.cpp` |
| **Interdit** | Aucun |

`ScavTrap` **hérite** de `ClapTrap`. Construction/destruction doivent être **chaînées** et visibles dans les tests (ClapTrap construit en premier, détruit en dernier — pourquoi ?).

Attributs (mis à jour dans `ClapTrap` si besoin) :

- `hitPoints` (100), `energyPoints` (50), `attackDamage` (20)

Capacité propre : `void guardGate();` (affiche le passage en mode gardien).

---

## Exercice 02 — Repetitive work

| | |
|---|---|
| **Dossier** | `ex02/` |
| **Fichiers à rendre** | Fichiers précédents + `FragTrap.{h, hpp}`, `FragTrap.cpp` |
| **Interdit** | Aucun |

`FragTrap` hérite de `ClapTrap`, même principe que `ScavTrap` (messages différents, chaînage construction/destruction) :

- `hitPoints` (100), `energyPoints` (100), `attackDamage` (30)

Capacité propre : `void highFivesGuys(void);`.

---

## Exercice 03 — Now it's weird!

| | |
|---|---|
| **Dossier** | `ex03/` |
| **Fichiers à rendre** | Fichiers précédents + `DiamondTrap.{h, hpp}`, `DiamondTrap.cpp` |
| **Interdit** | Aucun |
| **Optionnel** | Le module passe sans cet exercice |

`DiamondTrap` hérite de **`FragTrap` ET `ScavTrap`** (héritage en diamant) :

- Attribut privé `name` (même nom exact que dans `ClapTrap`)
- `ClapTrap::name` initialisé avec `<nom passé au constructeur> + "_clap_name"`
- PV de `FragTrap`, énergie de `ScavTrap`, dégâts de `FragTrap`, `attack()` de `ScavTrap`
- L'instance `ClapTrap` ne doit être construite **qu'une seule fois** (héritage virtuel)

Capacité propre : `void whoAmI();` (affiche son nom et son nom ClapTrap).

> Se renseigner sur `-Wshadow` / `-Wno-shadow`.

---

## Rendu et évaluation

- Rendu sur le dépôt Git ; seul le contenu du repo est évalué
- Une petite modification peut être demandée en soutenance pour vérifier la compréhension réelle du code
