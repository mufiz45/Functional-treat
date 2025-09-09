# Functional-treat
# PR.4 Functional Treat - Data Analyzer and Transformer

# Global variable to store dataset summary
dataset_summary = {}

# ---------------- Built-in Functions ----------------
def builtin_functions(arr):
    """Demonstrate built-in functions on list"""
    print("Length of data:", len(arr))
    print("Sum:", sum(arr))
    print("Min:", min(arr))
    print("Max:", max(arr))

# ---------------- User Defined Functions (UDF) ----------------
def calculate_average(arr):
    """Return average of list"""
    return sum(arr) / len(arr) if arr else 0

def find_duplicates(arr):
    """Return duplicate values from list"""
    return list(set([x for x in arr if arr.count(x) > 1]))

def unique_values(arr):
    """Return unique values from list"""
    return list(set(arr))

# ---------------- *args, **kwargs, __doc__ ----------------
def args_example(*args):
    """Accepts multiple values and displays them"""
    print("Values:", args)

def kwargs_example(**kwargs):
    """Accepts key-value pairs and prints summary"""
    for key, value in kwargs.items():
        print(f"{key}: {value}")

# ---------------- Recursion ----------------
def factorial(n):
    """Recursive factorial"""
    if n == 0 or n == 1:
        return 1
    return n * factorial(n - 1)

def fibonacci(n):
    """Recursive Fibonacci"""
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

# ---------------- Lambda Functions ----------------
def lambda_filter(arr, threshold):
    """Filter values above threshold"""
    return list(filter(lambda x: x > threshold, arr))

def lambda_map(arr):
    """Square all values using lambda"""
    return list(map(lambda x: x**2, arr))

# ---------------- Global Keyword ----------------
def update_summary(arr):
    """Update global dataset summary"""
    global dataset_summary
    dataset_summary = {
        "count": len(arr),
        "sum": sum(arr),
        "mean": calculate_average(arr)
    }

def show_summary():
    """Show global dataset summary"""
    print("Dataset Summary:", dataset_summary)

# ---------------- Return Multiple Values ----------------
def stats(arr):
    """Return min, max, avg"""
    return min(arr), max(arr), calculate_average(arr)

# ---------------- 1D and 2D Array ----------------
def display_2d(arr):
    """Display 2D list in formatted grid"""
    for row in arr:
        print(row)

# ---------------- Sorting ----------------
def sort_1d(arr):
    """Sort 1D list ascending and descending"""
    print("Ascending:", sorted(arr))
    print("Descending:", sorted(arr, reverse=True))

def sort_2d(arr):
    """Sort 2D list rows by first element"""
    arr.sort(key=lambda x: x[0])
    display_2d(arr)

# ---------------- Menu ----------------
def main():
    while True:
        print("\n--- Data Analyzer & Transformer ---")
        print("1. Built-in Functions")
        print("2. User Defined Functions")
        print("3. Args/Kwargs Example")
        print("4. Recursion")
        print("5. Lambda Functions")
        print("6. Global Variable Summary")
        print("7. Return Multiple Values")
        print("8. 1D & 2D Arrays")
        print("9. Sorting")
        print("0. Exit")

        choice = input("Enter choice: ")

        if choice == "1":
            arr = [1, 2, 3, 4, 5]
            builtin_functions(arr)

        elif choice == "2":
            arr = [1, 2, 2, 3, 4, 5]
            print("Average:", calculate_average(arr))
            print("Duplicates:", find_duplicates(arr))
            print("Unique:", unique_values(arr))

        elif choice == "3":
            args_example(10, 20, 30)
            kwargs_example(name="Mufij", age=18, country="India")
            print(args_example.__doc__)

        elif choice == "4":
            print("Factorial(5):", factorial(5))
            print("Fibonacci(6):", fibonacci(6))

        elif choice == "5":
            arr = [1, 5, 8, 3, 10]
            print("Filtered (>5):", lambda_filter(arr, 5))
            print("Squared:", lambda_map(arr))

        elif choice == "6":
            arr = [2, 4, 6, 8, 10]
            update_summary(arr)
            show_summary()

        elif choice == "7":
            arr = [10, 20, 30, 40, 50]
            mn, mx, avg = stats(arr)
            print("Min:", mn, "Max:", mx, "Average:", avg)

        elif choice == "8":
            arr1 = [1, 2, 3, 4]
            arr2 = [[1, 2], [3, 4], [5, 6]]
            print("1D Array:", arr1)
            print("2D Array:")
            display_2d(arr2)

        elif choice == "9":
            arr1 = [7, 2, 5, 1, 9]
            arr2 = [[3, 2], [1, 5], [2, 4]]
            sort_1d(arr1)
            print("Sorted 2D Array:")
            sort_2d(arr2)

        elif choice == "0":
            print("Exiting program...")
            break

        else:
            print("Invalid choice, try again!")

# Run program
if __name__ == "__main__":
    main()
