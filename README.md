# Идентификация пользователей по посещенным веб-страницам
**Описание задачи:** В этом проекте мы будем решать задачу идентификации пользователя по его поведению в сети Интернет. 
Это сложная и интересная задача на стыке анализа данных и поведенческой психологии. В качестве примера, компания Яндекс 
решает задачу идентификации взломщика почтового ящика по его поведению. В двух словах, взломщик будет себя вести не так, 
как владелец ящика: он может не удалять сообщения сразу по прочтении, как это делал хозяин, он будет по-другому ставить 
флажки сообщениям и даже по-своему двигать мышкой. Тогда такого злоумышленника можно идентифицировать и "выкинуть" из 
почтового ящика, предложив хозяину войти по SMS-коду. Этот пилотный проект описан 
в [статье](https://habrahabr.ru/company/yandex/blog/230583/) на Хабрахабре. Похожие вещи делаются, например, 
в Google Analytics и описываются в научных статьях, найти можно многое по фразам "Traversal Pattern Mining" и 
"Sequential Pattern Mining".

Мы будем решать похожую задачу: по последовательности из нескольких веб-сайтов, посещенных подряд один и тем же 
человеком, мы будем идентифицировать этого человека. Идея такая: пользователи Интернета по-разному переходят по ссылкам, 
и это может помогать их идентифицировать (кто-то сначала в почту, потом про футбол почитать, затем новости, контакт, 
потом наконец – работать, кто-то – сразу работать).

**План проекта:**  
**1 неделя. Подготовка данных к анализу и построению моделей.**    
Первая часть проекта посвящена подготовке данных для дальнейшего описательного анализа и построения прогнозных моделей. 
Надо будет написать код для предобработки данных (исходно посещенные веб-сайты указаны для каждого пользователя в отдельном 
файле) и формирования единой обучающей выборки.  
- Подготовка обучающей выборки
- Работа с разреженным форматом данных

**2 неделя. Подготовка и первичный анализ данных.**  
На второй неделе я продолжу подготовливать данные для дальнейшего анализа и построения прогнозных моделей. 
Конкретно, ранее было определено что сессия – это последовательность из 10 посещенных пользователем сайтов, теперь же я 
сделаю длину сессии параметром, и потом при обучении прогнозных моделей выберу лучшую длину сессии. Также на этой неделе будет 
произведена проверка первых гипотез, связанных с наблюдениями.  
- Подготовка нескольких обучающих выборок для сравнения  
- Первичный анализ данных, проверка гипотез  

**3 неделя. Визуальный анализ данных и построение признаков.**  
Построение различных признаков и наглядное их представление на графиках. Оценка полезности того или иного признака в данной задаче.  
- Визуальный анализ данных
- Построение признаков  

**4 неделя. Сравнение алгоритмов классификации.**  
Обучение моделей классификации, сравнение на кросс-валидации несколько алгоритмов. Также для выбранного алгоритма будут 
построены кривые валидации (как качество классификации зависит от одного из гиперпараметров алгоритма) и кривые 
обучения (как качество классификации зависит от объема выборки).  
- Сравнение нескольких алгоритмов на сессиях из 10 сайтов
- Выбор параметров – длины сессии и ширины окна
- Идентификация конкретного пользователя и кривые обучения

**5 неделя. Соревнование Kaggle Inclass по идентификации пользователей.**  
Самая интересная часть. Здесь я принимаю участие в соревновании по идентификации конкретного пользователя, 
используя полученный опыт предыдущих недель.  

**6 неделя. Vowpal Wabbit**  
Знакомство с библиотекой Vowpal Wabbit и применение к данным по веб-сессиям.
