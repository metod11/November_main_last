# DEPRECATED
See Annushka instead.


# Глобальная минимизация многомерной функции

Пространство поиска заполняется равномерной сеткой, в каждом узле которой вычисляется значение целевой функции. Составляется список кандидатов (k точек, значения целевой функции в которых минимально), а затем из каждого кандидата запускаются три различных алгоритма поиска локального минимума. Возвращается список из k точек, отсортированный по значению функции в них в порядке возрастания. Таким образом, первую точку можно считать глобальным минимумом.

## Виды сеток:
* Sobol
* NiederreiterBaseTwo

## Алгоритмы локальной минимизации:
1. BFGS
2. BFGS2
3. Hessian Free
4. Nesterov
5. DFP
6. DFP2
7. Powell
8. Powell2
9. Powell21
10. Adadelta
11. Adagrad
12. Adam
13. AdaMax
14. AMSGrad
15. Nadam
16. RmsProp

Предусмотрено тестирование методов как отдельное, так и в сравнении друг с другом. Программа тестирования отдельно методов BFGS, Hessian Free, Nesterov, DFP и Powell расположена в директории test-methods.

В основном проекте тестируется глобальная минимизация, задействуя все перечисленные выше методы.

Статус сборки : [![Build Status](https://ci.worldfly.org/buildStatus/icon?job=Minimization-Container/Minimization-main)](https://ci.worldfly.org/job/Minimization-Container/job/Minimization-main/)

## Инструкция по сборке на Windows и *nix

Для сборки требуется:
* GNU Make ( >= 3.81 )
* gcc ( >= 6.4 )

Сборка проекта:

    make

Запуск проекта:

    ./main

## Инструкция по установке необходимых для сборки утилит на Windows

Для установки GCC необходимо:

1. Скачать Cygwin с официального сайта https://cygwin.com/install.html
2. При установке обязательно выбрать следующие опции из раздела Devel(см в левый верхний угол, таблица):
    * gcc-core (в разделе Devel)
    * gcc-g++ (в разделе Devel)
    * make (в разделе Devel)
3. Дождаться окончания установки

GNU Make также можно установить с официального сайта http://gnuwin32.sourceforge.net/packages/make.htm

После установки GCC и GNU Make необходимо добавить пути к папкам bin в переменную окружения PATH. Сделать это можно следующим образом:
1. Запустить cmd
2. Если у Вас, например, пути до папок bin расположены C:\Program Files (x86)\GnuWin32\bin и C:\cygwin64\bin, то ввести следующую команду:
        
        setx path "%PATH%;C:\Program Files (x86)\GnuWin32\bin;C:\cygwin64\bin"
3. Иначе в этой команде необходимо поменять пути на пути в Вашей системе
4. Перезапустить терминал
5. Убедиться, что все успешно установлено, можно при помощи команд:

        gcc -v
        make -v
        
6. В случае, если сборка проекта не состоялась - обратить внимание на наличие в операционной системе программы Octave, 
при её наличии - удалить, переустановить GNU Make заново.
