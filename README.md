# LangGraph Lab - Intelligent University Assistant

## Prérequis
- Python 3.10 ou supérieur
- Une clé API Google Gemini (créée sur Google AI Studio)

## Installation
1. Créer un environnement virtuel : `python -m venv env`
2. L'activer : `.\env\Scripts\Activate.ps1`
3. Installer les dépendances : `pip install notebook langgraph langchain langchain-google-genai pandas`

## Comment lancer le projet
1. Ouvrir Jupyter Notebook : `python -m notebook`
2. Ouvrir le fichier `langgraph_lab_Statement.ipynb`
3. Exécuter les cellules dans l'ordre. 
4. Lors de la partie III, une boîte de dialogue vous demandera votre clé API Gemini.

## Choix de conception (Design Choices)
- **Modèle :** J'ai utilisé le modèle `gemini-2.5-flash` via `ChatGoogleGenerativeAI` au lieu d'OpenAI pour des raisons de coût et de disponibilité.
- **Sécurité :** La calculatrice utilise le module `ast` (Safe Calculator) pour éviter les injections de code via `eval()`, comme recommandé dans l'énoncé.
- **Mémoire :** J'ai utilisé `MemorySaver` avec des `thread_id` distincts pour isoler les conversations des différents utilisateurs (étudiants).