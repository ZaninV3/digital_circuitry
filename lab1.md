# Контрольная работа №1
### Вариант №3

| $X_1$ | $X_3$ | $X_3$ | $F$ |
|:-----:|:-----:|:-----:|:---:|
|0|0|0|0|
|0|0|1|1|
|0|1|0|1|
|0|1|1|0|
|1|0|0|0|
|1|0|1|0|
|1|1|0|0|
|1|1|1|1|

1) Построить СДНФ и минимизировать функцию.

    СДНФ:

    $$F = \overline{X_1 X_2} X_3 + \overline{X_1} X_2 \overline{X_3} + X_1 X_2 X_3$$

    Результат минимизации: 

    $$F = \overline{X_1 X_2} X_3 + \overline{X_1} X_2 \overline{X_3} + X_1 X_2 X_3$$

2) Привести функцию к базису Шеффера и построить схему ее реализации в этом базисе

    Базис Шеффера использует только операцию "И-НЕ" (обозначается $\uparrow$). Преобразуем минимизированную функцию в базис Шеффера.
    
    ### Шаг 1: Преобразование

    * Используем тождества:

    НЕ: $\overline{A} = A \uparrow A$

    И: $AB = (A \uparrow B) \uparrow (A \uparrow B)$
    ИЛИ : $A + B = (A \uparrow A) \uparrow (B \uparrow B)$

    * Для формулы:

    $$F = \overline{X_1 X_2} X_3 + \overline{X_1} X_2 \overline{X_3} + X_1 X_2 X_3$$

    * Результат:

    $$F=(R \uparrow R) \uparrow (V_3 \uparrow V_3)$$
    * Где:
        * $R = (V_1 \uparrow V_1) \uparrow (V_2 \uparrow V_2)$
        * $V_1 = (F_3 \uparrow X_3) \uparrow (F_3 \uparrow X_3)$
        * $V_2 = (F_5 \uparrow F_4) \uparrow (F_5 \uparrow F_4)$
        * $V_3 = (F_6 \uparrow X_3) \uparrow (F_6 \uparrow X_3)$
        * $F_1 = X_1 \uparrow X_1$
        * $F_2 = X_2 \uparrow X_2$
        * $F_3 = (F_1 \uparrow F_2) \uparrow (F_1 \uparrow F_2)$
        * $F_4 = X_3 \uparrow X_3$
        * $F_5 = (F_1 \uparrow X_2) \uparrow (F_1 \uparrow X_2)$
        * $F_6 = (X_1 \uparrow X_2) \uparrow (X_1 \uparrow X_2)$

    ### Шаг 2: Построение схемы

    См. Этот файл
    Здесь будет черновик просчета формулы
