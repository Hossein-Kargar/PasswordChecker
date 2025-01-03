# PasswordChecker
Ce projet permet de vérifier si un mot de passe a été compromis en utilisant l'API **Pwned Passwords**. Pour assurer la confidentialité, seul le préfixe des 5 premiers caractères du hachage SHA-1 du mot de passe est envoyé à l'API. La vérification finale se fait localement, protégeant le mot de passe original.
