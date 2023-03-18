# C Sharp Stack coding example

## 1. Example:

Reverse a string using a stack: Push every character of the string onto a stack and then pop each character off the stack to get the reversed string.

```csharp
public static string ReverseString(string str)
{
    Stack<char> stack = new Stack<char>();
    foreach (char c in str)
    {
        stack.Push(c);
    }
    string reversedString = "";
    while (stack.Count > 0)
    {
        reversedString += stack.Pop();
    }
    return reversedString;
}
```
In this code, we create a new stack of characters Stack<char> stack = new Stack<char>() and iterate over each character in the input string str. We push every character onto the stack using stack.Push(c). We then create an empty string reversedString and pop each character off the stack using stack.Pop() and append it to the string. Finally, we return the reversed string.

So, the output of this program will be the reverse of the input string.

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

[Back to Stack Homepage](1-topic.md)