# Recursion for JS Beginners

> //start with a simple example of recursion

[![Jesse DeOms](https://miro.medium.com/fit/c/56/56/1*f1kkkkFWuEhhL1Sy4Z2Iug.png)](chrome-extension://cjedbglnccaioiolemnfhjncicchinao/@jessedeoms?source=post_page-----6633d258cb4c--------------------------------)

**//start with a simple example of recursion**

Prompt: write a function that will reverse a string:

var reverse = function(string){  
  if(string.length < 2){  
    return string;  
  }   
  var first = string\[0\]  
  var last = string\[string.length-1\];  
  return last +reverse(string.slice(1, string.length-1)) + first;  
};reverse('abcdef'); //returns 'fedcba'

**//explain what a recursive function is**

**_A function that calls itself_** is a recursive function.

If a function calls itself… then that function calls itself… then that function calls itself… well… then we have fallen into an infinite loop (a very unproductive place to be). To benefit from recursive calls, we need to be careful to include to give our interpreter a way to break out of the cycle of recursive function calls; we call this a **_base case_**.

The base case in the solution code above is as simple as testing that the length of the argument is less than 2… and if it is, returning the the value of that argument.

Notice how each time we recursively call the reverse function, we are passing it a shorter string argument… so each recursive call is getting us closer to hitting our **_base case_**.

**//visualize the interpreter’s path through recursive function calls**

![Image for post](https://miro.medium.com/max/60/1*J4FL6LpLY1AXy_KPFdREKw.png?q=20)

![Image for post](https://miro.medium.com/max/1810/1*J4FL6LpLY1AXy_KPFdREKw.png)

Slow down and follow the interpreter through its execution of your algorithm (thanks to PythonTutor.com)

Python Tutor is an excellent resource for learning to visualize and trace variable values through the multiple execution contexts of a recursive function’s invocation.

_Try it now with these simple steps:_

1.  _copy the solution code from above_
2.  _go over to_ [_http://pythontutor.com/javascript.html#mode=edit_](http://pythontutor.com/javascript.html#mode=edit)
3.  _paste the solution code into the editor_
4.  _click the “Visualize Execution” button_
5.  _progress through the execution with the “forward” button_

**//when can a recursive function help me?**

So if I hope that at this point that you are thinking: there is a **_better_** way to reverse a function, or there is a **_simpler_** way to reverse a string…

First off… **_simpler is better._** Writing good code isn’t about being clever or fancy; good code is about writing code that works, that makes sense to as many other minds as possible, that is time efficient, and that is memory efficient (in order of importance). As new programers, the first of these criteria is obvious, and the last two are given way too much weight. It’s the second of these criteria that needs to carry much more weight in our minds and deserves the most attention. Recursive functions can be a powerful tool in helping us write clear and simple solutions.

To be clear: recursion is not about being fancy or clever… it is an important skill to wrestle with early because there will be many scenarios when employing recursion will allow for a simpler and more reliable solution than would be possible without recursive functions.

**//more useful example**

Prompt: check to see if a binary-search-tree contains a value

var searchBST = function(tree, num){  
  if(tree.val === num){  
    return true  
  } else if(num > tree.val){  
    if(tree.right === null){  
      return false;  
    } else{  
      return searchBST(tree.right, num);  
    }  
  } else{  
    if(tree.left === null){  
      return false;  
    } else{  
      return searchBST(tree.left, num);  
    }  
  }  
};var tree = {val: 9,   
            left: {val: 5,   
                   left: null,   
                   right: {val: 7,   
                           left: null,   
                           right: null}  
                   },   
            right: {val: 20,  
                    left: {val: 16,  
                           left: null,  
                           right: {val: 18,   
                                   left: null,  
                                   right: null}  
                          },  
                    right: null}  
           };searchBST(tree, 18) // return true  
searchBST(tree, 4) // return false

When traversing trees and many other other non-primative data structures, recursion allows us to define a clear algorithm that elegantly handles uncertainty and complexity. Without recursion, it would be impossible to write a single function that could search a binary search tree of any size and state… yet by employing recursion, we can write a concise algorithm that will traverse any binary search tree and determine if it contains a value or not.

Take a moment to analyze how recursion is used in this example by tracing the interpreters path through this solution. Just as we did for the reverse function above, paste this binary search tree code snippet into the editor at [http://pythontutor.com/javascript.html#mode=display](http://pythontutor.com/javascript.html#mode=display)

In this function definition, there are three base cases that will return a value instead of recursively calling the searchBST function… can you find them?

//now go practice using recursion

[Codewars](https://www.codewars.com/) is a wonderful place to find toy problems and a quick recursion search on this page will give you some good problems to chew on. The best resource that I have found for a well-thought-out list of increasingly challenging recursion toy problems can be found at: [https://github.com/JS-Challenges/recursion-prompts](https://github.com/JS-Challenges/recursion-prompts).


[Source](https://medium.com/@jessedeoms/recursion-for-js-beginners-6633d258cb4c)