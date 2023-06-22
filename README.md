# defpolinome

Функция подбора коэффициентов полиномиальной модели сохраняемая в БД

Для развертывания и запуска проекта нужно:
1) В главный файл - "migration_DB", нужно скопировать функцию из файла "function" и вставить в файл "migration_DB"(место куда нужно вставить указано комментарием), либо импортировать функцию polynomial_regression из модуля "function"
2) Нужно записать входные значения для функции: вектор значений признака, вектор целевых значений, степень числа и вызвать функцию save_execution_result, которая подбирает коэффициенты полиномиальной модели на Python, и факт запуска функции сохраняет в БД PostgreSQL, и создает таблицу function_runs(если она не создана).

 
Функция сохраняет следующие данные: Дата запуска, Название функции, Аргументы функции, Результат функции (если успешно), вектор параметров, выходной параметр функций (предсказанные значения), Текст ошибки функции (если неуспешно)


# Пример использования
x = np.array([13, 66, -3, -99, 22, 38, 57, -85, -92, 85])  # Вектор значений признака
y = np.array([27, 6, 72, 4, 7, -86, -10, 24, -14, -92])  # Вектор целевых значений

degree = 3  # степень полинома

save_execution_result(x, y, degree) # Пример вызова функции
