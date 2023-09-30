# Lab01AI
Lab 01 Artificial Intelligence

#Lab  1
#Task 2

#Create three variables representing your name, age, and favorite color. Print a message using these
variables.

name = "Muhammad Akram"
age = 22   
favorite_color = "Black"

# Print a message using the variables
print(f"Hello, my name is {name}. I am {age} years old, and my favorite color is {favorite_color}.")

#Ask the user for their name and then print a personalized greeting
# Ask the user for their name
user_name = input("What is your name? ")

# Print a personalized greeting
print(f"Hello, {user_name}! Welcome.")

#Create a string containing your favorite quote. Print the quote and its length
# Define the favorite quote
favorite_quote = " See the bad inside yourself, and see the good inside others"

# Print the quote
print("Favorite Quote:")
print(favorite_quote)

# Print the length of the quote
quote_length = len(favorite_quote)
print(f"\nLength of the Quote: {quote_length} characters")

#Create a list of your favorite fruits. Print the list and the total number of fruits
# Define a list of favorite fruits
favorite_fruits = ["Apple", "Banana", "Orange", "Strawberry", "Grapes"]

# Print the list of favorite fruits
print("Favorite Fruits:")
for fruit in favorite_fruits:
    print(f"- {fruit}")

# Print the total number of fruits
total_fruits = len(favorite_fruits)
print(f"\nTotal Number of Fruits: {total_fruits}")

#Create a dictionary representing a person's information (name, age, and city). Print the dictionary
# Create a dictionary representing a person's information
person_info = {
    "name": "Muhammad Akram",
    "age": 22,
    "city": "Islamabad"
}

# Print the dictionary
print("Person's Information:")
print(person_info)

#Ask the user for their age and check if they are eligible to vote (age 18 or older). Print the eligibility
status.
# Ask the user for their age
user_age = input("Please enter your age: ")

# Convert the input to an integer
user_age = int(user_age)

# Check eligibility to vote
if user_age >= 18:
    print("You are eligible to vote!")
else:
    print("Sorry, you are not eligible to vote yet.")

#Ask the user to guess a number between 1 and 10. Keep prompting them until they guess correctly.
# Generate a random number between 1 and 10 for the user to guess
import random
correct_number = random.randint(1, 10)

# Initialize a variable to store the user's guess
user_guess = 0

# Keep prompting the user until they guess correctly
while user_guess != correct_number:
    # Ask the user to guess a number
    user_guess = int(input("Guess a number between 1 and 10: "))

    # Check if the guess is correct
    if user_guess == correct_number:
        print("Congratulations! You guessed the correct number.")
    else:
        print("Incorrect. Try again!")

# End of the loop

#. Create a function that calculates the area of a rectangle given its length and width. Ask the user
for the values and print the area
# Define the function to calculate the area of a rectangle
def calculate_rectangle_area(length, width):
    return length * width

# Ask the user for the length and width
length = float(input("Enter the length of the rectangle: "))
width = float(input("Enter the width of the rectangle: "))

# Calculate the area using the function
area = calculate_rectangle_area(length, width)

# Print the area
print(f"The area of the rectangle is: {area}")

#Create a command-line To-Do List application that allows users to add tasks, view tasks, mark
tasks as completed, and delete tasks.

a. Requirements:

i. Allow users to add tasks with descriptions.

ii. Display a list of tasks with their statuses (completed or not completed).

iii. Allow users to mark tasks as completed.

iv. Allow users to delete tasks.

v. Provide a menu for users to choose actions (add, view, mark, delete, exit).


class ToDoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, description):
        self.tasks.append({"description": description, "completed": False})
        print(f'Task "{description}" added successfully.')

    def view_tasks(self):
        print("\n--- To-Do List ---")
        for index, task in enumerate(self.tasks, start=1):
            status = "Completed" if task["completed"] else "Not Completed"
            print(f"{index}. {task['description']} - {status}")
        print("------------------")

    def mark_task_completed(self, task_index):
        if 1 <= task_index <= len(self.tasks):
            self.tasks[task_index - 1]["completed"] = True
            print(f'Task "{self.tasks[task_index - 1]["description"]}" marked as completed.')
        else:
            print("Invalid task index.")

    def delete_task(self, task_index):
        if 1 <= task_index <= len(self.tasks):
            deleted_task = self.tasks.pop(task_index - 1)
            print(f'Task "{deleted_task["description"]}" deleted.')
        else:
            print("Invalid task index.")

def main():
    to_do_list = ToDoList()

    while True:
        print("\n--- Menu ---")
        print("1. Add Task")
        print("2. View Tasks")
        print("3. Mark Task as Completed")
        print("4. Delete Task")
        print("5. Exit")

        choice = input("Enter your choice (1-5): ")

        if choice == "1":
            description = input("Enter task description: ")
            to_do_list.add_task(description)
        elif choice == "2":
            to_do_list.view_tasks()
        elif choice == "3":
            task_index = int(input("Enter the index of the task to mark as completed: "))
            to_do_list.mark_task_completed(task_index)
        elif choice == "4":
            task_index = int(input("Enter the index of the task to delete: "))
            to_do_list.delete_task(task_index)
        elif choice == "5":
            print("Exiting the To-Do List application. Goodbye!")
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 5.")

if __name__ == "__main__":
    main()

