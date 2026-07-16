## Résumé du TP

Dans le cadre de ce TP, j'ai mis en place une infrastructure Azure complète en Terraform, reproduisant les ressources créées manuellement en CLI lors des TPs précédents (Stockage et Réseau).

**Infrastructure déployée :**
- Un **Storage Account** avec deux conteneurs (`api-logs` privé, `api-config` public)
- Une **App Service** (Python 3.11, HTTPS uniquement)
- Une **Function App** avec son storage dédié
- Un **Container ** 
- Un **réseau virtuel** (VNet, 2 subnets) protégé par un Network Security Group (HTTP/HTTPS autorisés, tout le reste bloqué)

**Bonnes pratiques mises en œuvre :**
- Architecture en **modules réutilisables** (`modules/storage`, `modules/app-service`, `modules/function-app`, `modules/container`, `modules/network`)
- **Remote state** stocké dans Azure Blob Storage, avec verrouillage automatique
- **CI/CD** via GitHub Actions : `terraform plan` automatique sur chaque Pull Request, `apply` après merge sur `main`, authentification sans secret grâce à l'**OIDC**
- **Qualité de code** garantie par `tflint` (convention de nommage, variables/outputs documentés, absence de déclarations inutilisées) et un hook **pre-commit** qui bloque les commits non conformes

Ce TP m'a permis de comprendre concrètement l'intérêt de l'Infrastructure as Code : une infrastructure versionnée, reproductible et validée automatiquement avant chaque changement, plutôt que des commandes CLI exécutées manuellement sans trace ni contrôle.