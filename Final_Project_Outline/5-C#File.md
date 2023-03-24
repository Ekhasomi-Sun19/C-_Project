# Stack Problem Solution
## 2. Example:
Given a string with parentheses, write a function to determine if the parentheses are balanced. A string is considered balanced if it consists entirely of pairs of opening/closing parentheses (in that order), and for every opening parenthesis there is a corresponding closing parenthesis.

```csharp
public static bool IsBalanced(string str)
{
    Stack<char> stack = new Stack<char>();
    foreach (char c in str)
    {
        if (c == '(')
        {
            stack.Push(c);
        }
        else if (c == ')')
        {
            if (stack.Count == 0 || stack.Pop() != '(')
            {
                return false;
            }
        }
    }
    return stack.Count == 0;
}
```
This function uses a stack to keep track of opening parentheses. It iterates over each character in the input string str, and if the character is an opening parenthesis, it pushes it onto the stack. If the character is a closing parenthesis, it pops the top character off the stack and checks if it matches the corresponding opening parenthesis. If the stack is empty or the parentheses don't match, the function returns false. If the function makes it through the entire loop without returning false, it checks if the stack is empty and returns true if it is. This indicates that all parentheses were balanced.

So, if we call the IsBalanced method with the input string "((()))", the output would be true as this string has balanced parentheses. If we call the IsBalanced method with the input string "(()))", the output would be false as this string does not have balanced parentheses.


# SET Problem Solution
## 2. Example:
Given a set of integers, remove any duplicate elements and return the updated set.

```csharp
class Program
{
    static void Main(string[] args)
    {
        // Input set
        HashSet<int> set = new HashSet<int>() { 1, 2, 3, 3, 4, 5, 5 };

        // Create a new set to store the unique elements
        HashSet<int> uniqueSet = new HashSet<int>();

        // Add the elements from the input set to the new set
        foreach (int elem in set)
        {
            uniqueSet.Add(elem);
        }

        // Print the unique elements in the set
        Console.WriteLine("Unique elements:");
        foreach (int elem in uniqueSet)
        {
            Console.WriteLine(elem);
        }
    }
}
```
In this example, we first define an input set of integers using the HashSet<int> constructor. We then create a new HashSet<int> called uniqueSet to store the unique elements.

We loop through the input set using a foreach loop, and add each element to the new set using the Add method. Since the set automatically removes duplicates, we end up with only the unique elements in the new set.

Finally, we print the unique elements in the set using a foreach loop.

[Back to Stack Homepage](1-topic.md)


[Back to Set Tutorial Homepage](2-topic.md)