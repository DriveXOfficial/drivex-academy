# 🚀 Guide d'installation Supabase pour DriveX Academy

Ce guide vous explique comment configurer Supabase (base de données gratuite) pour votre site DriveX Academy.

---

## 📋 Pourquoi Supabase ?

✅ **100% GRATUIT** (jusqu'à 500 MB de données)
✅ **Base de données PostgreSQL** professionnelle
✅ **API REST automatique** - pas besoin de coder le backend
✅ **Authentification intégrée** pour l'admin
✅ **Temps réel** - les modifications sont instantanées
✅ **Sauvegardes automatiques**

---

## 🎯 Étape 1 : Créer un compte Supabase

1. Allez sur **https://supabase.com**
2. Cliquez sur **"Start your project"**
3. Connectez-vous avec **GitHub** (recommandé) ou créez un compte
4. Vous arrivez sur le dashboard Supabase

---

## 🎯 Étape 2 : Créer un nouveau projet

1. Cliquez sur **"New Project"**
2. Remplissez les informations :
   - **Name** : `drivex-academy`
   - **Database Password** : Créez un mot de passe fort (notez-le !)
   - **Region** : Choisissez **"West EU (Ireland)"** (le plus proche de la France)
   - **Pricing Plan** : Sélectionnez **"Free"** (0$/mois)
3. Cliquez sur **"Create new project"**

⏳ **Attendez 2-3 minutes** pendant la création du projet...

---

## 🎯 Étape 3 : Créer la table "pilotes"

1. Dans le menu de gauche, cliquez sur **"Table Editor"**
2. Cliquez sur **"Create a new table"**
3. Configurez la table :

**Nom de la table** : `pilotes`

**Colonnes** :

| Nom | Type | Options |
|-----|------|---------|
| `id` | `int8` | Primary Key, Auto-increment |
| `nom` | `text` | Required |
| `points` | `int4` | Required, Default: 0 |
| `team` | `text` | Required |
| `role` | `text` | Optional |
| `description` | `text` | Optional |
| `photo` | `text` | Optional |
| `licence` | `text` | Optional |
| `isPresident` | `bool` | Default: false |
| `created_at` | `timestamptz` | Default: now() |

4. Cliquez sur **"Save"**

---

## 🎯 Étape 4 : Importer les données existantes

1. Restez dans **"Table Editor"**
2. Sélectionnez la table **"pilotes"**
3. Cliquez sur **"Insert"** → **"Insert row"**
4. Ajoutez vos pilotes un par un, OU :

**Méthode rapide - Import SQL** :

1. Cliquez sur **"SQL Editor"** dans le menu de gauche
2. Cliquez sur **"New query"**
3. Copiez-collez ce code SQL :

```sql
INSERT INTO pilotes (nom, points, team, role, description, photo, licence, isPresident)
VALUES
  ('Hadrien Chartier', 91, 'LMP2', 'Président DriveX Academy - Président LMP2 - Président LMP3 - Président LMGT3', 'Pilote expérimenté et leader de la DriveX Academy.', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', true),
  ('Félix Arbez', 12, 'Hypercar', 'Président Hypercar', 'Spécialiste Hypercar et leader de la catégorie.', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', true),
  ('Nathan Bagarry', 45, 'Hypercar', '', 'Pilote talentueux de la catégorie Hypercar.', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Damien Motte', 37, 'Hypercar', '', 'Pilote prometteur de la catégorie Hypercar.', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Sacha Frisque', 8, 'LMP2', '', 'Pilote LMP2 déterminé et rigoureux.', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Andre Frederic', 23, 'LMP2', '', 'Pilote expérimenté en LMP2.', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Nicolas Coulon', 0, 'LMGT3', '', 'Spécialiste GT et pilote LMGT3.', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Nicolas Bertrand', 0, 'LMGT3', '', 'Pilote LMGT3 prometteur.', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Stefen Guinard', 10, 'LMP2', '', 'New', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Hugo Wax', 10, 'Hypercar', '', 'New', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Said Benabadji', 25, 'Hypercar', '', 'New', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Anthony Gardelle', 25, 'Hypercar', '', 'New', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Josselin Dubosq', 25, 'Hypercar', '', 'New', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Lenny Cheron', 62, 'Hypercar', '', 'Spécialiste Hypercar.', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Antoine Moreira', 12, 'LMP2', '', 'New', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Alessandro Cortese', 20, 'LMP2', '', 'New', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false),
  ('Evan Waslam', 4, 'LMP2', '', 'New', 'https://www.groupe-atf.com/sites/default/files/styles/photo_personnel_630px_/public/default_images/fond_pdp_0.png?itok=sNsxciTS', 'AAA-1234-BBB', false);
```

4. Cliquez sur **"Run"** (ou F5)
5. Vérifiez que les données sont bien importées dans **"Table Editor"**

---

## 🎯 Étape 5 : Récupérer les clés API

1. Cliquez sur **"Settings"** (⚙️) dans le menu de gauche
2. Cliquez sur **"API"**
3. Vous verrez :

**Project URL** : `https://xxxxxxxxxx.supabase.co`
**anon/public key** : `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...`

📝 **NOTEZ CES DEUX VALEURS** - vous en aurez besoin pour le site !

---

## 🎯 Étape 6 : Configurer les permissions (RLS)

Pour la sécurité, nous devons activer Row Level Security :

1. Allez dans **"Authentication"** → **"Policies"**
2. Sélectionnez la table **"pilotes"**
3. Cliquez sur **"New Policy"**

**Policy 1 - Lecture publique** :

```sql
CREATE POLICY "Permettre lecture publique"
ON pilotes
FOR SELECT
TO public
USING (true);
```

**Policy 2 - Modification admin uniquement** :

```sql
CREATE POLICY "Permettre modifications admin"
ON pilotes
FOR ALL
TO authenticated
USING (true)
WITH CHECK (true);
```

4. Cliquez sur **"Review"** puis **"Save policy"**

---

## 🎯 Étape 7 : Créer un utilisateur admin

1. Allez dans **"Authentication"** → **"Users"**
2. Cliquez sur **"Add user"** → **"Create new user"**
3. Remplissez :
   - **Email** : `admin@drivexacademy.com` (ou votre email)
   - **Password** : Créez un mot de passe fort
   - **Auto Confirm User** : ✅ Cochez cette case
4. Cliquez sur **"Create user"**

📝 **NOTEZ CES IDENTIFIANTS** - vous les utiliserez pour vous connecter à l'admin !

---

## 🎯 Étape 8 : Intégrer Supabase dans votre site

Maintenant, vous devez ajouter les clés Supabase dans votre code HTML.

**Dans le fichier `index.html`**, cherchez cette section (vers la ligne 1500) :

```javascript
// Configuration Supabase
const SUPABASE_URL = 'VOTRE_PROJECT_URL';
const SUPABASE_ANON_KEY = 'VOTRE_ANON_KEY';
```

Remplacez par vos vraies valeurs :

```javascript
// Configuration Supabase
const SUPABASE_URL = 'https://xxxxxxxxxx.supabase.co';
const SUPABASE_ANON_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...';
```

---

## 🎯 Étape 9 : Tester

1. **Sauvegardez** le fichier `index.html`
2. **Commitez et pushez** sur GitHub
3. **Vercel redéploie automatiquement** (30 secondes)
4. **Testez votre site** :
   - Les pilotes doivent s'afficher
   - Connectez-vous à l'admin avec vos identifiants
   - Ajoutez/modifiez un pilote
   - Vérifiez que les changements sont sauvegardés

---

## ✅ Vérification finale

Vérifiez que tout fonctionne :

- [ ] Les pilotes s'affichent sur la page d'accueil
- [ ] Le classement est correct
- [ ] La connexion admin fonctionne
- [ ] Vous pouvez ajouter un pilote
- [ ] Vous pouvez modifier un pilote
- [ ] Vous pouvez supprimer un pilote
- [ ] Les changements sont persistants (rechargez la page)

---

## 🆘 Problèmes courants

**Problème** : "Failed to fetch"
- **Solution** : Vérifiez que SUPABASE_URL et SUPABASE_ANON_KEY sont corrects

**Problème** : "Row Level Security policy violation"
- **Solution** : Vérifiez que vous avez bien créé les policies (Étape 6)

**Problème** : "Invalid login credentials"
- **Solution** : Vérifiez l'email/mot de passe de l'utilisateur admin

**Problème** : Les données ne s'affichent pas
- **Solution** : Vérifiez que les données sont bien dans la table (Étape 4)

---

## 🎉 Félicitations !

Votre site DriveX Academy est maintenant connecté à Supabase avec :

✅ Base de données professionnelle gratuite
✅ Sauvegarde automatique des modifications
✅ API REST automatique
✅ Authentification sécurisée
✅ Temps réel

**Besoin d'aide ?** Contactez-moi ! 😊

---

## 📚 Ressources utiles

- **Documentation Supabase** : https://supabase.com/docs
- **Dashboard Supabase** : https://app.supabase.com
- **Support communautaire** : https://github.com/supabase/supabase/discussions