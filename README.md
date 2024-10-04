# Технологии искусственного интеллекта  

© Петров М.В., старший преподаватель кафедры суперкомпьютеров и общей информатики, Самарский университет

## Лекции

1. [Библиотека Pandas](lectures/lecture_1/lecture_1.ipynb)
2. [Визуализация данных](lectures/lecture_2/lecture_2.ipynb)
3. Задачи классификации. Метрики качества
4. Деревья решений
5. Линейная регрессия
6. Градиентный бустинг
7. Перцептрон

> С визуализацией некоторых JS графиков может помочь [nbviewer](https://nbviewer.org/). Например, графики с использованием `Plotly` во 2 лекциии и некоторые JS графики из 6 лекции отображаются в `nbviewer`, но графики, сгенерированные `CatBoost` &ndash; нет (хотя под капотом там тоже `Plotly`).  
> Для того чтобы графики с JS кодом и некоторые HTML блоки рендерились нормально, необходимо подписать ноутбук согласно [Trusting Notebooks](https://jupyter-notebook.readthedocs.io/en/latest/notebook.html#trusting-notebooks):
> ```bash
> jupyter trust lecture_6.ipynb
> ```
> Должно появиться сообщение:
> ```bash
> Signing notebook: .\lecture_6.ipynb
>```

## Лабораторные работы

1. [Pandas](labs/lab_1.md)
2. [Визуализация данных](labs/lab_2.md)
3. Классификация *kNN*
4. Классификация. Деревья решений
5. Линейная регрессия
6. Градиентный бустинг
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