# Topic of Discuss : SET
[Welcome](0-welcome.md)
## Introduction

## Understanding the `SET` data structure 
A `SET` is a data structure that stores unique element of the same type in a sorted order. Each value is a key, which means that we access each value using the value itself. With arrays, on the other hand, we access each value by its position in the container. The SET data structure also represents a collection of unique elements. A set typically has no particular order, and its elements can be added, removed, and searched for efficiently. The basic operations supported by sets include:
- Adding an element to the set
- Removing an element from the set
- Testing whether an element is a member of the set
- Finding the number of element in the set
- Performing set operations such as union, intersection, and difference.


In set data structure, we use a dictionary also called hash map. Hash map helps for efficienct lookups and insertions of key-value pairs. it works by mapping key to a unique index in an array, which is used to store the corresponding value.

### Hashing 
In C#, a HashSet is a collection that uses hashing to store and retrieve its elements. When you add an element to a HashSet, C# generates a hash code for the element using its GetHashCode method. The hash code is then used to find the appropriate bucket to store the element in. To retrieve an element from a HashSet, C# generates a hash code for the element being searched and then searches for that hash code in the appropriate bucket. If the hash code is found, C# uses the Equals method to compare the element being searched with the elements in the bucket until it finds a match. 

### Dictionary

A dictionary is a collection that stores key-value pairs. It uses hashing to store and retrieve its key-value pairs efficiently. When you add an item to a dictionary, C# calculates a hash value for the key using a hash function. The hash value is then used to determine the location in memory where the key-value pair should be stored. When you look up a value by its key in a dictionary, C# calculates the hash value for the key again, uses it to determine the location of the corresponding key-value pair, and returns the value associated with the key.


Another thing we'll also like to discuss in this tutorial with set is `Conflict Resolution`. In set data structure, conflicts can arise when attempting to add an element to a set that already contains the same element. This conflict can be resolved in several ways, depending on the specific requirements and constraints of the application. One approach to resolve this in cases of duplicate is to ignore the duplicate element and not add it to the set. Another approach to conflict resolution is to replace the existing element in the set with the new element, or also use the merge approach to merge the new element to the already existing element in the set, by this, combining any shared information and preserving any unique information.

The implementation of set may vary base on the programming language being used. But in this tutorial, we'll be learning set with C sharp programming language.

## What is the purpose of the `SET` data structure?

The purpose of the set data structure is to provide an efficient way to store and manipulate a collection of unique elements. Sets are often used when there is a need to perform membership tests, deduplicate data, or perform set operations such as union, intersection, and difference.

## How would the data structure be used in C#
As mentioned earlier in the introduction, the SET data structure has different operations that enable us to perform various operations like sorting of data, accessing element in the set, managing data, and manipulating data as required. Some of this operations will be discussed with examples in this section. The table below explains the various operations that can be used to effectly perform different functions in set.

Operation | Explanation | C# Example
----------|-------------|---------------
`Add()`|The operation help us add element to the set using the `Add()` method| mySet.Add("car");
`Remove()`| We remove the element "car" from the set using the `Remove()` method.| mySet.Remove("car")
`Contains()`|In C#, you can test whether an element is a member of a set using the `Contains()`|mySet.Contains("car")
`Count`|We can find the number of elements in the set using the `Count` property and assign the result to an integer variable `count`. Finally, we print the value of `count` to the console.|int count = mySet.Count()
`Union`, `intersect`, `Except`| In set data structure, the union of two sets is the set of all elements that are in either of the two sets. The intersection of two sets is the set of all elements that are common to both sets. The difference of two sets is the set of all elements that are in the first set but not in the second set.| set1.Union(set2), set1.Intersect(set2), set1.Except(set2)


## What is the performance of the data structure 

The performance of the set data structure depends on the specific implementation and the operations being performed. In general, sets typically provide average-case constant time (O(1)) performance for add, remove, and membership test operations. However, the worst-case performance for these operations can be O(n), where n is the number of elements in the set, if there are many collisions in the hash table used to implement the set. Additionally, set operations like union, intersection, and difference typically have a worst-case performance of O(n) because they require iterating over all the elements in the sets.
```csharp
  HashSet<string> mySet = new HashSet<string>();

    // Add elements to the set
    mySet.Add("apple");
    mySet.Add("banana");
    mySet.Add("orange");

    // Print the set
    foreach (string element in mySet)
    {
        Console.WriteLine(element);
    }      
```
The above code example is an O(1) performance. Because the Add and Remove operation usually use an O(1) time to add and remove element from the set, following similar unchanging step for every process of Add() and Remove().

## Efficiency of common operations

The summary of the common operations and time complexity in Set 
Operation | Time Complexity/Peformance
----------|-----------------
Add|O(1) on average, O(n) in worse case if the hash table need to be resized
Remove| O(1) on average, O(n) in the worst case if the hash table needs to be resized.
Contains | O(1) since the set stores its size internally.
Union, Intersection, and except| O(m + n) where m and n are the sizes of the input sets.
Iterating over all elements | O(n) since all elements need to be visited.


## Problem to Solve
### Examples
1. Given an array of integers, find the unique elements in the array and return them in a new array.
```csharp
class Program
{
    static void Main(string[] args)
    {
        // Input array
        int[] arr = { 1, 2, 2, 3, 3, 4, 5, 5 };

        // Create a set to store unique elements
        HashSet<int> set = new HashSet<int>();

        // Add elements from the array to the set
        for (int i = 0; i < arr.Length; i++)
        {
            set.Add(arr[i]);
        }

        // Convert the set back to an array
        int[] uniqueArr = new int[set.Count];
        set.CopyTo(uniqueArr);

        // Print the unique elements
        Console.WriteLine("Unique elements:");
        for (int i = 0; i < uniqueArr.Length; i++)
        {
            Console.WriteLine(uniqueArr[i]);
        }
    }
}
```
In this example, we first define an input array of integers. We then create a HashSet<int> to store the unique elements from the array. We loop through the input array, and add each element to the set using the Add method. Since the set automatically removes duplicates, we end up with only the unique elements in the set.

We then convert the set back to an array using the CopyTo method, which copies the elements in the set to an array. We create a new array of the appropriate size and pass it to the CopyTo method.

Finally, we print the unique elements in the array using a for loop.

2. Example 
Given a set of integers, remove any duplicate elements and return the updated set.
```csharp
class Program
{
    static void Main(string[] args)
    {
        //Your Code Solution Here
    }

}
```
## [Problem Solution](5-C%23File.md)

## Explain what kind of error are common using this data structure.
Some common error you might encounter when implementing the SET operation is listed as follow;
1. TypeError: unhashable type: 'list' - This error occurs when trying to add a mutable object such as a list to a set, as sets can only contain hashable objects.
2. KeyError - This error occurs when trying to remove an element from a set that does not exist in the set.
3. SyntaxError: invalid syntax - This error occurs when trying to create a set using curly braces {} instead of using the set() constructor. Curly braces are used for creating a dictionary, not a set.


This are some common errors to look out for carefully when implementing SET operations.

## [Picture Explanation on Set](4-pictureFile.md)
## [Other Files Including Tables](6.otherFiles.md)

