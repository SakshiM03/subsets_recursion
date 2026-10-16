
def subsets(arr):
    result = []

    def backtrack(index, path):
        if index == len(arr):
            result.append(path.copy())
            return

        # Exclude the current element
        backtrack(index + 1, path)

        # Include the current element
        path.append(arr[index])
        backtrack(index + 1, path)

        # Undo the choice
        path.pop()

    backtrack(0, [])
    return result


numbers = [1, 2, 3]

for item in subsets(numbers):
    print(item)
# subsets_recursion
