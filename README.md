# Import the DoublyLinkedList class from the provided doubly_linked_list.py file
from doubly_linked_list import DoublyLinkedList

class UndoRedoList:
    def __init__(self):
        self.undo_stack = DoublyLinkedList()
        self.redo_stack = DoublyLinkedList()
        self.current_state = DoublyLinkedList()

# Create initial list with values [5,3,2,1,4,8]
    for val in [5,3,2,1,4,8]:
        self.current_state.append(val)

    def do(self, operation):
# Add current state to undo stack
        self.undo_stack.append(self.current_state)

if operation == "sort":
    # Sort the list
    self.current_state.sort()
elif operation == "reverse":
    # Reverse the list
    self.current_state.reverse()
elif operation == "add":
    # Add a 9 to the end of the list
    self.current_state.append(9)

    # Clear redo stack
    self.redo_stack = DoublyLinkedList()

    # Print current state
    print("Current state: ", self.current_state)

    def undo(self):
        if self.undo_stack.length() > 0:
   # Move current state to redo stack
           self.redo_stack.append(self.current_state)

  # Pop previous state from undo stack and set as current state
           self.current_state = self.undo_stack.pop()
  # Print current state
    print("Current state: ", self.current_state)
else:
    print("Cannot undo further")

def redo(self):
    if self.redo_stack.length() > 0:
        # Move current state to undo stack
        self.undo_stack.append(self.current_state)
        # Pop next state from redo stack and set as current state
        self.current_state = self.redo_stack.pop()
        # Print current state
        print("Current state: ", self.current_state)
    else:
        print("Cannot redo further")


# Create an instance of UndoRedoList and test the methods
my_list = UndoRedoList()
my_list.do("sort")
my_list.do("reverse")
my_list.do("add")
my_list.undo()
my_list.do("add")
my_list.undo()
my_list.undo()
my_list.redo()
my_list.redo()
my_list.redo()


# Palindrome checker using a stack
def is_palindrome(word):
    stack = []


# Add each letter of the word to the stack
for letter in word:
    stack.append(letter)
# Pop each letter from the stack and compare to the original word
for letter in word:
    if letter != stack.pop():
        return False

return True



# Open and read the file
with open("palindrome.txt", "r") as file:
    # Create an empty list to store palindromes
    palindromes = []

# Read each line of the file
for line in file:
    # Strip the newline character
    line = line.strip()

    # Check if the line is a palindrome
    if is_palindrome(line):
        palindromes.append(line)

# Print the list of palindromes
print("Palindromes: ", palindromes)