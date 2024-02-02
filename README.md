# cdiff

Supported OS
The application has been tested on Windows and Linux, but it should also work on other POSIX-compliant operating systems, such as macOS and FreeBSD.

Supported compilers
The following compilers are recommended for building the project: GCC, Clang and MinGW. While Microsoft Visual C++ is also supported, Makefile for building with MSVC is not provided.

For users who want to build the project with MSVC, there are two options available:

Create a new C++ project in Visual Studio and add all files from src folder (recommended).
Write a Makefile specifically for MSVC (advanced).
Step-by-step instructions
Install the necessary tools
The following examples show how to install GCC and make on a few popular Linux distributions.

Debian, Ubuntu

sudo apt update
sudo apt install build-essential
Fedora

sudo dnf update
sudo dnf install make automake gcc gcc-c++
Arch Linux

sudo pacman -Syu
sudo pacman -S base-devel
MinGW is needed to build C and C++ projects on Windows. The official website has numerous versions for various systems.

winlibs.com hosts standalone builds for Windows, as well as installation instructions. Building the project on Windows systems was tested with the following flavor of MinGW:

Win32 - i686 (32-bit)
Threading library: POSIX
Runtime library: MSVCRT
Clone the repository:

git clone https://github.com/y-govor/cdiff.git
cd cdiff
Create the bin directory:

mkdir bin
Use make utility to build the project:

make
To compile with Clang instead of GCC, open the Makefile and replace the line CXX = g++ with CXX = clang++. Alternatively, specify the value for CXX variable in the command:

make CXX=clang++
Note for MinGW users: you might need to use mingw32-make instead of make.

Usage
Usage: cdiff [options] [files]

Description:
  Compare two files and display the difference.

Options:
  -h, --help                    Display this help message and exit.
  -c, --color                   Enable color support when printing to console.
  -a, --force-ansi              Use ANSI escape codes for colors on Windows systems.
  -o, --out-file FILE           Redirect output to the file instead of a console.
  -n, --lines NUM               Number of lines for context (3 by default).

Files:
  original                      Original file.
  modified                      New (modified) file.

Examples:
  cdiff original.txt modified.txt
  cdiff -c -a original.txt modified.txt
  cdiff -o output.diff -n 5 original.txt modified.txt


#cdiff
Простая консольная утилита для вычисления разницы между двумя файлами, написанная на C++.

Сборка
Поддерживаемые ОС
Приложение было протестировано на Windows и Linux, но оно должно работать и на других POSIX-совместимых операционных системах, таких как macOS и FreeBSD.

Поддерживаемые компиляторы
Для сборки проекта рекомендуются следующие компиляторы: GCC, Clang и MinGW. Хотя Microsoft Visual C++ также поддерживается, Makefile для сборки с MSVC не предоставляется.

Для пользователей, которые хотят собрать проект с помощью MSVC, есть два варианта:

Создать новый проект C++ в Visual Studio и добавить все файлы из папки src (рекомендуется).
Написать Makefile специально для MSVC (расширенный вариант):
Создать новый проект C++ в Visual Studio и добавить все файлы из папки src (рекомендуется).
Написать Makefile специально для MSVC (расширенный вариант).
Пошаговые инструкции
Установите необходимые инструменты
В следующих примерах показано, как установить GCC и make на несколько популярных дистрибутивов Linux.

Debian, Ubuntu

sudo apt update
sudo apt install build-essential
Fedora

sudo dnf update
sudo dnf install make automake gcc gcc-c++
Arch Linux

sudo pacman -Syu
sudo pacman -S base-devel
MinGW необходим для сборки проектов на C и C++ под Windows. На официальном сайте представлено множество версий для различных систем.

На сайте winlibs.com размещены автономные сборки для Windows, а также инструкции по установке. Сборка проекта на Windows-системах была протестирована со следующей версией MinGW:

Win32 - i686 (32-bit)
Библиотека Threading: POSIX
Библиотека времени выполнения: MSVCRT
Клонируйте репозиторий:

git clone https://github.com/y-govor/cdiff.git
cd cdiff
Создайте каталог bin:

mkdir bin
Используйте утилиту make для сборки проекта:

make
Чтобы скомпилировать с помощью Clang вместо GCC, откройте Makefile и замените строку CXX = g++ на CXX = clang++. Или же укажите значение переменной CXX в команде:

make CXX=clang++
Примечание для пользователей MinGW: вам может понадобиться использовать mingw32-make вместо make.

Использование
Использование: cdiff [options] [files]

Описание:
  Сравнивает два файла и отображает разницу.


Опции:
  -h, --help Вывести сообщение о помощи и выйти.  -c, --color Включить поддержку цветов при печати на консоль.
  -a, --force-ansi Использовать аварийные коды ANSI для цветов в системах Windows.
  -o, --out-file FILE Перенаправить вывод в файл вместо консоли.  -n, --lines NUM Количество строк для контекста (по умолчанию 3).Файлы:  original Оригинальный файл.
  modified Новый (измененный) файл.

Примеры:
  cdiff original.txt modified.txtcdiff -c -a original.txt modified.txtcdiff -o output.diff -n 5 original.txt modified.txt
