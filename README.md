# LangGraph Lab - Intelligent University Assistant

## Prérequis
- Python 3.10 ou supérieur
- Une clé API Google Gemini (créée sur Google AI Studio) OU une clé API OpenRouter (pour utiliser des modèles gratuits)

## Installation
1. Créer un environnement virtuel : `python -m venv env`
2. L'activer : `.\env\Scripts\Activate.ps1`
3. Installer les dépendances : `pip install notebook langgraph langchain langchain-google-genai langchain-openrouter pandas`

## Comment lancer le projet
1. Ouvrir Jupyter Notebook : `python -m notebook`
2. Ouvrir le fichier `langgraph_lab_Statement 2.ipynb`
3. Exécuter les cellules dans l'ordre. 
4. Lors de la partie III, une boîte de dialogue vous demandera votre clé API de manière sécurisée.

## Choix de conception (Design Choices)
- **Modèle :** J'ai utilisé le modèle `gemini-3.5-flash-lite` via `ChatGoogleGenerativeAI`. Le code inclut également une option commentée pour utiliser des modèles gratuits via `ChatOpenRouter` (`openrouter/free`).
- **Sécurité :** La calculatrice utilise le module `ast` (Safe Calculator) pour éviter les injections de code via `eval()`, comme recommandé dans l'énoncé.
- **Gestion d'erreurs :** Le classifieur inclut des blocs `try/except` pour gérer les limites de requêtes (erreurs 429 de l'API) et gère les questions vides via un nœud `Fallback`.
- **Mémoire :** J'ai utilisé `MemorySaver` avec des `thread_id` distincts pour isoler les conversations des différents utilisateurs (étudiants).
