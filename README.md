# E-Commerce Microservices Application - II BDCC
Ce projet consiste en la mise en place d'une architecture distribuée basée sur les microservices pour une plateforme d'e-commerce. Il a été réalisé dans le cadre du module Architecture Microservices de la filière II-BDCC.

## Architecture du Système
L'application suit une architecture microservices moderne utilisant l'écosystème Spring Cloud et un frontend en Angular.

### 1. Backend (Microservices)
Customer Service : Gère les informations relatives aux clients (CRUD).

Inventory Service : Gère le catalogue des produits et les stocks.

Order Service : Gère le processus de commande (gestion des états, association produits/clients via OpenFeign).

Billing Service : (Optionnel selon les vidéos) Service dédié à la facturation.

### 2. Infrastructure Cloud & Discovery
Spring Cloud Config Server : Centralise la configuration de tous les microservices via un dépôt Git ou local.

Eureka Discovery Service : Permet l'enregistrement et la découverte dynamique des instances de microservices.

Spring Cloud Gateway : Point d'entrée unique de l'application. Gère le routage dynamique et la configuration CORS globale.

### 3. Frontend (Angular Client)
Développement d'une interface Single Page Application (SPA).

Consommation des API REST via le Gateway.

Affichage dynamique des produits, des clients et suivi des commandes.
<img width="1919" height="938" alt="image" src="https://github.com/user-attachments/assets/030ba5af-abc6-4a9a-ac0f-3735cbd85f50" />

## Technologies Utilisées
Backend : Java, Spring Boot, Spring Data JPA, H2 Database (In-Memory).

Cloud : Spring Cloud Gateway, Netflix Eureka, Spring Cloud Config.

Communication Inter-services : OpenFeign (Client REST déclaratif).

Frontend : Angular, TypeScript, Bootstrap pour le design.

Outils : Maven, IntelliJ IDEA, Postman, Git.

## Étapes de Réalisation
Partie 1 & 2 : Fondations et Services
Création des microservices Customer-Service et Inventory-Service.

Configuration de l'accès aux données avec Spring Data JPA et exposition via Spring Data REST.

Mise en place de l'infrastructure Discovery avec Eureka Server.

Partie 3 : Order Service & Communication
Développement du Order-Service pour gérer les commandes complexes.

Utilisation de OpenFeign pour récupérer les données clients et produits à partir d'autres microservices de manière transparente.

Implémentation du Gateway Service pour sécuriser et centraliser les appels API.

Partie 4 : Client Angular
Création d'un projet Angular pour interfacer l'utilisateur avec le backend.

Implémentation de services Angular pour appeler les endpoints du Gateway.

Gestion du routage et affichage des données (Clients, Produits, Détails des commandes).

### Comment lancer le projet
**Cloner le repository :**

```Bash

git clone https://github.com/salmaad/ecom-ii-bdcc-app.git
```
**Lancer l'infrastructure :** Démarrer d'abord Config-Server et Eureka-Server.

**Lancer les microservices :** Démarrer Customer-Service, Inventory-Service et Order-Service.

**Lancer le Gateway :** Démarrer Gateway-Service.

**Lancer le Frontend :**

```Bash

cd angular-client
npm install
ng serve
