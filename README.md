<p align="center">
  <img src="https://capsule-render.vercel.app/content?type=waving&color=gradient&customColorList=10,15,20&height=220&section=header&text=joi%20%C2%B7%20deck%20%F0%9F%8E%AC&fontSize=50&animation=twinkling&fontColor=ffffff" width="100%" alt="Header Animé" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Next.js%2015-App%20Router-black?style=for-the-badge&logo=next.js&logoColor=white" alt="Next.js 15">
  <img src="https://img.shields.io/badge/MongoDB-7.0-green?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB">
  <img src="https://img.shields.io/badge/Docker-Supported-blue?style=for-the-badge&logo=docker&logoColor=white" alt="Docker">
  <br>
  <img src="https://img.shields.io/github/stars/Nathan-Pro-FR/JOI_Links_V3?style=flat-square&color=yellow" alt="Stars">
  <img src="https://img.shields.io/github/forks/TNathan-Pro-FR/JOI_Links_V3?style=flat-square&color=blue" alt="Forks">
  <img src="https://img.shields.io/github/issues/Nathan-Pro-FR/JOI_Links_V3?style=flat-square&color=red" alt="Issues">
</p>

<p align="center">
  <font size="4">✨ <strong>Un dashboard multimédia personnel ultra-rapide pour organiser et visionner vos clips vidéos.</strong> ✨</font>
</p>

<p align="center">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=nextjs,react,mongodb,docker,nodejs,ts,tailwind" alt="Tech Stack" />
  </a>
</p>

---

## 📸 Aperçu du Dashboard

<p align="center">
  <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM3BvMTVteXoxM2xtbXF6Y2Z4NXF6N3R5OHd5MXd5MXd5MXd5MXd5bSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/3o7qE1YN7aBOFPRw8E/giphy.gif" width="80%" style="border-radius: 10px; box-shadow: 0 4px 30px rgba(0, 0, 0, 0.5);" alt="Dashboard Demo Preview" />
</p>

---

## 🛠 Prérequis

<details open>
<summary><b>Cliquez pour afficher les outils nécessaires (Recommandé pour les juniors)</b></summary>
<br>

| Outil | Version | Statut | Rôle |
| :--- | :---: | :---: | :--- |
| **Node.js** | `18.0.0+` | 🟢 Requis | Faire tourner l'application Next.js |
| **MongoDB** | `7.0` ou Atlas | 🟢 Requis | Stocker les métadonnées de vos clips |
| **Docker** | `Latest` | 🟡 Optionnel | Déployer toute la stack en 1 ligne |

</details>

---

## 🚀 Installation & Lancement Rapide (Local)

Suivez ces étapes simples pour lancer le projet sur votre machine :

```bash
# 1️⃣ Cloner le projet et installer les dépendances
npm install

# 2️⃣ Dupliquer le fichier de configuration environnementale
cp .env.example .env.local
```

> [!TIP]
> 📝 **Configuration de la BDD :** Ouvrez le fichier `.env.local` nouvellement créé. Par défaut, la variable `MONGODB_URI` est configurée sur `mongodb://127.0.0.1:27017/joi_deck`. Si vous utilisez Atlas ou un port différent, modifiez cette ligne.

```bash
# 3️⃣ Injecter les données de test (Seed) pour éviter d'avoir un site vide 
npm run seed

# 4️⃣ Allumer le moteur de dev ! 🚀
npm run dev

```

🔗 Votre application brille maintenant sur : **[http://localhost:3000](https://www.google.com/search?q=http://localhost:3000)** !

---

## 🐳 Déploiement Instantané avec Docker

Vous ne voulez pas installer MongoDB en local ? Pas de problème. Docker Compose s'occupe de tout (App + Base de données).

```bash
# 🏗️ Build l'image Next.js standalone et démarre le cluster
docker compose -f local/docker-compose.yml up --build

```

> [!IMPORTANT]
> **Une fois le conteneur démarré**, ouvrez un **deuxième terminal** et lancez la commande suivante une seule fois pour charger les vidéos de démonstration :

```bash
# 🌱 Peupler la base de données Dockerisée
docker compose -f local/docker-compose.yml run --rm seed

```

> [!WARNING]
> **Gestion des ports :** Pour éviter d'entrer en conflit avec un processus MongoDB qui tournerait déjà sur votre machine (`27017`), l'instance MongoDB Docker est mappée sur le port extérieur **`27018`**.

---

### 🛑 Éteindre proprement la stack Docker :

```bash
docker compose -f local/docker-compose.yml down

# Astuce : Ajoutez le drapeau "-v" pour détruire complètement le volume et réinitialiser la BDD.
# docker compose -f local/docker-compose.yml down -v
```
