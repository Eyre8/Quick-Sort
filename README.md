Psuedocode:

FUNCTION quicksort(array, length)
    CALL quicksort_recursion(array, 0, length - 1)

FUNCTION quicksort_recursion(array, low, high)
    IF low < high THEN
        pivot_index = CALL partition(array, low, high)

        // Recursively sort elements before and after partition
        CALL quicksort_recursion(array, low, pivot_index - 1)
        CALL quicksort_recursion(array, pivot_index + 1, high)

FUNCTION partition(array, low, high)
    pivot_value = array[high]
    i = low

    FOR j FROM low TO high - 1 DO
        IF array[j] <= pivot_value THEN
            SWAP array[i] WITH array[j]
            INCREMENT i

    SWAP array[i] WITH array[high]
    RETURN i

MAIN FUNCTION
    DEFINE array = [12, 4, 15, 8, 17, 6, 11]
    DEFINE length = 7
    
    CALL quicksort(array, length)

    FOR i FROM 0 TO length - 1 DO
        PRINT array[i]
    PRINT NEWLINE
