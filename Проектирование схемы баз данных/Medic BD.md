
## СLIENT (Клиенты)

| Поле | Тип | Ограничения | Описание |
|------|------|-------------|-----------|
| client_id | INT | PRIMARY KEY AUTO_INCREMENT | ID клиента |
| surname | VARCHAR(100) | NOT NULL | Фамилия |
| first_name | VARCHAR(100) | NOT NULL | Имя |
| middle_name | VARCHAR(100) |  | Отчество |
| birth_date | DATE | NOT NULL | Дата рождения |
| phone | VARCHAR(20) | NOT NULL | Телефон |
| email | VARCHAR(100) | NOT NULL | Email |
| birth_place | VARCHAR(200) | NOT NULL | Место рождения |
| citizenship | VARCHAR(50) | NOT NULL | Гражданство |

## INSURANCE (Страховые компании)

| Поле | Тип | Ограничения | Описание |
|------|------|-------------|-----------|
| insurance_id | INT | PRIMARY KEY AUTO_INCREMENT | ID страховой компании |
| insurance_name | VARCHAR(200) | NOT NULL | Название |
| contact_phone | VARCHAR(20) | NOT NULL | Контактный телефон |
| contact_email | VARCHAR(100) | NOT NULL | Email |

## TECHNICH (Медицинское оборудование)

| Поле | Тип | Ограничения | Описание |
|------|------|-------------|-----------|
| tech_id | INT | PRIMARY KEY AUTO_INCREMENT | ID оборудования |
| tech_name | VARCHAR(150) | NOT NULL | Наименование |
| description | TEXT |  | Характеристики |

## DOCTOR (Врачи)

| Поле | Тип | Ограничения | Описание |
|------|------|-------------|-----------|
| doctor_id | INT | PRIMARY KEY AUTO_INCREMENT | ID врача |
| surname | VARCHAR(100) | NOT NULL | Фамилия |
| first_name | VARCHAR(100) | NOT NULL | Имя |
| specialization | VARCHAR(150) |  | Специализация |
| license_number | VARCHAR(50) | NOT NULL | Номер лицензии |

## POLIS (Полисы)

| Поле | Тип | Ограничения | Описание |
|------|------|-------------|-----------|
| polis_id | INT | PRIMARY KEY AUTO_INCREMENT | ID полиса |
| polis_number | VARCHAR(50) | NOT NULL | Номер полиса |
| issue_date | DATE | NOT NULL | Дата выдачи |
| expiry_date | DATE | NOT NULL | Дата окончания |
| status | VARCHAR(20) |  | Статус |
| client_id | INT | FOREIGN KEY REFERENCES KLIENT(client_id) | ID клиента |

## POLIS_INSURANCE (Связь полис-страховая компания)

| Поле | Тип | Ограничения | Описание |
|------|------|-------------|-----------|
| polis_id | INT | PRIMARY KEY, FOREIGN KEY REFERENCES POLIS(polis_id) | ID полиса |
| insurance_id | INT | PRIMARY KEY, FOREIGN KEY REFERENCES INSURANCE(insurance_id) | ID страховой компании |

## POLIS_TECHNICH (Связь полис-оборудование)

| Поле | Тип | Ограничения | Описание |
|------|------|-------------|-----------|
| polis_id | INT | PRIMARY KEY, FOREIGN KEY REFERENCES POLIS(polis_id) | ID полиса |
| tech_id | INT | PRIMARY KEY, FOREIGN KEY REFERENCES TECHNICH(tech_id) | ID оборудования |

## POLIS_DOCTOR (Связь полис-врач)

| Поле | Тип | Ограничения | Описание |
|------|------|-------------|-----------|
| polis_id | INT | PRIMARY KEY, FOREIGN KEY REFERENCES POLIS(polis_id) | ID полиса |
| doctor_id | INT | PRIMARY KEY, FOREIGN KEY REFERENCES VRACH(doctor_id) | ID врача |
