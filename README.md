# Oluwapelumi Omidiji
# 11/19/2024

def evaluate_sum():
    """
    This function prompts the user to input two numbers, calculates their sum, 
    and then evaluates whether the sum is greater than, less than, or equal to 10.
    """
    # Taking two inputs from the user
    num1 = float(input("Enter the first number: "))  # Convert the first input to float
    num2 = float(input("Enter the second number: "))  # Convert the second input to float
    
    # Calculating the sum of the two numbers
    total = num1 + num2
    
    # Evaluating the sum and providing a message based on the result
    if total > 10:
        print("The sum is greater than 10.")
    elif total < 10:
        print("The sum is less than 10.")
    else:
        print("The sum is equal to 10.")

# Call the function to run the evaluation
evaluate_sum()



# Oluwapelumi Omidiji
# 11/19/2024

def check_for_five(input_list):
    """
    This function checks if the value 5 is present in the input list.
    It prints a message depending on whether 5 is in the list or not.
    """
    # Check if 5 is in the list
    if 5 in input_list:
        print("The value 5 is in the list.")  # If 5 is found, print this message
    else:
        print("The value 5 is not in the list.")  # If 5 is not found, print this message

# Example usage: A list of numbers is provided to check for 5.
my_list = [1, 2, 3, 4, 5, 6]
check_for_five(my_list)  # Function is called with the provided list



# Oluwapelumi Omidiji
# 11/19/2024

class Character:
    """
    The Character class represents a character with a nickname, weapons, and weaknesses.
    It also provides functionality to check whether a character can perform a task based on its requirements and debuffs.
    """
    def __init__(self, nickname, weapons, weaknesses):
        """
        Initializes a new Character instance with a nickname, weapons, and weaknesses.

        Parameters:
        nickname (str): The name or nickname of the character.
        weapons (list): A list of items that the character has as weapons.
        weaknesses (list): A list of weaknesses the character has.
        """
        self.nickname = nickname
        self.weapons = weapons
        self.weaknesses = weaknesses

    def check_task(self, task_requirements, task_debuffs):
        """
        Checks if the character can perform a task based on the required items and debuffs.

        Parameters:
        task_requirements (list): A list of items required to perform the task.
        task_debuffs (list): A list of debuffs (weaknesses) that would prevent the task from being completed.
        """
        # Check if the character has all the required items for the task
        has_items = all(item in self.weapons for item in task_requirements)
        # Check if the character has any debuffs that would prevent completing the task
        has_debuffs = any(debuff in self.weaknesses for debuff in task_debuffs)
        
        # Determine whether the character can perform the task
        if has_items and not has_debuffs:
            print(f"{self.nickname} can perform the task.")  # If all conditions are met
        else:
            print(f"{self.nickname} cannot perform the task.")  # If any condition fails

# Character setup: Create an instance of a character with a nickname, weapons, and weaknesses
player1 = Character('Dragon Slayer', ['pan', 'paper', 'idea', 'rope', 'groceries'], ['slow'])

# Task requirements and debuffs for various tasks
tasks = {
    "Climb a mountain": (['rope', 'coat', 'first aid kit'], ['slow']),  # Task requires rope and has a "slow" debuff
    "Cook a meal": (['pan', 'groceries'], ['small']),  # Task requires pan and groceries, but has a "small" debuff
    "Write a book": (['pen', 'paper', 'idea'], ['confusion'])  # Task requires pen, paper, and idea, with a "confusion" debuff
}

# Check if the character can perform each task
for task, (requirements, debuffs) in tasks.items():
    print(f"Checking task: {task}")
    player1.check_task(requirements, debuffs)  # For each task, call the check_task method

