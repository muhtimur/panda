# 📋 Техническое задание
## Веб-приложение «ЕГЭ-трекер: N дней до экзамена»

---

## 1. Ключевые особенности

- ✅ **Ежедневный чек-ин:** занимался/не занимался сегодня
- ✅ **Детальная статистика по заданиям:** сколько решил задач по каждому номеру (1–27)
- ✅ **GitHub-style тепловая карта:** визуализация активности по дням
- ✅ **Система достижений:** ачивки за прогресс
- ✅ **Поддержка нескольких предметов:** русский язык, математика, обществознание и т.д. (в перспективе)

---

## 2. Функциональные требования

### 2.1. Модуль аутентификации

| ID | Требование | Приоритет |
|----|------------|-----------|
| A1 | Регистрация (имя, email, пароль, класс, выбранные предметы) | Высокий |
| A2 | Вход по email/паролю | Высокий |
| A3 | Редактирование профиля | Средний |

---

### 2.2. Модуль ежедневного учета (главная фича!)

| ID | Требование | Приоритет |
|----|------------|-----------|
| B1 | На дашборде отображается **сегодняшняя карточка** с вопросом: «Занимался ли ты сегодня?» | Высокий |
| B2 | Если «Да» — открывается форма для выбора предмета и заполнения заданий | Высокий |
| B3 | Для каждого предмета — чекбоксы/поля для ввода количества решенных заданий по номерам 1–27 | Высокий |
| B4 | Возможность отметить, какие именно номера заданий были решены (например, 1, 2, 3, 14, 15) | Средний |
| B5 | Возможность добавить заметку о том, что делали | Низкий |
| B6 | Нельзя заполнить прошедший день (только сегодняшний, но с возможностью редактирования) | Средний |

**Пример интерфейса:**
```
┌─────────────────────────────────────────┐
│ 📅 Сегодня, 28 марта 2026               │
│                                         │
│ ❓ Ты занимался сегодня?                 │
│ [✅ Да] [❌ Нет]                         │
└─────────────────────────────────────────┘

(при нажатии "Да" раскрывается:)

┌─────────────────────────────────────────┐
│ 📚 Информатика                │
│ Решенные задания:                       │
│ □ 1  □ 2  □ 3  □ 4  □ 5  □ 6  □ 7  □ 8│
│ □ 9  □ 10 □ 11 □ 12 □ 13 □ 14 □ 15 □ 16│
│ □ 17 □ 18 □ 19 □ 20 □ 21 □ 22 □ 23 □ 24│
│ □ 25 □ 26 □ 27                          │
│                                         │
│ [Сохранить]                             │
└─────────────────────────────────────────┘
```

---

### 2.3. Модуль тепловой карты (GitHub-style)

| ID | Требование | Приоритет |
|----|------------|-----------|
| C1 | Отображение календаря активности за последние недели | Высокий |
| C2 | Каждый день — квадратик, цвет зависит от количества решенных заданий | Высокий |
| C3 | Цветовая шкала: серый (0 задач) → светло-зеленый → темно-зеленый (максимум) | Высокий |
| C4 | При наведении на квадратик — всплывает подсказка: дата, количество решенных заданий по предметам | Высокий |
| C5 | Фильтр по предмету: можно посмотреть тепловую карту только по математике/русскому и т.д. | Средний |

**Визуализация:**
```
      Апр 2026                Май 2026
Пн  ████ ██ ████ ████ ██ ████ ██ ████
Вт  ██ ████ ██ ████ ██ ████ ██ ████ ██
...
(цветные квадратики как на GitHub)
```

---

### 2.4. Модуль статистики и прогресса

| ID | Требование | Приоритет |
|----|------------|-----------|
| D1 | График «Динамика решенных заданий по дням» (линейный) | Высокий |
| D2 | График «Распределение по заданиям» — гистограмма, где видно, какие номера заданий решаются чаще всего | Высокий |
| D3 | Статистика «Всего решено заданий» за всё время | Высокий |
| D4 | Статистика «Текущая серия дней подряд» (streak) | Высокий |
| D5 | Статистика «Лучшая серия» | Средний |
| D6 | Прогресс-бар до экзамена (дней осталось / всего) | Высокий |
| D7 | Таблица «Слабые места» — задания, которые решались меньше всего | Средний |

---

### 2.5. Модуль достижений (ачивки)

