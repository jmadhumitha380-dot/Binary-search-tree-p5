# Binary-search-tree-p5
Practice program
class Node:
    def __init__(self, roll, name):
        self.roll = roll
        self.name = name
        self.left = None
        self.right = None
def insert(root, roll, name):
    if root is None:
        return Node(roll, name)
    if roll < root.roll:
        root.left = insert(root.left, roll, name)
    else:
        root.right = insert(root.right, roll, name)
    return root
def search(root, roll):
    if root is None:
        return None
    if root.roll == roll:
        return root
    if roll < root.roll:
        return search(root.left, roll)
    else:
        return search(root.right, roll)
# Main Program
root = None
root = insert(root, 103, "Ravi")
root = insert(root, 101, "Anu")
root = insert(root, 105, "Kumar")
root = insert(root, 102, "Meena")
roll_no = 105
result = search(root, roll_no)
if result:
    print("Student Found")
    print("Roll No:", result.roll)
    print("Name:", result.name)
else:
    print("Student Not Found")

  Output:
  Output:

Student Found
Roll No: 105
Name: Kumar
