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
