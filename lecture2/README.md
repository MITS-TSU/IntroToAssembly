# История. Арихитектура Intel x86. Первые операции nasm.


- [Слайды](https://docs.google.com/presentation/d/1xhGBAFwGLSKRS-0w6UN-2Opv73r_B3t7WI-N7qnMRR4/edit?usp=sharing)
- [Запись лекции](#)

## Домашка

1. **Теория. Сдвиги (100)**

    Объяснить своими словами что делают следующие операции:

    ```assembly
    shl ah, 1
    shr ah, 1
    rol ah, 1
    ror ah, 1
    ```

    *Для выполнения задания рекоммендуется использовавть отладчик, чтобы своими ручками выяснить что происходит.

    __Ожидаемый формат ответа:__ объяснение своими словами.

2. **Теория. Прыжки (200)**

    Объяснить своими словами что делают следующие операции:

    ```assembly
    jmp label
    je  label
    jl  label
    jle label
    jg  label
    jge label
    ```

    label -  некоторая метка в коде.
    
    *Для выполнения задания рекоммендуется использовавть отладчик, чтобы своими ручками выяснить что происходит.

    __Ожидаемый формат ответа:__ объяснение своими словами.

3. **Запись в файл (300)**

    Модифицировать (дописать) дописать программу с прошлой домашки так, чтобы она записывала строку `Hello world!` в файл с произвольным названием.
    
    ```
    global _start
    section .text

    _start:
        mov     edx, len   
        mov     ecx, hello
        mov     ebx, 1
        mov     eax, 4
        int     0x80
        mov     eax, 1
        mov     ebx, 0
        int     0x80


    section .data
        hello db 'Hello, world!', 0xa
        len   equ $ - hello
    ```

    Алгоритм:
        
        - открыть файл (sys_open) (системное прерывание вернет вам номер файлового дескриптора)
        - записать строку (sys_write)
        - закрыть файл (sys_close)

    Полезные ресурсы:

    1. [Таблица прерываний x64](https://blog.rchapman.org/posts/Linux_System_Call_Table_for_x86_64/)
    2. [Таблица прерывание x86](https://syscalls32.paolostivanin.com/)

    