def display_menu():
    print("   WELCOME TO MY PYTHON MINI TOOLKIT  ")
    print("1. Grade Calculator")
    print("2. To-Do List")
    print("3. Daily Motivation Generator")
    print("4. Exit Program")


def grade_calculator():
    print("\nGRADE CALCULATOR")
    try:
        score1 = float(input("Enter score 1 (0-100): "))
        score2 = float(input("Enter score 2 (0-100): "))
    except ValueError:
        print("Please enter valid numeric scores.")
        return

    total = score1 + score2
    average = total / 2

    if 90 <= average <= 100:
        final_grade = "A"
    elif 80 <= average < 90:
        final_grade = "B"
    elif 70 <= average < 80:
        final_grade = "C"
    elif 60 <= average < 70:
        final_grade = "D"
    else:
        final_grade = "F"

    print("\nResults:")
    print("Total:", total)
    print("Average:", round(average, 2))
    print("Final Grade:", final_grade)


def todo_list():
    print("\nTO-DO LIST")
    tasks = []

    while True:
        task = input("Enter a task to add (or press Enter to finish): ").strip()
        if not task:
            break
        tasks.append(task)

    if tasks:
        print("\nYour to-do list:")
        for index, task in enumerate(tasks, start=1):
            print(f"{index}. {task}")
    else:
        print("No tasks were added.")


def daily_motivation():
    import random

    quotes = [
        "Believe you can and you're halfway there.",
        "Small steps every day lead to big results.",
        "Progress, not perfection.",
        "You are stronger than you think.",
        "Keep going — your future self will thank you."
    ]
    print("\nDAILY MOTIVATION")
    print(random.choice(quotes))

def main():
    while True:
        display_menu()
        user_choice = input("Select a tool to open (1-4): ").strip()

        # Conditional control logic based on user input
        if user_choice == "1":
            grade_calculator()
        elif user_choice == "2":
            todo_list()
        elif user_choice == "3":
            daily_motivation()
        elif user_choice == "4":
            print("\nThank you for using my Python Toolkit!!")
            break  # Exits the loop and closes the application
        else:
            print("Invalid selection. Please type 1, 2, 3, or 4.")

# Standard Python boilerplate to ensure main() runs when file is executed directly
if __name__ == "__main__":
    main()
