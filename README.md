# RICK-E — Robot Interactif de Quiz et de Distribution

## Présentation du projet

RICK-E est un robot interactif inspiré de l’univers de *Rick et Morty*.

Son objectif est de rendre un quiz plus amusant et plus interactif. 
Le robot pose des questions à l’utilisateur grâce à un programme Python. 
L’utilisateur répond à l’oral et le programme analyse sa réponse.

Si la réponse est correcte, le robot commande un servo-moteur qui permet de distribuer une sucette.

Le robot utilise également un écran OLED pour afficher des visages et montrer son état.

---

## Objectifs

Les objectifs du projet sont :

- créer un robot interactif ;
- utiliser la reconnaissance vocale ;
- poser des questions à l’utilisateur ;
- vérifier les réponses ;
- communiquer entre un ordinateur et un ESP32 ;
- afficher des expressions sur un écran OLED ;
- commander un servo-moteur ;
- distribuer une sucette en cas de bonne réponse ;
- mélanger programmation, électronique et fabrication numérique.

---

## Fonctionnement général

Le fonctionnement du robot est le suivant :

1. Le programme Python démarre.
2. RICK-E pose une question à l’utilisateur.
3. L’utilisateur répond avec sa voix.
4. Le microphone enregistre la réponse.
5. La réponse est convertie en texte.
6. Python vérifie si la réponse est correcte.
7. Si la réponse est correcte :
   - le robot annonce la réussite ;
   - Python envoie la commande `DISPENSE` à l’ESP32 ;
   - l’ESP32 fait tourner le servo-moteur ;
   - le robot distribue une sucette ;
   - le servo revient à sa position initiale.
8. Si la réponse est incorrecte, le robot indique que la réponse n’est pas correcte.
9. Le quiz continue jusqu’à la fin des questions ou jusqu’à la limite prévue.

---

## Architecture du projet

Le projet est composé de deux parties principales.

### 1. Le programme Python

Python joue le rôle de cerveau du robot.

Il permet de :

- poser les questions ;
- parler avec une voix synthétique ;
- enregistrer la réponse de l’utilisateur ;
- utiliser la reconnaissance vocale ;
- vérifier la réponse ;
- envoyer des commandes à l’ESP32 par USB-C ;
- gérer le déroulement du quiz.

### 2. Le programme ESP32

L’ESP32 contrôle la partie électronique du robot.

Il permet de :

- recevoir les commandes envoyées par Python ;
- contrôler l’écran OLED ;
- afficher les expressions du robot ;
- contrôler le servo-moteur ;
- gérer la distribution de la sucette ;

---

## Communication entre Python et l’ESP32

La communication se fait par un câble USB en liaison série.

### Paramètres utilisés

- Port série : `COM3`
- Vitesse : `115200 bauds`

### Commandes principales

| Commande | Fonction |
|---|---|
| `DISPENSE` | Lance la distribution d’une sucette |
| `PARLE_DEBUT` | Affiche l’état de parole du robot |
| `PARLE_FIN` | Termine l’état de parole du robot |
