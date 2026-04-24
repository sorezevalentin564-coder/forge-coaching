# 🔥 FORGE - Guide de déploiement

Bienvenue ! Ce dossier contient ton site **FORGE** prêt à être mis en ligne sur **Vercel** (gratuit).

## 📦 Ce qu'il y a dans le dossier

- **`index.html`** → Ton site complet (design, contenu, chatbot)
- **`api/chat.js`** → Le backend qui fait marcher le chatbot IA
- **`vercel.json`** → Configuration Vercel
- **`package.json`** → Info du projet
- **`README.md`** → Ce fichier

---

## 🚀 Mise en ligne sur Vercel (étape par étape)

### Étape 1 : Créer un compte sur Vercel
1. Va sur [https://vercel.com](https://vercel.com)
2. Clique sur **"Sign Up"** → connecte-toi avec ton email ou GitHub (recommandé)
3. C'est gratuit, pas de carte bancaire demandée

### Étape 2 : Obtenir une clé API Anthropic
1. Va sur [https://console.anthropic.com](https://console.anthropic.com)
2. Crée un compte (gratuit)
3. Va dans **"API Keys"** → clique sur **"Create Key"**
4. **COPIE LA CLÉ** (elle commence par `sk-ant-...`) et garde-la quelque part en sécurité
5. Ajoute 5-10€ de crédits sur ton compte Anthropic (section "Billing") — ça durera des mois pour un chatbot
6. ⚠️ **Ne partage JAMAIS cette clé publiquement**

### Étape 3 : Déployer le site

**Option A : Glisser-déposer (le plus simple)** ⭐
1. Sur Vercel, clique sur **"Add New..."** → **"Project"**
2. Clique sur **"Browse"** ou glisse le dossier `forge-vercel` complet dans la zone
3. Vercel détecte automatiquement tout
4. **AVANT de cliquer "Deploy"**, ajoute la variable d'environnement :
   - Section **"Environment Variables"**
   - Name : `ANTHROPIC_API_KEY`
   - Value : colle ta clé API (`sk-ant-...`)
   - Clique **"Add"**
5. Clique **"Deploy"**
6. Attends 30 secondes → ton site est en ligne ! 🎉

**Option B : Via GitHub (plus pro, pour les mises à jour)**
1. Crée un compte sur [GitHub](https://github.com) si tu n'en as pas
2. Crée un nouveau dépôt (repository) et upload les fichiers du dossier `forge-vercel`
3. Sur Vercel, clique **"Add New" → "Project"** → connecte ton GitHub
4. Sélectionne le repo
5. Ajoute la variable d'environnement `ANTHROPIC_API_KEY` (voir étape 4 ci-dessus)
6. Clique **"Deploy"**

### Étape 4 : Vérifier que le chatbot marche
1. Une fois déployé, Vercel te donne une URL du genre `forge-coaching.vercel.app`
2. Ouvre l'URL sur ton téléphone ou ordi
3. Clique sur le bouton chatbot (en bas à droite)
4. Pose une question → la vraie IA Claude doit répondre ✅

---

## 🌐 Avoir ton propre nom de domaine (optionnel)

Si tu veux `forge.fr` ou `forge-coaching.com` au lieu de `xxx.vercel.app` :

1. Achète un domaine sur **OVH** (environ 12€/an pour `.fr` ou `.com`) ou **Namecheap**
2. Dans Vercel, va dans ton projet → **"Settings"** → **"Domains"**
3. Ajoute ton domaine et suis les instructions (tu dois changer quelques paramètres DNS chez ton registrar)
4. C'est fait en 5-10 minutes

---

## ✏️ Modifier le site après déploiement

**Si tu veux changer quelque chose (prix, texte, témoignage, etc.) :**

1. Ouvre `index.html` avec un éditeur de texte (VSCode, Sublime, ou même Notepad)
2. Cherche et modifie ce que tu veux
3. Sauvegarde
4. Sur Vercel, re-déploie (glisse le dossier à nouveau OU si tu utilises GitHub, fais un commit)
5. En 30 secondes, les changements sont en ligne

**OU plus simple** : tu me renvoies un message à moi (Claude), je fais les modifs, tu re-déploie.

---

## 💰 Ajouter les paiements (Stripe)

Quand tu seras prêt à encaisser :

1. Crée un compte sur [Stripe](https://stripe.com) (français, gratuit)
2. Crée tes 3 produits (STARTER, FORGE, ELITE) avec les bons prix
3. Génère des **Payment Links** pour chaque plan
4. Remplace les boutons du site pour qu'ils pointent vers les Payment Links Stripe
5. Quand un client paie, tu reçois une notif → tu lui envoies son questionnaire

On verra ça ensemble quand tu seras prêt.

---

## 💡 Coûts attendus

| Service | Coût |
|---------|------|
| Vercel (hébergement) | **0€** (gratuit pour toujours) |
| Claude API (chatbot) | ~**5-10€/mois** selon le trafic |
| Nom de domaine (optionnel) | **12€/an** |
| Stripe (paiements) | 1.4% + 0.25€ par transaction |

**Total au démarrage** : ~**5-15€/mois** (incroyablement peu pour un vrai business)

---

## ⚠️ Sécurité importante

- **JAMAIS** de clé API dans le code HTML directement
- La clé reste dans Vercel (variable d'environnement), elle n'est pas visible publiquement
- Si quelqu'un essaie d'abuser du chatbot (milliers de messages), tu peux mettre des limites

---

## 🆘 En cas de problème

- Le chatbot ne répond pas → vérifie que la variable `ANTHROPIC_API_KEY` est bien configurée dans Vercel
- Le site ne s'affiche pas → vérifie que `index.html` est bien à la racine du projet
- Erreur de déploiement → regarde les logs dans Vercel (onglet "Deployments")

Si tu bloques, renvoie-moi un message avec le problème ou une capture d'écran, on règle ça ensemble 💪

---

🔥 **Let's forge this.**
