# Прогнозирование конечных свойств композиционных материалов
Выпускная квалификационная работа по курсу «Data Science» в ЦДО МГТУ им. Н. Э. Баумана по теме: "Прогнозирование конечных свойств новых материалов (композиционных материалов)". Описание: Композиционные материалы — это искусственно созданные материалы, состоящие из нескольких других с четкой границей между ними. Композиты обладают теми свойствами, которые не наблюдаются у компонентов по отдельности. При этом композиты являются монолитным материалом, т. е. компоненты материала неотделимы друг от друга без разрушения конструкции в целом. Яркий пример композита - железобетон. Бетон прекрасно сопротивляется сжатию, но плохо растяжению. Стальная арматура внутри бетона компенсирует его неспособность сопротивляться сжатию, формируя тем самым новые, уникальные свойства. Современные композиты изготавливаются из других материалов: полимеры, керамика, стеклянные и углеродные волокна, но данный принцип сохраняется. У такого подхода есть и недостаток: даже если мы знаем характеристики исходных компонентов, определить характеристики композита, состоящего из этих компонентов, достаточно проблематично. Для решения этой проблемы есть два пути: физические испытания образцов материалов, или прогнозирование характеристик. Суть прогнозирования заключается в симуляции представительного элемента объема композита, на основе данных о характеристиках входящих компонентов (связующего и армирующего компонента). Цель работы разработать модели для прогноза модуля упругости при растяжении, прочности при растяжении и соотношения «матрица-наполнитель». На входе имеются данные о начальных свойствах компонентов композиционных материалов, содержащихся в двух файлах:

X_bp.xlsx, состоящий из 1024 строки и 11 столбцов (1 строка содержит – названия столбцов): a) Соотношение матрица-наполнитель; b) Плотность, кг/м3; c) модуль упругости, ГПа; d) Количество отвердителя, м.%; e) Содержание эпоксидных групп,%_2; f) Температура вспышки, С_2; g) Поверхностная плотность, г/м2; h) Модуль упругости при растяжении, ГПа; i) Прочность при растяжении, МПа; j) Потребление смолы, г/м2;
X_nup.xlsx, состоящий из 1040 строки и 3 столбцов: k) Шаг нашивки l) Плотность нашивки m) Угол нашивки
На выходе необходимо спрогнозировать ряд конечных свойств получаемых композиционных материалов:

Модуль упругости при растяжении, ГПа;
Прочность при растяжении, МПа; Написать нейронную сеть, которая будет рекомендовать: Соотношение матрица-наполнитель.
Структура репозитория:

data - папка с файлами: X_bp.xlsx - первый датасет, X_nup.xlsx - второй датасет, X_sum.xlsx - объединенный датасет, X_sum_norm.xlsx - очищенный от выбросов, нормализованный датасет, X_sum_22.xlsx - суммарный датасет, содержащий 23 строки, X_sum_norm.xlsx - суммарный нормализованный датасет, содержащий 23 строки.

app_flask - папка с файлами для работы пользовательского приложения, включая приложение.

VKR_1.ipynb - Загрузка датасетов, разведочный анализ, предобработка данных

VKR_2.ipynb - Анализ датасета без сгенерированных данных (первые 23 строчки)

VKR_clean_23.ipynb - Выявление и удаление сгенерированных данных

VKR_nero.ipynb - нейросеть для Соотношения матрица-наполнитель

VKR_model.ipynb - Построение моделей для прогноза модуля упругости при растяжении и про…

VKR_model_2_clean_2.ipynb - Построение моделей для прогноза модуля упругости при растяжении и про…

VKR_nero_mn.ipynb - Нейронка с рекомендацией "Матрица-наполнитель"

ВКР_pptx - презентация в формате pdf для защиты

ВКР_2.pdf -пояснительная записка в формате pdf

Инструкция использования приложения:

Приложение позволяет решать задачу прогнозирования "Соотношение матрица наполнитель".

Для получения прогноза необходимо

а) запустить app.py,

б) совершить запуск всех ячеек,

в) в появившейся строке ( * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)) - нажать на ссылку: http://127.0.0.1:5000/.

г) В новом открывшемся окне (сайте) ввести 12 входных параметров и нажать "Рассчитать".

д) появится результат в виде числа с плавающей точкой.

Автор: Семиврагов Сергей Александрович
