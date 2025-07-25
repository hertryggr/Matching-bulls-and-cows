# Оптимальный подбор пар "бык–корова" для племенного разведения КРС

**Алгоритм для максимизации генетического потенциала потомства при соблюдении биологических ограничений**

Этот проект решает задачу оптимального подбора пар "корова-бык" с целью:
- Максимизации средней ожидаемой селекционной ценности потомства (EBV)
- Обеспечения генетического разнообразия через максимальный разброс EBV
- Соблюдения ограничений по родству и использованию быков

## Ключевые цели
1. **Максимизация генетического потенциала**  
   Повышение EBV потомства через оптимальный подбор пар
2. **Предотвращение инбридинга**  
   Контроль родства (<5%) для исключения кровосмешения
3. **Оптимальное использование быков**  
   Ограничение нагрузки на быков (≤10% стада)

## Алгоритм работы
Процесс включает 6 ключевых этапов:

### 1. Загрузка и предобработка данных
- Загрузка данных о коровах, быках и родословных
- Визуализация распределения генетических потенциалов (EBV)

### 2. Расчет генетических потенциалов
- Рекурсивный расчет EBV для животных с неизвестными данными
- Использование данных о родителях для точной оценки

### 3. Расчет коэффициентов родства
- Создание словаря родственных связей
- Рекурсивный расчет коэффициента родства с мемоизацией
- Проверка допустимого уровня родства (<5%)

### 4. Формирование допустимых пар
- Генерация всех возможных пар "корова-бык"
- Параллельная проверка родства
- Расчет среднего EBV для потомства

### 5. Жадная оптимизация назначений
- Сортировка пар по убыванию EBV
- Последовательное назначение оптимальных пар
- Контроль нагрузки на быков (не более 10% стада)
- Гарантированное покрытие всех коров

### 6. Экспорт результатов и анализ
- Сохранение оптимальных пар в CSV-файл
- Расчет среднего EBV потомства и дисперсии
- Проверка соблюдения ограничений

