# Project
Проєкт: Менеджер завдань
Мета: Створити консольний додаток, який дозволяє додавати завдання до списку, переглядати поточні завдання та видаляти виконані.C
Code:
def show_menu():
    print("\nМеню:")
    print("1. Додати завдання")
    print("2. Показати всі завдання")
    print("3. Видалити завдання")
    print("4. Вийти")

def add_task(tasks):
    task = input("Введи нове завдання: ")
    tasks.append(task)
    print(f"Завдання '{task}' додано!")

def show_tasks(tasks):
    if not tasks:
        print("Список завдань порожній!")
    else:
        print("\nТвої завдання:")
        for idx, task in enumerate(tasks, 1):
            print(f"{idx}. {task}")

def delete_task(tasks):
    show_tasks(tasks)
    try:
        task_num = int(input("\nВведи номер завдання для видалення: ")) - 1
        if 0 <= task_num < len(tasks):
            removed_task = tasks.pop(task_num)
            print(f"Завдання '{removed_task}' видалено!")
        else:
            print("Невірний номер завдання!")
    except ValueError:
        print("Будь ласка, введи число!")

def main():
    tasks = []
    while True:
        show_menu()
        choice = input("Вибери опцію (1-4): ")

        if choice == '1':
            add_task(tasks)
        elif choice == '2':
            show_tasks(tasks)
        elif choice == '3':
            delete_task(tasks)
        elif choice == '4':
            print("Дякую за користування менеджером завдань! Гарного дня!")
            break
        else:
            print("Невірний вибір, спробуй ще раз!")

if __name__ == '__main__':
    main()
