# leet-day88

## Problem Description

You are given a list of flowers, each with a start time and an end time, and a list of people, each arriving at a specific time. Your task is to find, for each person, how many flowers are in full bloom at the time of their arrival.

## Example

**Input:**

Flowers:
```
[[1, 6], [3, 7], [9, 12], [4, 13]]
```

People:
```
[2, 3, 7, 11]
```

**Output:**

```
[1, 2, 2, 2]
```

**Explanation:**

For each person, we calculate the number of flowers that are in full bloom when that person arrives. The output shows the count of such flowers for each person.

## Approach

1. Initialize two vectors, `start` and `end`, to store the start and end times of the flowers.
2. For each flower in the input, add its start time to the `start` vector and its end time to the `end` vector.
3. Sort the `start` and `end` vectors in non-decreasing order.
4. For each person's arrival time:
   - Use binary search to find the number of flowers that have started blooming at or before the person's arrival time (`started`).
   - Use binary search to find the number of flowers that have ended blooming at or before the person's arrival time (`ended`).
   - Calculate the number of flowers in full bloom as `started - ended` and add it to the result vector.
5. Return the result vector containing the number of flowers in full bloom for each person.

## Complexity Analysis

- Time Complexity: O(N log N) where N is the number of flowers and people. The sorting of the `start` and `end` vectors takes O(N log N) time, and each person's query takes O(log N) time.
- Space Complexity: O(N) for storing the `start` and `end` vectors and the result vector.

## How to Run

we can run this solution by creating a `Solution` class and calling the `fullBloomFlowers` method with the flower and people input. Here's an example of how to use it:

```cpp
Solution solution;
vector<vector<int>> flowers = {{1, 6}, {3, 7}, {9, 12}, {4, 13}};
vector<int> people = {2, 3, 7, 11};
vector<int> result = solution.fullBloomFlowers(flowers, people);

// Print the result
for (int num : result) {
    cout << num << " ";
}
```
