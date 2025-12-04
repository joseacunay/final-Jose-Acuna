---
title: " Reversing an Array!"
description: ""
omit_header_text: false
featured_image: images/int.webp
summary: "If you want to learn more about this topic, press the button below."
type: page
weight: 2
---


## Introduction to the Array

An array is a list-like container that holds a collection of items. These items are stored in a specific order, and each item can be accessed using an index number, starting from 0.

### Practical Example

```
let colors = ["red", "blue", "green"];
console.log(colors[0]); // "red"

```

<p>Enter your array (example: red,blue,green or  number 1,2,3,4,5):</p>
<input type="text" id="inputArray" placeholder="red,blue,green or 1,2,3,4,5">
<button onclick="showArrayInfo()">Run</button>

<h3>Result:</h3>
<pre id="result" style="background:#f0f0f0; padding:10px;"></pre>

<script>
// Function executed when the button is pressed
function showArrayInfo() {
    const input = document.getElementById('inputArray').value;
    const resultEl = document.getElementById('result');
    
    // Convert input to an array of strings
    let array = input.split(',').map(item => item.trim());

    // Build output text
    let output = "";
    output += "Full array: " + JSON.stringify(array) + "\n\n";
    output += "First element (index 0): " + (array[0] ?? "undefined") + "\n";
    output += "Second element (index 1): " + (array[1] ?? "undefined") + "\n";
    output += "Third element (index 2): " + (array[2] ?? "undefined") + "\n\n";
    output += "Array length: " + array.length;

    // Show the result
    resultEl.textContent = output;
}
</script>
The result shows that you can create an array with numbers, things, or a combination of both.

##  Reversing an Array

You must write two functions:
>ReverseArray(arr)
Creates a new array with elements in reversed order.
Does not change the 
original array (pure function).

>ReverseArrayInPlace(arr)
Reverses the elements inside the original array.
Changes the array directly (has side effects)

<img class="profile-image-bottom" src="/images/ar.png" alt="arrays">


### Class Exercise

In this section I will explain a practical exercise from the page <a href="https://eloquentjavascript.net/04_data.html" target="_blank">Eloquent Javasript</a> 

```
Reversing an Array
console.log("\nExercise 4.2: Reversing an array"); // Print title

function reverseArray(array) { // Function that creates a new reversed array 
(does not change original)
  let result = [];                
  for (let i = array.length - 1; i >= 0; i--) {
    result.push(array[i]);// Add elements from end to start
  }
  return result;                  
}

function reverseArrayInPlace(array) { // Function that reverses array in place 
(changes the original array)
  for (let i = 0; i < Math.floor(array.length / 2); i++) {
    let j = array.length - 1 - i; // Index from the end
    let temp = array[i]; // Save current element
    array[i] = array[j]; // Swap with opposite element
    array[j] = temp; // Put saved element in opposite position
  }
  return array;
}

```
## Practical Example from Reverse Array

<p>Enter your array (example: 1,2,3,4,5):</p>
<input type="text" id="inputReverse" placeholder="1,2,3,4,5">
<button onclick="reverseAndShow()">Run</button>

<pre id="resultReverse" style="background:#f0f0f0; padding:10px;"></pre>

{{< rawhtml >}}
<script>
function reverseArrayInPlace(array) {
    for (let i = 0; i < Math.floor(array.length / 2); i++) {
        let temp = array[i];
        array[i] = array[array.length - 1 - i];
        array[array.length - 1 - i] = temp;
    }
}

function reverseAndShow() {
    const input = document.getElementById("inputReverse").value;
    const result = document.getElementById("resultReverse");

    let array = input.split(",").map(x => x.trim());
    let original = [...array];

    reverseArrayInPlace(array);

    result.textContent =
        "Original array: " + JSON.stringify(original) + 
        "\nReversed array: " + JSON.stringify(array);
}
</script>
{{< /rawhtml >}}

<!-- Conclusion Section -->
<div style="
    background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
    border-radius: 15px;
    padding: 25px;
    margin-top: 30px;
    box-shadow: 0 8px 20px rgba(0,0,0,0.2);
    font-family: 'Arial', sans-serif;
    color: #333;
">
    <h2 style="
        text-align: center;
        color: #fff;
        text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        margin-bottom: 15px;
    ">🎯 Conclusion</h2>
    <p style="font-size: 16px; line-height: 1.6;">
        Reversing an array may seem like a simple task, but it teaches two fundamental ideas in programming: pure functions and in-place transformations. 
        With reverseArray, we saw how a function can take a value, process it, and return a new result without modifying the original data a key concept in functional programming. 
        On the other hand, <code>reverseArrayInPlace</code> showed how to directly transform the existing array by swapping its elements, which is more memory-efficient and often used in real-world applications.
    </p>
    <p style="font-size: 16px; line-height: 1.6;">
        Understanding the difference between these methods helps improve problem-solving skills, teaches when to preserve data, and prepares you for more advanced concepts like data structures, algorithms, and performance optimization. 
        Mastering exercises like this builds a strong foundation for writing cleaner, smarter, and more efficient JavaScript code.
    </p>
</div>

<!-- Fixed Button to Home -->
<a href="/" id="reversingBtn">Home</a>

<style>
  /* Styles for the fixed button */
  #reversingBtn {
    position: fixed;
    bottom: 20px;
    left: 20px;
    background-color: #007BFF;
    color: white;
    padding: 12px 18px;
    border-radius: 8px;
    text-decoration: none;
    font-weight: bold;
    box-shadow: 0 4px 6px rgba(0,0,0,0.2);
    transition: background-color 0.3s, transform 0.2s;
    z-index: 1000;
  }

  #reversingBtn:hover {
    background-color: #0056b3;
    transform: translateY(-2px);
  }
</style>

<!-- Fixed Button to Minimun -->
<a href="/articles/programming-2/" id="mini">Minimun!</a>

<style>
  /* Styles for the fixed button */
  #mini {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background-color: #007BFF;
    color: white;
    padding: 12px 18px;
    border-radius: 8px;
    text-decoration: none;
    font-weight: bold;
    box-shadow: 0 4px 6px rgba(0,0,0,0.2);
    transition: background-color 0.3s, transform 0.2s;
    z-index: 1000;
  }

  #reversingBtn:hover {
    background-color: #0056b3;
    transform: translateY(-2px);
  }
</style>