| ID | Достижение | Условие получения |
|----|------------|-------------------|
| E1 | 🔥 **Первые шаги** | Первый заполненный день |
| E2 | 🔥 **Неделя силы воли** | Серия 7 дней подряд |
| E3 | 🔥 **Месяц продуктивности** | Серия 30 дней подряд |
| E4 | 💪 **Математический боец** | Решено 100 заданий по математике |
| E5 | 💪 **Русский виртуоз** | Решено 100 заданий по русскому языку |
| E6 | 🎯 **Мастер первой части** | Решены все задания 1–12 хотя бы по разу |
| E7 | 🎯 **Покоритель второй части** | Решено хотя бы одно задание из 13–27 |
| E8 | ⭐ **Первая сотня** | Всего решено 100 заданий |
| E9 | ⭐ **500 задач** | Всего решено 500 заданий |
| E10 | 📚 **Эрудит** | Заполнено 7 дней подряд по 3+ предметам |
| E11 | 🏆 **100 дней до ЕГЭ** | Зарегистрировался за 100 дней до экзамена |

**Требования к модулю:**
- Достижения отображаются на отдельной странице / виджете на дашборде
- При получении достижения — всплывающее уведомление (toast)
- Можно делиться достижением в соцсети (опционально)

---

## 3. Модели данных (обновленные)

```python
# app/models.py

from flask_sqlalchemy import SQLAlchemy
from flask_login import UserMixin
from datetime import datetime, date
import json

db = SQLAlchemy()

class User(UserMixin, db.Model):
    __tablename__ = 'users'
    
    id = db.Column(db.Integer, primary_key=True)
    username = db.Column(db.String(64), unique=True, nullable=False)
    email = db.Column(db.String(120), unique=True, nullable=False)
    password_hash = db.Column(db.String(128), nullable=False)
    class_name = db.Column(db.String(20))
    created_at = db.Column(db.DateTime, default=datetime.utcnow)
    
    # Отношения
    study_days = db.relationship('StudyDay', backref='user', lazy='dynamic', cascade='all, delete-orphan')
    achievements = db.relationship('UserAchievement', backref='user', lazy='dynamic')
    subjects = db.relationship('UserSubject', backref='user', lazy='dynamic', cascade='all, delete-orphan')


class Subject(db.Model):
    """Справочник предметов ЕГЭ"""
    __tablename__ = 'subjects'
    
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(50), unique=True, nullable=False)  # Математика (профиль)
    short_name = db.Column(db.String(20))  # Математика
    icon = db.Column(db.String(50))
    exam_date = db.Column(db.Date)
    color = db.Column(db.String(7), default='#6c757d')
    
    # Количество заданий в ЕГЭ по предмету
    max_tasks = db.Column(db.Integer, default=27)  # для математики — 27, для русского — 27


class UserSubject(db.Model):
    """Предметы, которые выбрал пользователь"""
    __tablename__ = 'user_subjects'
    
    id = db.Column(db.Integer, primary_key=True)
    user_id = db.Column(db.Integer, db.ForeignKey('users.id'), nullable=False)
    subject_id = db.Column(db.Integer, db.ForeignKey('subjects.id'), nullable=False)
    is_active = db.Column(db.Boolean, default=True)
    
    __table_args__ = (db.UniqueConstraint('user_id', 'subject_id', name='unique_user_subject'),)


class StudyDay(db.Model):
    """
    Основная модель — один день подготовки пользователя
    Хранит информацию о том, занимался ли пользователь в этот день
    """
    __tablename__ = 'study_days'
    
    id = db.Column(db.Integer, primary_key=True)
    user_id = db.Column(db.Integer, db.ForeignKey('users.id'), nullable=False)
    date = db.Column(db.Date, default=date.today, nullable=False)
    
    # Флаг: занимался ли пользователь в этот день
    studied = db.Column(db.Boolean, default=False)
    
    # Общая статистика за день
    total_tasks_solved = db.Column(db.Integer, default=0)
    
    # Заметка на день
    note = db.Column(db.Text)
    
    # Дата создания/обновления записи
    updated_at = db.Column(db.DateTime, default=datetime.utcnow, onupdate=datetime.utcnow)
    
    __table_args__ = (db.UniqueConstraint('user_id', 'date', name='unique_user_day'),)


class TaskProgress(db.Model):
    """
    Детальная статистика по каждому заданию в конкретный день
    """
    __tablename__ = 'task_progress'
    
    id = db.Column(db.Integer, primary_key=True)
    study_day_id = db.Column(db.Integer, db.ForeignKey('study_days.id'), nullable=False)
    subject_id = db.Column(db.Integer, db.ForeignKey('subjects.id'), nullable=False)
    
    # Номер задания (от 1 до max_tasks предмета)
    task_number = db.Column(db.Integer, nullable=False)
    
    # Решено или нет (можно решить несколько заданий одного номера в день?)
    # В контексте ЕГЭ обычно "решил задание №X" — бинарно
    solved = db.Column(db.Boolean, default=False)
    
    # Если нужно больше деталей — можно добавить количество
    count = db.Column(db.Integer, default=0)  # сколько раз решил задание №X
    
    __table_args__ = (
        db.UniqueConstraint('study_day_id', 'subject_id', 'task_number', name='unique_day_subject_task'),
    )
    
    study_day = db.relationship('StudyDay')
    subject = db.relationship('Subject')


class Achievement(db.Model):
    """Справочник достижений"""
    __tablename__ = 'achievements'
    
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(100), nullable=False)
    description = db.Column(db.String(200))
    icon = db.Column(db.String(50))  # эмодзи или класс иконки
    condition_type = db.Column(db.String(50))  # 'streak', 'total_tasks', 'subject_tasks', 'task_coverage'
    condition_value = db.Column(db.Integer)
    condition_subject_id = db.Column(db.Integer, db.ForeignKey('subjects.id'), nullable=True)  # для предметных ачивок
    condition_extra = db.Column(db.String(100))  # дополнительные параметры (например, 'task_range:1-12')


class UserAchievement(db.Model):
    __tablename__ = 'user_achievements'
    
    id = db.Column(db.Integer, primary_key=True)
    user_id = db.Column(db.Integer, db.ForeignKey('users.id'), nullable=False)
    achievement_id = db.Column(db.Integer, db.ForeignKey('achievements.id'), nullable=False)
    earned_at = db.Column(db.DateTime, default=datetime.utcnow)
    
    achievement = db.relationship('Achievement')
```

