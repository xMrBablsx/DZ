'''Реализовать прототип консольной программы - проводника, для работы с файлами.
Создать функции создания, удаления, перемещения, копирования(файла, папки) с использованием системы контроля версий git.
Зарегистрироваться на Github и выгрузить с помощью git программу в созданный репозиторий.
Прикрепить ссылку на репозиторий'''

import os
import shutil


def display_menu():
    # Выводит меню с доступными действиями
    print("1. Просмотреть текущий каталог")
    print("2. Создать файл")
    print("3. Создать папку")
    print("4. Удалить файл или папку")
    print("5. Переместить файл или папку")
    print("6. Копировать файл или папку")
    print("0. Выйти")


def show_current_directory():
    # Выводит текущий рабочий каталог
    current_directory = os.getcwd()                 # Получаем путь к текущему рабочему каталогу
    print(f"Текущий каталог: {current_directory}")  # Выводим сообщение с текущим каталогом


def create_file():
    # Создает новый файл
    file_name = input("Введите имя файла: ")  # Запрашиваем у пользователя имя файла
    try:
        with open(file_name, 'w') as file:
            # Открываем файл для записи ('w'), создавая его, если он не существует, и очищаем его содержимое
            print(f"Файл {file_name} создан успешно.")
    except Exception as e:
        # Если происходит ошибка при создании файла, выводим сообщение об ошибке
        print(f"Ошибка при создании файла: {e}")


def create_folder():
    # Создает новую папку
    folder_name = input("Введите имя папки: ")          # Запрашиваем у пользователя имя новой папки
    try:
        os.mkdir(folder_name)                           # Создаем новую папку с указанным именем
        print(f"Папка {folder_name} создана успешно.")  # Выводим сообщение об успешном создании папки
    except Exception as e:
        # Если происходит ошибка при создании папки, выводим сообщение об ошибке
        print(f"Ошибка при создании папки: {e}")


def delete_file_or_folder():
    # Удаляет файл или папку
    target_name = input("Введите имя файла или папки для удаления: ")  # Запрашиваем у пользователя имя файла или папки
    try:
        if os.path.isfile(target_name):
            # Если указанный путь - это файл, то используем функцию os.remove для его удаления
            os.remove(target_name)
            print(f"Файл {target_name} удален успешно.")
        elif os.path.isdir(target_name):
            # Если указанный путь - это папка, то используем функцию shutil.rmtree для удаления папки и её содержимого
            shutil.rmtree(target_name)
            print(f"Папка {target_name} удалена успешно.")
        else:
            # Если путь не соответствует ни файлу, ни папке, выводим сообщение о том, что указанный объект не найден
            print(f"{target_name} не найден.")
    except Exception as e:
        # Если происходит ошибка при удалении файла или папки, выводим сообщение об ошибке
        print(f"Ошибка при удалении: {e}")


def move_file_or_folder():
    # Перемещает файл или папку
    source_name = input("Введите имя файла или папки: ")        # Запрашиваем у пользователя имя файла или папки
    destination_name = input("Введите путь для перемещения: ")  # Запрашиваем у пользователя путь для перемещения

    try:
        shutil.move(source_name, destination_name)  # Используем функцию shutil.move для перемещения файла или папки
        print(f"{source_name} перемещен в {destination_name} успешно.")
    except Exception as e:
        # Если происходит ошибка при перемещении, выводим сообщение об ошибке
        print(f"Ошибка при перемещении: {e}")


def copy_file_or_folder():
    # Копирует файл или папку
    source_name = input("Введите имя файла или папки: ")        # Запрашиваем у пользователя имя файла или папки
    destination_name = input("Введите путь для копирования: ")  # Запрашиваем у пользователя путь для копирования

    try:
        if os.path.isfile(source_name):
            # Если исходный объект - файл, используем shutil.copy2 для копирования файла
            shutil.copy2(source_name, destination_name)
            print(f"Файл {source_name} скопирован в {destination_name} успешно.")
        elif os.path.isdir(source_name):
            # Если исходный объект - папка, используем shutil.copytree для копирования папки
            shutil.copytree(source_name, os.path.join(destination_name, os.path.basename(source_name)))
            print(f"Папка {source_name} скопирована в {destination_name} успешно.")
        else:
            print(f"{source_name} не найден.")
    except Exception as e:
        # Если происходит ошибка при копировании, выводим сообщение об ошибке
        print(f"Ошибка при копировании: {e}")


if __name__ == "__main__":
    while True:
        display_menu()
        choice = input("Выберите действие: ")

        if choice == "1":
            show_current_directory()
        elif choice == "2":
            create_file()
        elif choice == "3":
            create_folder()
        elif choice == "4":
            delete_file_or_folder()
        elif choice == "5":
            move_file_or_folder()
        elif choice == "6":
            copy_file_or_folder()
        elif choice == "0":
            break
        else:
            print("Некорректный ввод. Попробуйте снова.")
