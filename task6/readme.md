Бэкэнд: https://github.com/F1urst/kanban-backend/tree/main/kanban-backend <br>
Фронтенд: https://github.com/F1urst/kanban-frontend/tree/main/kanban-frontend <br>
Репозиторий: https://github.com/F1urst/teach/tree/main/task6


#сборка <br>

mkdir task6 <br>
cd task6 <br>
https://github.com/F1urst/teach/blob/main/task6/docker-compose <br>


git clone https://github.com/F1urst/kanban-backend.git <br>
cd kanban-backend <br>
docker build -t kanban-backend <br>

cd ../

git clone https://github.com/F1urst/kanban-frontend.git <br>
cd kanban-frontend <br>
docker build -t kanban-frontend <br>

#запуск<br>
cd ../
<br>
docker-compose up -d

















