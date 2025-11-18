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

### Example

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
Does not change the original array (pure function).

>ReverseArrayInPlace(arr)
Reverses the elements inside the original array.
Changes the array directly (has side effects)

<img class="profile-image-bottom" src="/images/ar.png" alt="arrays">


### Class Exercise

In this section I will explain a practical exercise from the page <a href="https://eloquentjavascript.net/04_data.html" target="_blank">Eloquent Javasript</a> 

```
Reversing an Array
console.log("\nExercise 4.2: Reversing an array"); // Print title

function reverseArray(array) { // Function that creates a new reversed array (does not change original)
  let result = [];                
  for (let i = array.length - 1; i >= 0; i--) {
    result.push(array[i]);// Add elements from end to start
  }
  return result;                  
}

function reverseArrayInPlace(array) { // Function that reverses array in place (changes the original array)
  for (let i = 0; i < Math.floor(array.length / 2); i++) {
    let j = array.length - 1 - i; // Index from the end
    let temp = array[i]; // Save current element
    array[i] = array[j]; // Swap with opposite element
    array[j] = temp; // Put saved element in opposite position
  }
  return array;
}

```