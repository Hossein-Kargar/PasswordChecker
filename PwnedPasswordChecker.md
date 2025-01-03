# Pwned Password Checker

Ce projet fournit un outil permettant de vérifier si un mot de passe a été compromis dans une fuite de données publique, en utilisant l'API **Pwned Passwords**. Grâce à une approche sécurisée, le mot de passe n'est jamais partagé directement avec l'API, garantissant ainsi la confidentialité de l'utilisateur.

---

## Fonctionnalités

- **Vérification de mot de passe** : Détermine si un mot de passe a fait l’objet d’une compromission.
- **Utilisation sécurisée de l'API** : Seules les 5 premières lettres du hachage SHA-1 du mot de passe sont partagées avec le service externe.
- **Vérification locale** : La correspondance finale entre le mot de passe haché et les résultats de l’API est effectuée localement pour protéger les informations sensibles.

---

## Comment ça fonctionne ?

1. Le mot de passe à vérifier est transformé en **hachage SHA-1**.
2. Les 5 premiers caractères du hachage (le préfixe) sont envoyés à l’API **Pwned Passwords**.
3. L’API renvoie une liste des hachages correspondants qui partagent le même préfixe.
4. Le programme effectue une comparaison locale entre le suffixe du hachage et les résultats, déterminant ainsi si le mot de passe a été trouvé dans la base de données des mots de passe compromis.

---

## Prérequis

- **Python 3.x**
- Bibliothèque `requests` (installable via `pip install requests`)

---

## Installation

1. Clonez ce dépôt en local :
   ```bash
   git clone https://github.com/votre-utilisateur/pwned-password-checker.git
   cd pwned-password-checker
   ```
2. Assurez-vous d'avoir les dépendances nécessaires :
   ```bash
   pip install -r requirements.txt
   ```

(Le fichier `requirements.txt` pourrait inclure : `requests`)

---

## Utilisation

Exécutez le script en ligne de commande en passant les mots de passe à vérifier comme arguments :

```bash
python pwned_password_checker.py "password1" "password2" "password3"
```

Exemple de sortie :

```bash
password1 was found 15 times. Change it.
password2 was not found.
```

---

## Sécurité

Ce projet a été conçu avec la confidentialité à cœur :
- **Aucune donnée brute sensible n’est transmise à l’API.**
- Seules les 5 premières lettres du hachage SHA-1 sont partagées.
- Tous les calculs sensibles sont effectués localement.

---

## Contribution

Les contributions sont les bienvenues ! N’hésitez pas à ouvrir une [issue](https://github.com/votre-utilisateur/pwned-password-checker/issues) ou une pull request pour améliorer le projet.

---

## Licence

Ce projet est sous licence [MIT](LICENSE).