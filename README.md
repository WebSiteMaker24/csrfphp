# CSRFProtection - Protection contre les attaques CSRF (Cross-Site Request Forgery)

## Description

La classe **CSRFProtection** est un composant de sécurité pour protéger votre application contre les attaques CSRF. Elle permet de générer un token unique pour chaque session utilisateur, de l'inclure dans vos formulaires HTML, et de valider ce token lors de la soumission du formulaire. Elle garantit ainsi que les requêtes HTTP proviennent bien de votre application et non d'une source malveillante.

## Fonctionnalités

### 1. **Génération d'un token CSRF**
   La méthode `generateToken()` génère un token CSRF unique pour chaque session utilisateur. Ce token est stocké dans la session de l'utilisateur et est utilisé pour valider la source des requêtes HTTP.

### 2. **Inclusion du token dans les formulaires**
   La méthode `includeToken()` permet d'inclure le token CSRF dans un formulaire HTML sous forme d'un champ caché. Cela permet de l'envoyer avec la requête POST pour vérifier sa validité.

### 3. **Validation du token**
   La méthode `validateToken($token)` vérifie si le token envoyé avec la requête correspond au token stocké dans la session. Si les tokens ne correspondent pas, la requête est considérée comme potentiellement malveillante et rejetée.

### 4. **Nettoyage du token après soumission**
   Une fois le token validé, la méthode `cleanupToken()` supprime le token de la session pour éviter qu'il soit utilisé plusieurs fois.

## Installation

1. Clonez ce projet dans votre environnement de développement local :

   ```bash
   git clone https://github.com/WebSiteMaker24/csrfphp.git
   cd csrfphp
