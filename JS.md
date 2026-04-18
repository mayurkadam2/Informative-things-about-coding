
![](https://img.shields.io/badge/Mayur_Kadam_is_the_best-8A2BE2)
- [ ] Yes Mayur is best

In programming, a function is a reusable block of code that performs a specific task and can be called with various inputs. 
A method, on the other hand, is a type of function that is associated with an object, meaning it operates on the data contained within that object.

<hr>


getElementsByClassName(): It matches the elements with the specified class name, and returns a set of the matched elements.
The returned elements are live HTML collection of elements.
These live elements can be further updated if any changes are made in the Document Object Model.

querySelector(): It returns only a single element that matches the specified classname. If it does not find any matching element, it returns null.


<hr>


document.createElement('elementName');
document.createElement('elementName').appendChild(document.queryselector('.class'));

document.queryselector('.class');
document.queryselector('.panel').clientWidth;
document.queryselector('.panel').classList.add("className");

addEventListener(,);
document.queryselector('.class').addEventListener( , );

object['key'] = value;
object['key']=document.createElement('elementName');



in JavaScript, arrays are just special objects, so you can also use them like a dictionary (key-value store).
Your blocks is acting like a dictionary keyed by "row-col" strings, not a traditional array. That’s why it works, but it’s a bit misleading to initialize it as [].
blocks['${row}-{col}'] = block;
