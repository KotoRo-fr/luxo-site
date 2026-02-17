# Luxo - Site Web Optimisé

Site web optimisé pour conversion, SEO et crédibilité de Luxo, assistant IA personnel.

## 📦 Contenu du package

- `index.html` - Page d'accueil optimisée (tous les éléments de conversion)
- `demo.html` - Dashboard de démonstration interactif
- `comment-ca-marche.html` - Page détaillée du processus
- `mentions-legales.html` - Mentions légales et RGPD
- `404.html` - Page d'erreur personnalisée
- `CHANGES.md` - Liste détaillée des modifications
- `README.md` - Ce fichier (instructions de déploiement)

## 🚀 Déploiement

### Option 1 : Vercel (recommandé)

1. **Installer Vercel CLI** (si pas déjà fait) :
   ```bash
   npm i -g vercel
   ```

2. **Déployer** :
   ```bash
   cd luxo-site-optimized
   vercel
   ```

3. **Suivre les instructions** :
   - Project name : `luxo-site`
   - Framework preset : `Other`
   - Build command : (laisser vide)
   - Output directory : `./`

4. **Déploiement en production** :
   ```bash
   vercel --prod
   ```

### Option 2 : Netlify

1. **Via Netlify Drop** :
   - Aller sur [https://app.netlify.com/drop](https://app.netlify.com/drop)
   - Glisser-déposer le dossier `luxo-site-optimized`

2. **Via Netlify CLI** :
   ```bash
   npm install netlify-cli -g
   netlify deploy --dir=luxo-site-optimized --prod
   ```

### Option 3 : GitHub Pages

1. **Créer un repo GitHub** et pousser les fichiers :
   ```bash
   git init
   git add .
   git commit -m "Site Luxo optimisé"
   git branch -M main
   git remote add origin https://github.com/VOTRE-USERNAME/luxo-site.git
   git push -u origin main
   ```

2. **Activer GitHub Pages** :
   - Aller dans Settings → Pages
   - Source : Deploy from branch `main` → `/root`
   - Save

### Option 4 : FTP classique

Uploader tous les fichiers HTML à la racine de votre hébergement via FileZilla, Cyberduck ou le gestionnaire de fichiers de votre hébergeur.

## ⚙️ Configuration post-déploiement

### 1. Google Analytics 4

**Fichier à modifier :** `index.html` (ligne ~35)

```html
<!-- Remplacer -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXX"></script>
<script>
    gtag('config', 'G-XXXXXXXX');
</script>

<!-- Par votre vrai ID Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-VOTRE-ID"></script>
<script>
    gtag('config', 'G-VOTRE-ID');
</script>
```

**Comment obtenir votre ID GA4 :**
1. Aller sur [Google Analytics](https://analytics.google.com/)
2. Admin → Propriété → Flux de données → Web
3. Copier l'ID de mesure (format `G-XXXXXXXXXX`)

### 2. LinkedIn Pixel

**Fichier à modifier :** `index.html` (ligne ~43)

```javascript
// Remplacer
_linkedin_partner_id = "LINKEDIN_PLACEHOLDER";

// Par votre Partner ID
_linkedin_partner_id = "1234567";
```

**Comment obtenir votre Partner ID :**
1. Aller sur [LinkedIn Campaign Manager](https://www.linkedin.com/campaignmanager/)
2. Account Assets → Insight Tag
3. Copier votre Partner ID (numérique)

### 3. Données entreprise

**Fichier à modifier :** `mentions-legales.html`

Remplacer les placeholders suivants :
- `[Adresse complète à compléter]` → Votre adresse
- `[Ville]` et `[Numéro SIRET]` → Vos infos légales
- `[Nom du responsable légal]` → Directeur de publication
- `[fonction]` → Fonction du responsable
- `[Numéro à compléter]` → Téléphone

### 4. Coordonnées de contact

**Fichier à modifier :** `index.html` (formulaire de contact)

Le formulaire utilise actuellement `mailto:`. Options :

**Option A - Service tiers (recommandé) :**
- [Formspree](https://formspree.io/) : Gratuit jusqu'à 50 soumissions/mois
- [Basin](https://usebasin.com/) : Gratuit jusqu'à 100 soumissions/mois

Remplacer :
```html
<form action="mailto:contact@luxo-assistant.fr" method="post">
```

Par :
```html
<form action="https://formspree.io/f/VOTRE-FORM-ID" method="post">
```

**Option B - Backend custom :**
Créer un endpoint API pour traiter les soumissions.

## ✅ Checklist post-déploiement

### Tracking & Analytics

- [ ] Remplacer `G-XXXXXXXX` par votre vrai ID Google Analytics
- [ ] Remplacer `LINKEDIN_PLACEHOLDER` par votre Partner ID LinkedIn
- [ ] Vérifier que les events sont trackés (tester avec l'extension GA Debugger)

### Données légales

- [ ] Compléter l'adresse complète dans `mentions-legales.html`
- [ ] Ajouter SIRET et numéros d'immatriculation
- [ ] Indiquer le directeur de publication
- [ ] Ajouter le numéro de téléphone
- [ ] Vérifier la conformité RGPD avec un avocat

### Configuration formulaire

- [ ] Configurer Formspree ou autre service de formulaire
- [ ] Tester la réception des emails
- [ ] Ajouter une page de confirmation "Merci"

### Tests techniques

- [ ] Tester le site sur mobile (iPhone/Android)
- [ ] Tester sur différents navigateurs (Chrome, Firefox, Safari, Edge)
- [ ] Vérifier tous les liens internes
- [ ] Tester le formulaire de contact
- [ ] Vérifier le chat widget
- [ ] Tester le cookie banner
- [ ] Vérifier le exit-intent popup
- [ ] Tester la FAQ (accordion)

### SEO & Performance

- [ ] Générer et uploader une image OG (`og-image.jpg`, 1200x630px)
- [ ] Générer un `sitemap.xml` (via [XML-Sitemaps.com](https://www.xml-sitemaps.com/))
- [ ] Créer un `robots.txt` minimal
- [ ] Vérifier la vitesse sur [PageSpeed Insights](https://pagespeed.web.dev/)
- [ ] Soumettre le site à Google Search Console
- [ ] Vérifier les rich snippets avec [Schema Markup Validator](https://validator.schema.org/)

### Sécurité

- [ ] Activer HTTPS (certificat SSL)
- [ ] Configurer les en-têtes de sécurité (CSP, HSTS)
- [ ] Vérifier l'absence de failles XSS

## 📊 Fichiers robots.txt et sitemap.xml

### robots.txt

Créer un fichier `robots.txt` à la racine :

```
User-agent: *
Allow: /

Sitemap: https://luxo-site.vercel.app/sitemap.xml
```

### sitemap.xml

Créer un fichier `sitemap.xml` à la racine :

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://luxo-site.vercel.app/</loc>
    <lastmod>2026-02-17</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://luxo-site.vercel.app/demo.html</loc>
    <lastmod>2026-02-17</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://luxo-site.vercel.app/comment-ca-marche.html</loc>
    <lastmod>2026-02-17</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://luxo-site.vercel.app/mentions-legales.html</loc>
    <lastmod>2026-02-17</lastmod>
    <changefreq>yearly</changefreq>
    <priority>0.3</priority>
  </url>
</urlset>
```

## 🎨 Image OG (Open Graph)

Créer une image `og-image.jpg` de **1200x630px** avec :
- Logo Luxo
- Texte : "Gagnez 15h par semaine avec Luxo"
- Fond navy/gold
- Uploader à la racine du site

## 🔧 Support

Pour toute question technique :
- Email : contact@luxo-assistant.fr
- Documentation : (à créer si besoin)

## 📈 KPIs à surveiller

Après le déploiement, suivre ces métriques dans GA4 :

1. **Trafic** : Pages vues, visiteurs uniques
2. **Engagement** : Temps sur site, taux de rebond
3. **Conversions** :
   - Clics sur "Essayer gratuitement"
   - Soumissions du formulaire
   - Visionnage de la démo
4. **Parcours** : Pages les plus visitées, chemins de navigation
5. **Sources** : Origine du trafic (organique, direct, réseaux sociaux)

## ⚡ Optimisations futures

- Ajouter un blog pour le SEO
- Créer des landing pages spécifiques par secteur
- Ajouter des études de cas détaillées
- Implémenter un chatbot live (Intercom, Crisp)
- Tests A/B sur les CTA

---

**Version :** 1.0  
**Date :** Février 2026  
**Auteur :** Luxo Team