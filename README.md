# Робот-фармацевт
Учебный пример для курса по кибериммунной разработке
Учебный пример "Робот-фармацевт"
![image](https://github.com/SvPolyanskaya/CyberImmunity/assets/163770686/dba32d39-8329-461a-8010-7a76d741f667)


Краткое описание проектируемой системы

Робот-фармацевт

![image](https://github.com/SvPolyanskaya/CyberImmunity/assets/163770686/be1ae8e9-5c97-4155-b25b-92425a7fb39b)


Продукт - робот-фармацевт, который производит лекарство по индивидуальному рецепту.
Рецепт включает в себя

а) точный состав и количество компонентов, порядок и условия изготовления конечного продукта

б) уникальный идентификатор лекарства, который изготавливается в определённом объёме для индивидуального курса лечения


Особенности:

Робот-фармацевт управляется центральной системой по беспроводному интерфейсу
Робот-фармацевт передаёт состояние в центральную систему
Ключевые ценности, ущербы, неприемлемые события
Ценность	Негативное событие	Оценка ущерба	Комментарий
люди	два разрешающих сигнала в пересекающихся направлениях привели к дтп с пострадавшими	высокий	
скорость движения	из-за неправильной работы светофора образовалась пробка	средний	можно вызвать человека-регулировщика
Контекст
Контекстная диаграмма

Основные функциональные сценарии
Базовый функциональный сценарий

Высокоуровневая архитектура
Высокоуровневая архитектура
Цели и предположения безопасности
Цели безопасности
При любых обстоятельствах загораются только незапрещенные сочетания
Предположения безопасности
физическая безопасность светофора обеспечена
Таблица соотнесения ценностей, неприемлемых событий и целей безопасности
Ценность	Негативное событие	Оценка ущерба	Цель безопасности
люди	два разрешающих сигнала в пересекающихся направлениях привели к дтп с пострадавшими	высокий	1
скорость движения	из-за неправильной работы светофора образовалась пробка	средний	-
Негативные сценарии
НС1

Политика архитектуры
Версия 1
Политика архитектуры

Домен безопасности	Уровень доверия	Оценка сложности и размера домена	Обоснование
1. Связь	недоверенный	MM	при компрометации нарушение ЦБ блокируется проверкой в системе управления
2. Система управления	доверенный, повышающий целостность данных	MM	при компрометации нарушается ЦБ1
3. Управление светодиодами	доверенный	SS	при компрометации нарушается ЦБ1
4. Система диагностики	недоверенный	MM	в худшем случае замедляется время реакции городских служб на поломку светофора, не нарушает ЦБ
Версия 2
Политика архитектуры v2

Домен безопасности	Уровень доверия	Оценка сложности и размера домена	Обоснование
1. Связь	недоверенный	MM	при компрометации нарушение ЦБ блокируется проверкой в системе контроля конфигураций
2. Система управления	недоверенный	MM	при компрометации нарушение ЦБ блокируется проверкой в системе контроля конфигураций
3. Управление светодиодами	доверенный	SS	при компрометации нарушается ЦБ1
4. Система диагностики	недоверенный	MM	в худшем случае замедляется время реакции городских служб на поломку светофора, не нарушает ЦБ
5. Контроль конфигурации	доверенный, повышающий целостность данных	SS	при компрометации нарушается ЦБ1
Прототип системы
