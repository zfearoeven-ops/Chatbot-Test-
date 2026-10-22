# Assistant ACM — Google Gemini (V7)

Cette version est **100 % connectée à l'API Google Gemini**, et **n'utilise pas Ollama**.

Contenu :

- `app.py` — interface Streamlit : chatbot, boutons-guides, test API, saisie du séjour, import Excel facultatif.
- `acm_core.py` — consignes ACM, règle interne 1/8, lecture Excel et historique.
- `requirements.txt` — dépendances pour Streamlit Community Cloud.
- `GUIDE_DEPLOIEMENT.md` — instructions très simples de déploiement.
- `exemple_sejours_FICTIFS.xlsx` — classeur pour tester sans données confidentielles ; ne pas publier sur GitHub.

## Les 3 fichiers à transférer à la racine du dépôt GitHub

`app.py`, `acm_core.py`, `requirements.txt`.

## Secrets (dans les paramètres Streamlit, jamais dans GitHub)

```toml
GEMINI_API_KEY = "votre_clé_privée"
# Facultatif : ajoute un code partagé, pas une vraie authentification
# APP_ACCESS_CODE = "un-code-long-et-non-trivial"
```

Le modèle par défaut est `gemini-2.5-flash`, qui possède un niveau gratuit selon l'éligibilité du compte et les quotas actuels. Vérifier https://ai.google.dev/gemini-api/docs/pricing

## Lancer sur Windows en local (facultatif)

Depuis PowerShell ouvert dans ce dossier :

```powershell
python -m pip install -r requirements.txt
$env:GEMINI_API_KEY="VOTRE_CLE_PRIVEE"
python -m streamlit run app.py
```

Ne sauvegardez pas la clé dans le code, un historique partagé, une capture, ni dans GitHub.

## Confidentialité

Cette app **n'est pas un service professionnel validé**. L'offre gratuite Gemini peut utiliser les contenus soumis pour améliorer les produits de Google. Ne pas transmettre de données personnelles de mineurs, de santé, de familles ni d'informations confidentielles. Si vous travaillez sur un PC professionnel ou avec des collègues, demandez l'accord de votre organisation / DPO / service informatique avant diffusion.

Avec le mode **public**, le lien peut être trouvé et utilisé par des personnes extérieures. Un `APP_ACCESS_CODE` facultatif réduit l'accès spontané, mais n'est ni un contrôle des identités, ni une solution de conformité RGPD.
