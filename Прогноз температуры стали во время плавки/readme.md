
## План проекта
**Подготовка данных:**
- загрузка необходимых библиотек,
- визуализация данных,
- выбрала модели для обучения,
- подбор гиперпараметров.

**Анализ и предобработка данных:**
- получила общую информацию о данных (head, info, describe, графический анализ),
- переименовала столбцы на английский,
- *температура*  тут находится целевая. Удалила пустые значения и значения, в которых указана одна температура ковша + температура выше 1673 градуса по Цельсию (брак). Привела столбцы со временем к нужному формату. Для основного датасета взяла даннные о первой и последней температуре нагрева ковша, длительность нагрева ковша.
- *электроды, нагрев* с датасетом пришлось потрудиться. Не имеет пропусков, есть аномалия в реактивной мощности - убрала. Привела столбцы со временем к нужному формату. Из не получила данные полной мощности, длительность нагрева, длительность работы электродов. Для получения МАЕ < 6,8 эти данные оказались ключевыми, их все добавила в основной датасет.
- *газ* самый идеальный датасет. Без пропусков, аномалий и имеет один показатель на ковш.
- *сыпучие материалы и проволока* решила объединить, так как принцип работы с ними был одинаковый. Удалила присыпки, в которых было меньше 500 значений. В тех, что остались пустые значения заменила на "0". Их добавила в основной датасет.
- *сыпучие материалы и проволока, время* не использовала в работе, так как время присыпки не интересовало. От него ничего не зависело.

 **Основной датасет:**
   - собрала все необходимые даныне из 5 датасетов по 'key' в один,
   - обучала модели по нему.

 **Модели:**
   - выбор моделей,
   - подбор гиперпараметров,
   - обучение,
   - тестирование.

 **Выводы**



### Ключевые этапы:

1. Выделить нужные данные из всех датасетов в один.
2. Добавить недостающие признаки.
3. Определить целевой признак.
4. Выбрать модели и обучить их, подбирая гиперпараметры через ...SearchCV.
5. Протестировать модель, показавшую лучшие результаты на тренировочной выборке.
