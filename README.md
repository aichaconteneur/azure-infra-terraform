# TP Terraform - Infrastructure as Code sur Azure

## 📖 Description

Ce projet a été réalisé dans le cadre d'un TP de découverte de **Terraform** et de l'**Infrastructure as Code (IaC)** sur **Microsoft Azure**.

L'objectif était de reproduire le déploiement d'une infrastructure Azure en utilisant Terraform afin d'automatiser la création et la gestion des ressources.

---

## 🎯 Objectifs

- Découvrir le fonctionnement de Terraform.
- Comprendre le principe de l'Infrastructure as Code.
- Déployer une infrastructure Azure de manière automatisée.
- Organiser le code avec des modules Terraform.
- Mettre en place un Remote State.
- Automatiser les déploiements avec GitHub Actions.

---

## 🛠️ Ressources créées

Au cours de ce TP, j'ai créé les ressources suivantes :

- 📦 Un **Storage Account**
- 📁 Deux conteneurs Blob Storage
- 🌐 Un **App Service** sous Linux
- ⚡ Une **Azure Function App**
- 🐳 Un **Azure Container Instance** exécutant Nginx
- 🌍 Un **Virtual Network (VNet)**
- 🔀 Deux **Subnets**
- 🔒 Un **Network Security Group (NSG)** avec ses règles de sécurité

---

## 📂 Structure du projet

```
terraform/
├── backend.tf
├── providers.tf
├── variables.tf
├── main.tf
├── outputs.tf
└── modules/
    ├── storage/
    ├── app-service/
    ├── function-app/
    ├── container/
    └── network/
```

---

## 🚀 Déploiement

Initialisation :

```bash
terraform init
```

Vérification :

```bash
terraform validate
```

Prévisualisation des changements :

```bash
terraform plan
```

Déploiement :

```bash
terraform apply
```

Suppression de l'infrastructure :

```bash
terraform destroy
```

---

## 🔐 Bonnes pratiques mises en œuvre

- Utilisation de modules Terraform.
- Variables séparées dans `terraform.tfvars`.
- Gestion du **Remote State** avec Azure Blob Storage.
- Authentification Azure via **OIDC**.
- Validation du code avec `terraform validate` et `tflint`.
- Automatisation des déploiements grâce à **GitHub Actions**.

---

## 📚 Compétences acquises

À travers ce TP, j'ai appris à :

- utiliser Terraform pour gérer une infrastructure Azure ;
- créer une architecture modulaire et réutilisable ;
- gérer l'état de l'infrastructure avec un Remote State ;
- automatiser les déploiements avec une pipeline CI/CD ;
- appliquer les bonnes pratiques de l'Infrastructure as Code.

---

## 👨‍💻 Auteur

Projet réalisé dans le cadre de la formation **DevSecOps Azure - Simplon**.