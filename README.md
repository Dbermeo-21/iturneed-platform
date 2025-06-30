# iturneed-platform/
├── backend/               # Django (API)
│   ├── iturneed_api/
│   ├── manage.py
│   ├── requirements.txt
│   └── Dockerfile
├── frontend/              # React (Web)
│   ├── public/
│   ├── src/
│   ├── package.json
│   └── Dockerfile
├── docker-compose.yml     # Configuración para desarrollo local
└── README.md             # Documentación
Backend (backend/requirements.txt)
Django==4.2
djangorestframework==3.14
psycopg2-binary==2.9.6
django-cors-headers==4.2
Frontend (frontend/package.json)
{
  "name": "iturneed-frontend",
  "version": "1.0.0",
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test"
  },
  
  "dependencies": {
    "react": "^18.2",
    "react-dom": "^18.2",
    "axios": "^1.3"
  }
}
# Clona el repositorio
git clone https://github.com/tu-usuario/iturneed-platform.git
cd iturneed-platform

# Configura estructura de carpetas
mkdir -p backend frontend

# Inicializa backend Django
cd backend
django-admin startproject iturneed_api .

# Inicializa frontend React
cd ../frontend
npx create-react-app .

# Commit inicial
git add .
git commit -m "Estructura inicial del proyecto"
git push origin main

/.github/workflows/django.yml
name: Django CI

on: [push]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: Set up Python
      uses: actions/setup-python@v4
      with:
        python-version: '3.10'
    - name: Install dependencies
      run: |
        cd backend
        pip install -r requirements.txt
    - name: Run tests
      run: |
        cd backend
        python manage.py test
        
/.github/workflows/react.yml
name: React CI

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: Use Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18.x'
    - run: |
        cd frontend
        npm install
        npm run build
