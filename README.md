def find_subarray(arr, target):
    start, curr_sum = 0, 0
    for end in range(len(arr)):
        curr_sum += arr[end]
        while curr_sum > target:
            curr_sum -= arr[start]
            start += 1
        if curr_sum == target:
            return arr[start:end+1]
    return None

arr = list(map(int, input("Enter array: ").split(',')))
target = int(input("Enter target sum: "))

result = find_subarray(arr, target)
print(f"Subarray: {result}" if result else "No subarray found")

