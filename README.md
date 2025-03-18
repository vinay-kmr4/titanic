# titanic

# Import NumPy library
import numpy as np

# Basic arithmetic operations using NumPy
def add(a, b):
    return np.add(a, b)

def subtract(a, b):
    return np.subtract(a, b)

def multiply(a, b):
    return np.multiply(a, b)

def divide(a, b):
    try:
        return np.divide(a, b)
    except ZeroDivisionError:
        return "Error! Division by zero."


# Trigonometric operations using NumPy
def sine(angle):
    return np.sin(np.radians(angle))

def cosine(angle):
    return np.cos(np.radians(angle))

def tangent(angle):
    return np.tan(np.radians(angle))


# Logarithm and exponent functions
def logarithm(value, base=10):
    return np.log10(value) if base == 10 else np.log(value)

def exponent(value):
    return np.exp(value)

def power(base, exp):
    return np.power(base, exp)


# Matrix operations using NumPy
def matrix_add(matrix1, matrix2):
    return np.add(matrix1, matrix2)

def matrix_multiply(matrix1, matrix2):
    return np.dot(matrix1, matrix2)

def matrix_transpose(matrix):
    return np.transpose(matrix)

def matrix_determinant(matrix):
    return np.linalg.det(matrix)


# Main menu for calculator
def main_menu():
    print("📚 NumPy-Based Scientific Calculator 📚")
    print("1. Basic Operations (+, -, *, /)")
    print("2. Trigonometric Functions (sin, cos, tan)")
    print("3. Logarithm & Exponent (log, exp, power)")
    print("4. Matrix Operations")
    print("5. Exit")

while True:
    main_menu()
    choice = int(input("Enter your choice (1-5): "))

    if choice == 1:
        a = float(input("Enter first number: "))
        b = float(input("Enter second number: "))
        op = input("Choose operation (+, -, *, /): ")

        if op == "+":
            print("Result:", add(a, b))
        elif op == "-":
            print("Result:", subtract(a, b))
        elif op == "*":
            print("Result:", multiply(a, b))
        elif op == "/":
            print("Result:", divide(a, b))
        else:
            print("Invalid operation!")

    elif choice == 2:
        angle = float(input("Enter angle in degrees: "))
        trig_op = input("Choose operation (sin, cos, tan): ")

        if trig_op == "sin":
            print("Result:", sine(angle))
        elif trig_op == "cos":
            print("Result:", cosine(angle))
        elif trig_op == "tan":
            print("Result:", tangent(angle))
        else:
            print("Invalid operation!")

    elif choice == 3:
        value = float(input("Enter the value: "))
        log_exp_op = input("Choose operation (log, exp, power): ")

        if log_exp_op == "log":
            base = int(input("Enter base (default=10): "))
            print("Result:", logarithm(value, base))
        elif log_exp_op == "exp":
            print("Result:", exponent(value))
        elif log_exp_op == "power":
            exp = int(input("Enter the exponent: "))
            print("Result:", power(value, exp))
        else:
            print("Invalid operation!")

    elif choice == 4:
        matrix1 = np.array([[int(input("Matrix 1 Element [{}][{}]: ".format(i, j))) for j in range(2)] for i in range(2)])
        matrix2 = np.array([[int(input("Matrix 2 Element [{}][{}]: ".format(i, j))) for j in range(2)] for i in range(2)])
        matrix_op = input("Choose matrix operation (add, multiply, transpose, determinant): ")

        if matrix_op == "add":
            print("Result:\n", matrix_add(matrix1, matrix2))
        elif matrix_op == "multiply":
            print("Result:\n", matrix_multiply(matrix1, matrix2))
        elif matrix_op == "transpose":
            print("Transpose of Matrix 1:\n", matrix_transpose(matrix1))
            print("Transpose of Matrix 2:\n", matrix_transpose(matrix2))
        elif matrix_op == "determinant":
            print("Determinant of Matrix 1:", matrix_determinant(matrix1))
            print("Determinant of Matrix 2:", matrix_determinant(matrix2))
        else:
            print("Invalid matrix operation!")

    elif choice == 5:
        print("Exiting... Goodbye! 👋")
        break

    else:
        print("Invalid choice! Please enter a number between 1-5.")
