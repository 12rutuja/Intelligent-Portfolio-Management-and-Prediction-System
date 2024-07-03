# Intelligent-Portfolio-Management-and-Prediction-System

How To make all the files inside the Repo

Python
import os

# Define the base directory path

base_dir = r"Path_To_Your_Repository"

# Define the structure as a dictionary
structure = {
    'app': {
        'api': ['__init__.py', 'main.py'],
        'data': ['__init__.py', 'fetch_data.py'],
        'models': ['__init__.py', 'train_model.py'],
        'utils': ['__init__.py', 'config.py', 'helpers.py'],
        '__init__.py': ''
    },
    'docker': {
        'api': ['Dockerfile'],
        'compose': ['docker-compose.yml'],
        'README.md': ''
    },
    'docs': {
        'architecture.md': '',
        'api_reference.md': ''
        # Add more documentation files as needed
    },
    'tests': {
        'unit': {},
        'integration': {},
        'README.md': ''
    },
    'frontend': {
        'public': ['index.html'],
        'src': {
            'components': {},
            'services': {},
            'App.js': ''
            # Add more frontend modules as needed
        },
        'README.md': ''
    },
    'requirements.txt': ''
}

def create_structure(base_path, structure):
    for name, contents in structure.items():
        path = os.path.join(base_path, name)
        if isinstance(contents, dict):
            os.makedirs(path, exist_ok=True)
            create_structure(path, contents)
        elif isinstance(contents, list):
            os.makedirs(path, exist_ok=True)
            for file in contents:
                with open(os.path.join(path, file), 'w') as f:
                    pass  # Creating an empty file
        elif isinstance(contents, str):
            os.makedirs(os.path.dirname(path), exist_ok=True)
            with open(path, 'w') as f:
                f.write(contents)

# Create the directory structure
create_structure(base_dir, structure)

print("Directory structure created successfully.")
"""