---

## 4. API эндпоинты

| Метод | Эндпоинт | Описание |
|-------|----------|----------|
| GET | `/` | Дашборд с тепловой картой и сегодняшней карточкой |
| GET | `/api/heatmap` | JSON-данные для тепловой карты (цвета по дням) |
| POST | `/api/day/check` | Отметка «занимался/не занимался» |
| POST | `/api/day/tasks` | Сохранение решенных заданий за день |
| GET | `/api/day/<date>` | Получить данные за конкретный день (для редактирования) |
| GET | `/stats` | Страница со статистикой и графиками |
| GET | `/achievements` | Страница с полученными достижениями |
| GET | `/api/achievements/check` | Проверка новых достижений (вызывается после сохранения) |

---

## 5. Алгоритмы для достижений

```python
def check_achievements(user_id):
    """Проверяет и выдает новые достижения пользователю"""
    user = User.query.get(user_id)
    
    # Получаем все достижения, которые еще не получены
    earned_ids = [ua.achievement_id for ua in user.achievements]
    available = Achievement.query.filter(~Achievement.id.in_(earned_ids)).all()
    
    new_achievements = []
    
    for ach in available:
        if ach.condition_type == 'streak':
            # Вычисляем текущую серию дней
            current_streak = calculate_streak(user_id)
            if current_streak >= ach.condition_value:
                new_achievements.append(ach)
        
        elif ach.condition_type == 'total_tasks':
            # Сумма всех решенных заданий за всё время
            total = db.session.query(db.func.sum(StudyDay.total_tasks_solved)).filter_by(user_id=user_id).scalar() or 0
            if total >= ach.condition_value:
                new_achievements.append(ach)
        
        elif ach.condition_type == 'subject_tasks':
            # Решено N заданий по конкретному предмету
            total = db.session.query(db.func.sum(TaskProgress.count))\
                .join(StudyDay)\
                .filter(StudyDay.user_id == user_id, TaskProgress.subject_id == ach.condition_subject_id)\
                .scalar() or 0
            if total >= ach.condition_value:
                new_achievements.append(ach)
        
        elif ach.condition_type == 'task_coverage':
            # Решены все задания из диапазона (например, 1-12)
            subject_id = ach.condition_subject_id
            task_range = ach.condition_extra  # '1-12'
            start, end = map(int, task_range.split('-'))
            
            # Проверяем, решал ли пользователь каждое задание из диапазона хотя бы раз
            solved_tasks = db.session.query(TaskProgress.task_number)\
                .join(StudyDay)\
                .filter(StudyDay.user_id == user_id, TaskProgress.subject_id == subject_id, TaskProgress.solved == True)\
                .distinct()\
                .all()
            solved_numbers = {t[0] for t in solved_tasks}
            
            required = set(range(start, end + 1))
            if required.issubset(solved_numbers):
                new_achievements.append(ach)
    
    # Сохраняем новые достижения
    for ach in new_achievements:
        ua = UserAchievement(user_id=user_id, achievement_id=ach.id)
        db.session.add(ua)
    
    db.session.commit()
    return new_achievements
```

