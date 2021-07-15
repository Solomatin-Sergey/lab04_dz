[![Build Status](https://www.travis-ci.com/Solomatin-Sergey/lab04_dz.svg?branch=main)](https://www.travis-ci.com/Solomatin-Sergey/lab04_dz)
# lab04_dz
## Изучение систем непрерывной интеграции на примере сервиса Travis CI    
### Task 
> Вы продолжаете проходить стажировку в "Formatter Inc." (см подробности).

> В прошлый раз ваше задание заключалось в настройке автоматизированной системы CMake.

> Сейчас вам требуется настроить систему непрерывной интеграции для библиотек и приложений, с которыми вы работали в прошлый раз. 

*используйте TravisCI для сборки на операционной системе Linux с использованием компиляторов gcc и clang;

>> загружаем файлы hello_world_application и solver_application, полученные в предыдущей лабораторной работе.

>> создаём .travis.yml, его содержимое:

language: cpp

compiler:
  - clang
  - gcc

script:
- cd solver_application
- cmake .
- make
- cd ..
- cd hello_world_application
- cmake .
- make

addons:
  apt:
    sources:
      - george-edison55-precise-backports
    packages:
      - cmake
      - cmake-data
      - mingw-w64
      
 >> регистрируемся на travis-ci.com, где активируем данную лабу.

>> Travis CI автоматически соберёт и протестирует наши приложения и библиотеки (с результатами можно ознакомиться при нажатии на значок build|passing).



