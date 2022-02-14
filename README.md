# python-flask-docker
Итоговый проект курса "Машинное обучение в бизнесе"

Стек:

ML: sklearn, pandas, numpy
API: flask
Данные: с kaggle - https://www.kaggle.com/fedesoriano/stroke-prediction-dataset

Задача: предсказать по заданным параметрам вероятность инсульта (поле stroke). Бинарная классификация

Используемые признаки:

- age (float)
- hypertension (float)
- heart_disease (float)
- smoking_status (float)

Модель: RandomForest

### Клонируем репозиторий и создаем образ
```
$ git clone https://github.com/SergChupin/ML_in_business/tree/lesson_9_-_course_project.git
$ cd GB_docker_flask_example
$ docker build -t SergChupin/ML_in_business/tree/lesson_9_-_course_project .
```

### Запускаем контейнер

Здесь Вам нужно создать каталог локально и сохранить туда предобученную модель (<your_local_path_to_pretrained_models> нужно заменить на полный путь к этому каталогу)
```
$ docker run -d -p 8180:8180 -p 8181:8181 -v <your_local_path_to_pretrained_models>:/app/app/models SergChupin/ML_in_business/tree/lesson_9_-_course_project
```

### Переходим на localhost:8181
