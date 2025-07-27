# 📄 Cahier des charges du projet d'informatisation des activités de prêts  
**Client : CashToGo**

---

## 1. Contexte du projet

**CashToGo** est une entreprise informelle spécialisée dans le prêt d’argent à court et moyen terme, basée à Antananarivo. Actuellement, les activités sont gérées manuellement, ce qui entraîne des erreurs, des oublis et des pertes de données.

L’entreprise souhaite développer une **application web locale** permettant de gérer efficacement les clients, les prêts, les remboursements, les utilisateurs et les notifications, tout cela **sans connexion Internet**.

---

## 2. Objectifs du projet

- **Digitaliser** toutes les opérations de prêts
- **Centraliser** les données clients et transactions dans une base PostgreSQL locale
- **Automatiser** les calculs financiers (intérêts, échéances, pénalités)
- **Gérer les utilisateurs** avec rôles différenciés
- **Notifier** les échéances et retards
- **Fonctionner 100 % localement sur un ordinateur personnel (localhost)**

---

## 3. Périmètre fonctionnel

### 3.1. Gestion des utilisateurs & privilèges

#### Fonctionnalités :
- Connexion sécurisée
- Création, modification, suppression de comptes
- Attribution d’un rôle :
  - **Administrateur** : tous les droits
  - **Agent** : accès limité à la gestion
  - **Superviseur** : lecture seule

#### Champs utilisateur :
- Nom complet
- Nom d'utilisateur (unique)
- Mot de passe
- Rôle (menu déroulant)

---

### 3.2. Gestion des clients

#### Fonctionnalités :
- Ajouter, modifier, supprimer un client
- Voir les détails et l’historique de prêts
- Rechercher, trier et filtrer

#### Champs client :
- Nom complet
- Numéro CIN
- Date de naissance
- Adresse
- Téléphone
- Email (facultatif)
- Profession
- Nom d’un garant (facultatif)
- Photo (optionnelle)

---

### 3.3. Gestion des prêts

#### Fonctionnalités :
- Création d’un prêt avec :
  - Calcul automatique des intérêts
  - Génération d’un échéancier
  - Pénalités en cas de retard
- Ajout de remboursements
- Visualisation des états (en cours, remboursé, en retard)

#### Champs prêt :
- Client concerné (sélection)
- Montant
- Taux d’intérêt (%)
- Type de remboursement (mensuel, hebdomadaire, unique)
- Durée (en mois ou semaines)
- Date de début
- Garantie
- Agent responsable

#### Champs remboursement :
- Date de paiement
- Montant versé
- Mode de paiement (espèces, mobile money, virement)
- Remarques

---

### 3.4. Notifications

#### Fonctionnalités :
- Liste des échéances à venir
- Alertes pour prêts en retard
- Historique des actions critiques (création, suppression, remboursement)

---

## 4. Tableau de bord

La page d’accueil affichera :

- Nombre total de clients
- Montant total prêté
- Montant total remboursé
- Nombre de prêts en cours
- Nombre de prêts en retard
- Échéances du jour
- Dernières notifications
- Graphiques :
  - Montant prêté vs remboursé (par mois)
  - Nombre de prêts mensuels

---

## 5. Contraintes techniques

### Technologies utilisées :

- **Backend** : Laravel 11 (PHP 8.3)
- **Frontend** : Vue.js 3 (Composition API, Pinia)
- **Base de données** : PostgreSQL 15
- **Authentification** : Laravel Sanctum
- **Notifications** : Laravel Notification (stockées en base)
- **Interface** : Tailwind CSS
- **Langue** : Français
- **Mode de fonctionnement** : Hors ligne (localhost)

---

## 6. Architecture locale

- Application accessible via navigateur : `http://localhost:8000`
- Serveur Laravel exécuté localement avec `php artisan serve`
- Base de données PostgreSQL installée sur le même ordinateur
- Configuration via fichier `.env`
- Aucune dépendance réseau

---

## 7. Planning prévisionnel

| Phase                      | Durée estimée | Livrables associés               |
|----------------------------|---------------|----------------------------------|
| Analyse & conception       | 1 semaine     | Maquettes, modèle de données     |
| Développement backend      | 2 semaines    | API Laravel opérationnelle       |
| Développement frontend     | 2 semaines    | Interfaces Vue.js                |
| Intégration & test         | 1 semaine     | Application stable               |
| Formation & documentation  | 1 semaine     | Guide utilisateur + fiche résumé |

---

## 8. Livrables

- Code source Laravel + Vue.js
- Script de création de base PostgreSQL
- Fichier `.env.example` de configuration
- Manuel utilisateur (PDF)
- Manuel technique (README.md)
- Exemple de base avec données fictives

---

## 9. Critères de validation

- Application fonctionnelle en mode local
- Authentification et rôles opérationnels
- Enregistrement correct des clients, prêts et remboursements
- Notifications visibles dans l’interface
- Interface utilisateur intuitive en français

---

## 10. Maintenance et évolutivité

- Maintenance corrective pendant 1 mois après livraison
- Possibilités futures :
  - Export de reçus en PDF
  - Synchronisation multi-postes via réseau local
  - Intégration mobile money (Orange Money, MVola…)

---

## 11. Budget et responsabilités

- Le prestataire assure le développement, l’installation et la formation.
- CashToGo fournit les règles métier (taux, formules, rôles).
- Budget fixé à convenir selon complexité et itérations.

---

## 12. Annexes

### Maquettes à fournir :
- Tableau de bord
- Fiche client
- Fiche prêt
- Formulaire remboursement
- Page notifications
- Page utilisateurs et rôles

---

## 13. Contacts de l’entreprise CashToGo

- **Adresse** : 12 Rue de l’Innovation, Antananarivo 101, Madagascar  
- **Téléphone** : +261 34 12 345 67  
- **Email** : contact@cashtogo.mg  
- **Site web** : www.cashtogo.mg  
- **Support technique** : support@cashtogo.mg  
- **Responsable projet** : M. Jean Rakoto (jean.rakoto@cashtogo.mg)  
