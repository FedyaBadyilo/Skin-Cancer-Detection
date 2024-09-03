# ISIC 2024 - Выявление рака кожи с помощью 3D-TBP
## Описание
Данный пет-проект является исследовательской работой по выявлению рака кожи с помощью двух разных подходов: 
+ использование табличных данных (мета-данных) и обучение ML-моделей
+ использование снимков и обучение нейронных сетей
### Актуальность
Рак кожи - смертельное заболевание, поддающееся лечению на ранних стадиях. Однако в силу нехватки квалифицированного человеческого ресурса и регулярного массового дерматологического осмотра, многие люди, страдающие данной болезнью, не получают своевременной диагностики и помощи.
### Проблематика и задача
Алгоритмы искусственного интеллекта, основанные на дерматоскопии, уже зарекомендовали себя как полезный вспомогательный инструмент в работе клиницистов при диагностике меланомы, базально-клеточного и плоскоклеточного рака. Данная технология основана на обработке высококачественных дерматоскопических снимков, выполняемых только в специализированных узкопрофильных учреждениях, что, опять же, доступно ограниченному кругу пациентов. 

Из чего следует, что первоочередной задачей снижения уровня позднего диагностирования рака кожи среди населения является проведение массовой и нетрудоемкой первичной сортировки обращений пациентов, что возможно частично реализовать с помощью приспособления алгоритмов к оценке изображений низкого качества. 

В рамках решения данной задачи в текущей работе использовалась технология 3D TBP. Исследуемые данные представляют собой снимки огромного числа пациентов с трех разных континентов, близкие по качеству к фотографиям, сделанным с помощью мобильного телефона.

### Данные
Данные для исследования были взяты с сореванвания на платформе Kaggle [ISIC 2024 - Skin Cancer Detection with 3D-TBP](https://www.kaggle.com/competitions/isic-2024-challenge/overview). Туда входят метаданные и сами снимки. Более подробное описание данных вы можете найти на странице хакатона.

## Оценка качества
Для оченки качества работы моделей использовалась метрика recall - штрафующая модель за неопределенные раковые раковые поражения. Также для оценки качества использовалась кастомая метрика, по которой выстраивался leaderboard на [соревновании](https://www.kaggle.com/competitions/isic-2024-challenge/overview). Данная метрика является площадью под ROC-кривой выше 80%, то есть ее значения лежат на отрезке [0.0, 0.2]. Это связано с тем, что в пространстве ROC есть области, где значения TPR (true positive rate) неприемлемы в клинической практике. Более подробно вы можете прочитать о кастомном оценивании на страничке соревнования.

