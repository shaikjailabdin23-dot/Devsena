# Devsena
# Student Management System

students = [
    {
        "Roll": "25F81A0514",
        "Name": "S.Devasani",
        "Marks": 780
    }
]

def add_student():
    roll = input("Enter Roll Number: ")
    name = input("Enter Student Name: ")
    marks = float(input("Enter Marks: "))

    student = {
        "Roll": roll,
        "Name": name,
        "Marks": marks
    }

    students.append(student)
    print("Student Added Successfully!\n")


def display_students():
    if len(students) == 0:
        print("No Student Records Found.\n")
    else:
        print("\n------ Student Records ------")
        for s in students:
            print("Roll Number :", s["Roll"])
            print("Name        :", s["Name"])
            print("Marks       :", s["Marks"])
            print("-----------------------------")


def search_student():
    roll = input("Enter Roll Number to Search: ")

    for s in students:
        if s["Roll"] == roll:
            print("\nStudent Found")
            print("Roll Number :", s["Roll"])
            print("Name        :", s["Name"])
            print("Marks       :", s["Marks"])
            return

    print("Student Not Found.\n")


def update_student():
    roll = input("Enter Roll Number to Update: ")

    for s in students:
        if s["Roll"] == roll:
            s["Name"] = input("Enter New Name: ")
            s["Marks"] = float(input("Enter New Marks: "))
            print("Record Updated Successfully!\n")
            return

    print("Student Not Found.\n")


def delete_student():
    roll = input("Enter Roll Number to Delete: ")

    for s in students:
        if s["Roll"] == roll:
            students.remove(s)
            print("Record Deleted Successfully!\n")
            return

    print("Student Not Found.\n")


while True:
    print("\n===== STUDENT MANAGEMENT SYSTEM =====")
    print("1. Add Student")
    print("2. Display Students")
    print("3. Search Student")
    print("4. Update Student")
    print("5. Delete Student")
    print("6. Exit")

    choice = input("Enter Your Choice: ")

    if choice == "1":
        add_student()
    elif choice == "2":
        display_students()
    elif choice == "3":
        search_student()
    elif choice == "4":
        update_student()
    elif choice == "5":
        delete_student()
    elif choice == "6":
        print("Thank You!")
        break
    else:
        print("Invalid Choice! Please Try Again.")
