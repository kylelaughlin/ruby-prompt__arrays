---
title: Arrays
instructor_notes: Feel free to re-organize the headings (or add/remove headings) below. We included the headings for your benefit, but it's 100% fine if you want to write your responses in some different structure.
---

# What is an Array?

An array is a data structure that acts like a list of elements. The elements can be any data type, variables, 
objects, etc. Elements are held in the array in order. Retrieval of array elements depends on this order as 
elements are called based on their index. Arrays are zero based so the first element in an array would be called 
using the index 0 (my_array[0]).  

# What are some examples of information that would be Arrays as opposed to some other data type?

An array is usefull when storing multiple, connected (like) things.  For example if I had a list of guitar brands 
I needed to store I could utilize an array to hold the list.  ["gibson","epiphone","gretsch"].  An array can also 
be used to hold information on a grid. To do this you would use a two dimensional array.  An example of this could 
be what type of chess piece occupies a given space on a chess board.  

# What is one way, using Ruby, to retrieve the 6th element in an Array? How about the 8th element? What happens if you try to retrieve the value of the _9999th_ element (or some element that doesn't exist in the array)?

One way to retrieve the 6th element in an Array is to refrence the arrays index.  This would be done by writing 
my_array[6-1]. The 6 references the nth element you want to retrieve. You would subtract one becuase arrays are 
zero based so the first element in an array has an index of 0. To get the 8th element we would change the 6 to 
an 8 so would have my_array[8-1]. If I were to try and retrieve the 9999th element or any element that does not 
exist would return nil or nothing as that element does not exist.

# The previous question asks about finding, for example, the 6th element in an Array. Is it possible to find the **-6th** (Notice the negative symbol!) element in an Array? What does that even mean?

It is possible to find the -6th element of an array, assuming that there are at least 6 elements in the array. 
To find the -6th element of an array means to find the 6th element from the end of the array, moving right to 
left. If there are less than 6 elements in the array then my_array[-6] would return nil as nothing is there. 
Unlike the answer to the previous question, we do not need to subtract one as we do not have to deal with the 
zero index when moving from right to left.

# How would you perform an operation on every element inside an Array?

If I wanted to perform an operation on every element inside an Array I would utilize the each method.  This 
method iterates through each element in an array and carries out a block of code.  This is utilized by 
writing my_array.each {some operation}. 

# How do you add elements to an Array?

You add elements to an Array through the process of pushing an element into it.  This takes the information to 
be pushed into the array and adds it as a new element on the end of the array.  There are two ways to do this. 
Lets say I wanted to push the integer 28 into an existing array.  I could do it like this: my_array.push (28) or 
I could do it like this: my_array << 28.

# Given the Array `["Laura", "Fiona", "Tori"]`, how would you replace `"Fiona"` with `"Florence"` so that you end up with `["Laura", "Florence", "Tori"]`?

A simple way to do this would be to utilize the index that "Fiona" is located and re-assign it. Say we set the 
variable 'names' to the array above.  We would make the replacement by saying name[1] = "Florence". 

I could also use a method that would iterate through the array and check for "Fiona". If "Fiona" is found then 
it would be replaced with "Florence". To do this I would use the map method.  This method executes some block 
of code on each element of an array (or other object) and outputting what is returned form the code block to its 
respective location in the array. To accomplish the task given I would have my code block in the map function 
utilize an if statement to check for the name "Fiona" and if found return "Florence" to the array in its place. 
Instead of writing our a full if-else statement I could use a ternary operator. My code for seomthing like this 
would be this:

["Laura", "Fiona", "Tori"].map! { |i| i == "Fiona" ? "Florence" : i}

The code block is similar to if I were to write something like this { |i| if i == "Fiona" Then "Florence" else i}

# What do the methods `push`, `pop`, `shift`, and `unshift` do?

The push method is used to add another element into the end of an array.  If I did this: [5,4,3].push(2) I would 
be returned with [5,4,3,2]. I can also push multiple elements at the same time by doing this: [5,4,3].push(2, 1) 
which would return the array [5,4,3,2,1].

The pop method is used to return the last element of an array and also remove that element from the array. We can 
also tell the pop method to return the last two, three, four, and so one elements of an array and then remove them 
from the original array.  If I did this: [5,4,3].pop (2) I would be returned [4,3] since they are the last two 
elements in the array. The original array would then be [5] since the last two elements were removed by the pop 
method.

The shift method is much like pop except that it acts on the first element of an array. If i did this: 
[5,4,3].shift I would be returned 5 and the original array would be [4,3]. I can also tell it to return any 
number of elements until the array is empty. [5,4,3].shift (2) returns [5,4] and leaves [3] in the array.

The unshift method works much like the push method by adding something as an element to the front of an array. 
It shifts the index of existing elements of the array up to make room for the new array element. If I did this:
[5,4,3].unshift (7) the resulting array would be [7,5,4,3] and this [5,4,3].unshift(7, 3) would return the array 
[7,3,5,4,3].

# How do you determine how many elements are in an Array?

I would determine how many elements are in an Array by using the length method. This method returns how many 
elements are in an array. For example this [5,6,34,234].length would return 4.

# How would you reverse the order of elements in an Array?

I would reverse the elements in an array by utilizing the reverse method. If I set my_array = [5,4,3] and then 
utilized the reverse method by writing my_array.reverse I would be returned with [3,4,5]. If I wanted to make 
the array to keep the reversal I would write my_array!.

# How would you convert a String `"Sumeet Jain"` into an Array `["Sumeet", "Jain"]`? How about to `["S", "u", "m", "e", "e", "t", " ", "J", "a", "i", "n"]`? How would you convert the Array back into a String?

To convert "Sumeet Jain" into an array ["Sumeet", "Jain"] I would use the split method utilizing a space (" ") as 
the deliminator. The code "Sumeet Jain".split (" ") would return the array ["Sumeet", "Jain"]. In order to obtain 
an array with each element being each character in the string I would change the above code to make the split after 
each character: "Sumeet Jain".split ("").