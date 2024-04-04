# Java-array
Here's a more detailed implementation in Python:

```python
def merge_arrays(X, Y):
    m = len(X)  # Size of X
    n = len(Y)  # Size of Y
    
    # Start from the last element of X and Y
    i = m - n - 1  # Index of the last non-vacant cell in X
    j = n - 1      # Index of the last element in Y
    k = m - 1      # Index of the last cell in X
    
    # Merge elements of Y into X in sorted order
    while i >= 0 and j >= 0:
        if X[i] > Y[j]:
            X[k] = X[i]
            i -= 1
        else:
            X[k] = Y[j]
            j -= 1
        k -= 1
    
    # Copy remaining elements of Y if any
    while j >= 0:
        X[k] = Y[j]
        j -= 1
        k -= 1
    
    return X

# Example usage
X = [1, 3, 5, 0, 0, 0]  # X has 3 vacant cells at the end
Y = [2, 4, 6]
merged_array = merge_arrays(X, Y)

print("Merged Array:")
print(merged_array)
```

This code defines a function `merge_arrays` that takes two arrays `X` and `Y` as input and merges the elements of `Y` into `X` in their correct sorted order. It handles the case where `X` has vacant cells at the end to accommodate the elements of `Y`.
