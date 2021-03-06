# Повторение эксперимента на основе нейронной сети EditSql на базе датасета CoSQL
## Начало работы
Для подключения необходимых библиотек необходимо выполнить `%pip install -r editsql/requirements.txt`

Также необходимо скачать BERT модель: https://drive.google.com/file/d/1f_LEWVgrtZLRuoiExJa5fNzTS8-WcAX9/view?usp=sharing

Скачать базу данных с таблицами sql: https://drive.google.com/file/d/1a828mkHcgyQCBgVla0jGxKJ58aV8RsYK/view?usp=sharing - положить их в папку editsql/data/

Скачать датасет CoSql https://yale-lily.github.io/cosql
## Подготовка данных
Из-за ограничений по мощностям и времени, был взят 1% от всего датасета. 20 диалогов.
## Обучение 
Обучение проводилось с помощью запуска скрипта и его редактированием - актуальную версию можно найти в репозитории
```
cd editsql && ./run_cosql_editsql.sh
```
Было ограничено количество эпох до 10.
## Результаты
Так как данных было взято немного, модель переобучилась. На тренирвочном датасете значения очень хорошие, но на валидационном плохие:
| Dataset   |      Original      |  Experiment |
|:---------- |:-------------:|:------:|
| Train Loss |  0.0019981423803967966 | 0.10384764242917299 |
| Test Exact Match |    0.399   |   0.144   |

Обученная модель: [ссылка](https://drive.google.com/file/d/1qGRu8arSasrGibx7uboYfrIs6eRuEBNv/view?usp=sharing)

Выполнил Бузмаков Дмитрий, студент МФТИ ФИВТ группы М05-014а. 2021.
