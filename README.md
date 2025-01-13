# Технологии искусственного интеллекта  

© Петров М.В., старший преподаватель кафедры суперкомпьютеров и общей информатики, Самарский университет

> [Version in english language](README_EN.md).

## Лекции

1. [Библиотека Pandas](lectures/lecture_1/lecture_1.ipynb)
2. [Визуализация данных](lectures/lecture_2/lecture_2.ipynb)
3. [Задачи классификации. Метрики качества](lectures/lecture_3/lecture_3.ipynb)
4. [Деревья решений](lectures/lecture_4/lecture_4.ipynb)
5. [Линейная регрессия](lectures/lecture_5/lecture_5.ipynb)
6. [Градиентный бустинг](lectures/lecture_6/lecture_6.ipynb)
   - [HTML версия без графиков CatBoost](lectures/lecture_6/lecture_6.html)
7. [Перцептрон](lectures/lecture_7/lecture_7.ipynb)

Troubleshooting:
- [Проблема с отображением JS графиков](#проблема-с-отображением-js-графиков)
- [Версии Python и библиотек](#версии-python-и-библиотек)

## Лабораторные работы

1. [Pandas](labs/lab_1.md)
2. [Визуализация данных](labs/lab_2.md)
3. [Классификация *kNN*](labs/lab_3.md)
4. [Классификация. Деревья решений](labs/lab_4.md)
5. [Линейная регрессия](labs/lab_5.md)
6. [Градиентный бустинг](labs/lab_6.md)
7. Перцептрон

### Требования к оформлению лабораторных работ

1. Присылать ответы в jupyter-блокнотах со следующим названием файла: `<Номер группы>_<ФамилияИО>_lab_<номер лабораторной>_<тема лабораторной>.ipynb`, например, `0000_PetrovMV_lab_1_pandas.ipynb`
   
   В заголовке самого блокнота (в самой первой ячейке) - название задания и ФИО автора.

2. Все ячейки, требующие вычисления, должны быть вычислены, и в присылаемом блокноте должен содержаться вывод ячеек.
   > Пустой блокнот с очищенным выводом ячеек не принимается.

3. Внутри в markdown-ячейках обязательно дублировать условие задачи в виде оглавления, каждую подзадачу оформить markdown-ячейкой с описанием подзадачи.

4. Желательно прокомментировать блоки кода, выполняющие ту или иную функцию.

5. Код по возможности структурировать в небольшие логические блоки, каждый в своей ячейке, чтобы легко было его понять.

6. Если в работе используется какой-то датасет, то необходимо указать ссылку на него и на описание датасета. 
Желательно привести краткое описание датасета.

### Датасеты

- [Встроенные датасеты в sklearn](https://scikit-learn.org/stable/datasets)
- [Google-поиск по датасетам](https://datasetsearch.research.google.com/)

Репозитории с датасетами:
- [Kaggle](https://www.kaggle.com/datasets)  
  [Как начать работу в Kaggle: руководство для новичков в Data Science](https://habr.com/ru/post/248395/)
- [Материалы с курса OpenDataScience](https://nbviewer.org/github/Yorko/mlcourse.ai/tree/main/data/) или [тут](https://github.com/Yorko/mlcourse.ai/tree/master/data/)
- [Датасеты университета Калифорнии](https://archive.ics.uci.edu/ml/datasets)
- [Учебные датасеты для R](https://vincentarelbundock.github.io/Rdatasets/datasets.html)
- [Датасеты от FiveThirtyEight](https://data.fivethirtyeight.com/)
- [Подборка на habr](https://habr.com/ru/post/452740)
- [Подборка на Reddit](https://www.reddit.com/r/datasets/)
- [Ещё подборка 1](https://towardsai.net/p/machine-learning/best-free-datasets-for-machine-learning-and-data-science/stanfordai/3451/)
- [Ещё подборка 2](https://towardsdatascience.com/top-sources-for-machine-learning-datasets-bb6d0dc3378b)

Разные открытые данные:
- [Списки источников открытых данных от Яндекса](https://yandex.ru/promo/oda/useful)
- [Портал открытых данных Российской Федерации](https://data.gov.ru/)
- [Портал открытых данных правительства Москвы](https://data.mos.ru/opendata)
- [Открытые данные Сбербанка](https://www.sberbank.com/ru/analytics/opendata)
- [Открытые данные Министерства финансов РФ](https://www.minfin.ru/opendata/)
- [Открытые данные Министерства культуры РФ](https://opendata.mkrf.ru/opendata/)

### Разное

#### Проблема с отображением JS графиков

С визуализацией некоторых JS графиков может помочь [nbviewer](https://nbviewer.org/). Например, графики с использованием `Plotly` во 2 лекциии и некоторые JS графики из 6 лекции отображаются в `nbviewer`, но графики, сгенерированные `CatBoost` &ndash; нет (хотя под капотом там тоже `Plotly`).  
Для того чтобы графики с JS кодом и некоторые HTML блоки рендерились нормально, необходимо подписать ноутбук согласно [Trusting Notebooks](https://jupyter-notebook.readthedocs.io/en/latest/notebook.html#trusting-notebooks):
```bash
jupyter trust lecture_6.ipynb
```
Должно появиться сообщение:
```bash
Signing notebook: .\lecture_6.ipynb
```

#### Версии Python и библиотек

Версия Python: 3.10.11  
Версии установленных библиотек:

| Библиотека              | Версия      |
|-------------------------|-------------|
| catboost                | 1.2.5       |
| ipykernel               | 6.19.2      |
| ipympl                  | 0.9.3       |
| ipython                 | 8.7.0       |
| ipython-genutils        | 0.2.0       |
| ipywidgets              | 8.1.2       |
| jupyterlab              | 4.3.3       |
| jupyterlab-execute-time | 3.1.2       |
| kaleido                 | 0.1.0.post1 |
| matplotlib              | 3.8.4       |
| pandas                  | 2.2.1       |
| plotly                  | 5.19.0      |
| scikit-learn            | 1.4.1.post1 |
| seaborn                 | 0.13.2      |
| shap                    | 0.45.0      |
| xgboost                 | 2.0.3       |