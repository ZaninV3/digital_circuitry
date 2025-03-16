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

    См. `Scheffer.ms11`
   
    Черновик просчета формулы
    ![draft](https://github.com/user-attachments/assets/23ac671c-471a-4d82-b874-130bedd3c003)
3) Привести функцию к базису Пирса и построить схему ее реализации в этом базисе
   
    Базис Пирса использует только операцию "ИЛИ-НЕ" (обозначается $\downarrow$) Преобразуем минимизированную функцию в базис Пирса.

   ### Шаг 1: Преобразование

    * Используем тождества:

    НЕ: $\overline{A} = A \downarrow A$

    И: $AB = (A \downarrow A) \downarrow (B \downarrow B)$
   
    ИЛИ : $A + B = (A \downarrow B) \downarrow (A \downarrow B)$

    * Для формулы:

    $$F = \overline{X_1 X_2} X_3 + \overline{X_1} X_2 \overline{X_3} + X_1 X_2 X_3$$

    * Результат:

    $$F=(R \downarrow R) \downarrow (V_3 \downarrow V_3)$$
   
    * Где:
        * $R = (V_1 \downarrow V_2) \downarrow (V_1 \downarrow V_2)$
        * $V_1 = (F_4 \downarrow F_4) \downarrow (X_3 \downarrow X_3)$
        * $V_2 = (F_5 \downarrow F_5) \downarrow (F_3 \downarrow F_3)$
        * $V_3 = (F_6 \downarrow F_6) \downarrow (X_3 \downarrow X_3)$
        * $F_1 = X_1 \downarrow X_1$
        * $F_2 = X_2 \downarrow X_2$
        * $F_3 = X_3 \downarrow X_3$
        * $F_4 = (F_1 \downarrow F_1) \downarrow (F_2 \downarrow F_2)$
        * $F_5 = (F_1 \downarrow F_1) \downarrow (X_2 \downarrow X_2)$
        * $F_6 = (X_1 \downarrow X_1) \downarrow (X_2 \downarrow X_2)$
    
    ### Шаг 2: Построение схемы

    См. `Pierce.ms11`
   
    Черновик просчета формулы
    ![draft2](https://github.com/user-attachments/assets/97457749-3877-4cd2-9453-15d7c77f9ded)
4) Построить схему реализации функции на основе дешифратора

    См. `Decoder.ms11`

5) Построить схему реализации функции на основе универсального логического модуля с использованием мультиплексора 4-1

    См. `Multiplexer.ms11`

    ### Пояснение
    Будем использовать $X_1$ и $X_2$ в качестве управляющих входов.

    * Если $X_1 = 0$ и $X_2 = 0$, то выводим с $D_0$:
        * $0$, при $X_3 = 0$;
        * $1$, при $X_3 = 1$.

    То есть для $D_0$ мы напрямую подключаем $X_3$.
    * Если $X_1 = 0$ и $X_2 = 1$, то выводим с $D_1$:
        * $1$, при $X_3 = 0$;
        * $0$, при $X_3 = 1$.

    Для $D_1$ подключаем $X_3$ через инвертор.
    * Если $X_1 = 1$ и $X_2 = 0$, то выводим с $D_2$:
        * $0$, при $X_3 = 0$;
        * $0$, при $X_3 = 1$.

    Для $D_2$ должен быть всегда $0$.
    * Если $X_1 = 1$ и $X_2 = 1$, то выводим с $D_3$:
        * $0$, при $X_3 = 0$;
        * $1$, при $X_3 = 1$.

    Для $D_3$ подключаем просто $X_3$.

    То есть распиновка следующая:
    $D_0 = X_3$
    $D_1 = \overline{X_3}$;
    $D_2 = 0$;
    $D_3 = X_3$;
    $A = X_2$;
    $B = X_1$;

    ![very cool cat](https://github.com/user-attachments/assets/8a233d22-e6f9-4f3b-a0be-c72c702f3c3c)
