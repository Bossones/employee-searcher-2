# Задача: Анализ данных о сотрудниках компании

### Описание:

Вам необходимо разработать консольное Java-приложение, которое будет работать с данными о сотрудниках компании. Данные хранятся в CSV-файле и включают следующие поля:

- Идентификатор сотрудника (ID)
- Имя
- Фамилия
- Электронная почта
- Возраст
- Департамент

---

### Требования:

1. Чтение данных из файла:
    - Приложение должно прочитать данные из CSV-файла (__employees.csv__). Файл находится в той же директории, что и программа.

2. Валидация прочитанных данных:
    - Убедитесь, что все поля заполнены для каждого сотрудника.
    - Проверьте, что поле "Возраст" содержит положительное целое число от 18 до 150.
    - Проверьте, что поле "Электронная почта" имеет действительный формат some@mail.ru

3. Преобразование данных:
    - Преобразуйте все имена и фамилии сотрудников в заглавные буквы.
    - Добавьте новый столбец с полным именем сотрудника в формате "Имя Фамилия 'email:' Электронная почта".

4. Поиск данных по параметрам, передаваемым в коносли:
    - В консоле должны отображаться 3 опции:
      - Найти по фильтрам (Далее пользователь вводит фильтры.)
      - Получить данные всех пользователей (Выполняется загрузка данных, преобразование, группировка, запись в файлы)
      - Выход (Завершение работы приложения)
    - Пользователь может искать сотрудников по имени или фамилии или идентификатору. Фильтры по имени или фамилии должны искать по вхождению строки. Идентификатор - точное совпадение.
    - Программа должна поддерживать ввод фильтров через командную строку в стандарном потоке ввода, например:


      Введите фильтры в формате: <filterType> <value>
      name иван

Или

      Введите фильтры в формате: <filterType> <value>
      surname иван

Или

      Введите фильтры в формате: <filterType> <value>
      id someGUID

Или комбинация

      Введите фильтры в формате: <filterType> <value>
      surname иван name иван

Нет необходимости выполнять выполнять фильтры вида:

      Введите фильтры в формате: <filterType> <value>
      surname иван surname петр
      ----
      Введите фильтры в формате: <filterType> <value>
      id someGUID1 id someGUID2



5. Вывод преобразованных данных в файл:
    - Все преобразованные и отфильтрованные по запросу данные должны быть записаны в новый CSV-файл (__filtered_employees.csv__).
    - Все преобразованные и отфильтрованные по запросу данные должны быть сгруппированы по полю __department__ и записаны в свои файлы (__filtered_employees_IT.csv__, __filtered_employees_Marketing.csv__ и т.д.)
    - Данные, не прошедшие валидацию при запросе, должны быть записаны в новый CSV-файл (__filtered_not_valid_employees.csv__)

---

### Пример формата CSV:

      ID,Имя,Фамилия,Электронная почта,Возраст,Департамент
      f47ac10b-58cc-4372-a567-0e02b2c3d479,иван,иванов,ivan.ivanov@mail.com,29,IT
      c9bf9e57-1685-4c89-bafb-ff5af830be8a,Петр,петров,petrovg@corporate.org,-10,HR
      b4c0a912-fb62-4fa3-ab8f-24d7e032d0d9,светлана,сидорова,svetlana.s@infomarket.net,40,Marketing


Убедитесь, что программа корректно обрабатывает все условия задачи, сообщает об ошибках валидации и выводит информативные сообщения для пользователя.
