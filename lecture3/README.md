# Условные переходы. Циклы.

- [Слайды](https://docs.google.com/presentation/d/1xhGBAFwGLSKRS-0w6UN-2Opv73r_B3t7WI-N7qnMRR4/edit?usp=sharing)
- [Запись лекции](https://www.youtube.com/watch?v=RYSv68V8U-Q)

## Домашка

1. **Вывод чисел на экран (300)**

   Вывести массив чисел на экран.

   Подсказка: Попробуйте вывести на экран символ `'0'`. Чему на самом деле равен символ нуля?
   https://man7.org/linux/man-pages/man7/ascii.7.html

    ```assembly
    global _start

    section .text

    _start:
        jmp _exit
    _exit:
        mov     eax, 1
        mov     ebx, 0
        int     0x80

    section .data
        num_array db 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
    ```
    
    __Ожидаемый формат ответа:__ Текст готовой программы.

2. **Поиск максимального элемента (400)**

    Программа должна выводить на экран индекс максимального элемента.

    Если максимальных элементов несколько(они равны), то выводится индекс первого встретевшегося.
    
    Длина массива не должна превышать 10.

    ```assembly
    global _start

    section .text

    _start:
        jmp _exit
    _exit:
        mov     eax, 1
        mov     ebx, 0
        int     0x80

    section .data
        num_array db 32, 1, 56, 1997, 8, 0, 107, 34, 56, 1997
    ```

   __Ожидаемый формат ответа:__ Текст готовой программы. 

