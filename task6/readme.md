Бэкэнд: https://github.com/F1urst/kanban-backend/tree/main/kanban-backend
Фронтенд: https://github.com/F1urst/kanban-frontend/tree/main/kanban-frontend
Репозиторий: 


#сборка
git clone https://github.com/ivan123/kanban-backend.git
cd kanban-backend
docker build -t kanban-backend .

git clone https://github.com/ivan123/kanban-frontend.git
cd kanban-frontend
docker build -t kanban-frontend 

#запуск
cd task6
docker-compose up -d