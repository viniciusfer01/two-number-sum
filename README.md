# Two Number Sum 
This algorithm checks if an array contains two number that can be added to result in a given number.

## Previous algorithm
The previous algorithm functioned well but its operations numbers grew in an order of O(n^2), which isn't very scallable.

    def twoNumberSum(array, targetSum):
        for i in range(len(array) - 1):
            firstNum = array[i]
            for j in range (i+1, len(array)):
               secondNum = array[j]
               if firstNum + secondNum == targetSum:
                 return [firstNum, secondNum]
           return []

## An Optimized Solution

Fortunatelly, we can trade some storage for better performance using dictionaries.

    def twoNumberSum(array, targetSum):
        dictionary = {}
        for i in range(len(array)):
            result = targetSum - array[i] 
            if result in dictionary:
            return [array[i], result]
            else:
            dictionary[array[i]] = True
        return []

This way we only need to go over the array one time, so the algorithm's complexity shrinks to O(n).