---

## 6. Формула для тепловой карты

```python
def get_heatmap_data(user_id, subject_id=None):
    """
    Возвращает данные для GitHub-style тепловой карты
    Возвращает список дней с количеством решенных заданий
    """
    query = db.session.query(
        StudyDay.date,
        db.func.sum(TaskProgress.count).label('tasks_count')
    ).join(TaskProgress).filter(StudyDay.user_id == user_id)
    
    if subject_id:
        query = query.filter(TaskProgress.subject_id == subject_id)
    
    query = query.group_by(StudyDay.date).order_by(StudyDay.date)
    
    results = query.all()
    
    # Формируем словарь {date: count}
    data = {row.date: row.tasks_count for row in results}
    
    # Цветовая шкала:
    # 0 задач -> серый
    # 1-2 задач -> светло-зеленый
    # 3-5 задач -> зеленый
    # 6-10 задач -> темно-зеленый
    # >10 задач -> очень темно-зеленый
    
    return data
```

---

## 7. Интерфейс (страницы)

### 7.1. Главный дашборд

```
┌─────────────────────────────────────────────────────────────────┐
│  🔥 ЕГЭ-трекер                                    [Имя] ▼      │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  📅 До ЕГЭ по информатике: 64 дня  ████████░░░░░░░░░░░░ 32%     │
│                                                                 │
│  ┌─────────────────────────┐  ┌─────────────────────────────┐  │
│  │ Сегодня, 28 марта      │  │ 🔥 Серия: 12 дней           │  │
│  │                         │  │ 📊 Всего заданий: 347       │  │
│  │ ❓ Ты занимался?        │  │ 🏆 Достижений: 5/11         │  │
│  │ [✅ Да]  [❌ Нет]        │  └─────────────────────────────┘  │
│  └─────────────────────────┘                                   │
│                                                                 │
│  📊 Активность (GitHub-style)                                   │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │   Март 2026                                              │   │
│  │ Пн ██ ████ ██ ████ ██ ████ ██ ████ ██ ████ ██ ████     │   │
│  │ Вт ██ ████ ██ ████ ██ ████ ██ ████ ██ ████ ██ ████     │   │
│  │ ...                                                     │   │
│  │               ░ <1   ▓ 1-2  ▓▓ 3-5  ▓▓▓ 6-10  █ >10    │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  📚 Последние занятия                                          │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ 27 мар — Математика: задания 1,2,3,4,5,12,13 (7 шт)    │   │
│  │ 26 мар — Русский: задания 8,9,10,11,12 (5 шт)          │   │
│  │ 25 мар — Математика: задания 1,2,3,4 (4 шт)            │   │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
```

---

## 8. План реализации (по этапам)

| Этап | Задачи | Примерное время |
|------|--------|-----------------|
| **1** | Настройка Flask, базы данных, моделей |
| **2** | Аутентификация (регистрация, вход, профиль) |
| **3** | Ядро: ежедневный чек-ин и форма заданий |
| **4** | Тепловая карта (GitHub-style) |
| **5** | Система достижений (логика и UI) |
| **6** | Статистика и графики (Chart.js) |
| **7** | UI/UX, адаптивность (Bootstrap) |
| **8** | Тестирование, деплой (PythonAnywhere/Render) |


---

## 9. Вопросы для уточнения

1. **Какие предметы поддерживать?** Начнете с одного (например, математика) или сразу несколько?
2. **Задания 1–27** — для математики это актуально. Для русского тоже 27 заданий? Или для других предметов своя нумерация?
3. **Множественные решения** — можно ли решить задание №5 три раза за день? Или достаточно отметить один раз, что «решил»?
4. **Тепловая карта** — показывать только дни с занятиями или все дни (с пустыми квадратиками как в GitHub)?

---


Просто скажите, с какого этапа начинаем! 🚀
