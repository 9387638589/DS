def linear_search(arr, key):
    for i, element in enumerate(arr):
        if element == key:
            return i
    return -1

def binary_search(arr, key):
    low, high = 0, len(arr) - 1

    while low <= high:
        mid = (low + high) // 2
        mid_element = arr[mid]

        if mid_element == key:
            return mid
        elif mid_element < key:
            low = mid + 1
        else:
            high = mid - 1

    return -1

def search_element(arr, key, search_function):
    index = search_function(arr, key)
    if index != -1:
        return f"Element {key} found at index {index}."
    else:
        return f"Element {key} not found in the list."

if _name_ == "_main_":
    user_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

    print("Choose search type:")
    print("1. Linear Search")
    print("2. Binary Search")

    choice = int(input("Enter choice (1 or 2): "))

    if choice == 1:
        result = search_element(user_list, int(input("Enter element to search: ")), linear_search)
    elif choice == 2:
        result = search_element(user_list, int(input("Enter element to search: ")), binary_search)
    else:
        result = "Invalid choice. Please choose 1 or 2."

    print(result)
