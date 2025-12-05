---
title: "Minimum!"
description: ""
omit_header_text: true
featured_image: images/h1.png
summary: "Returns the smallest of the numbers given as input parameters."
type: page
weight: 3
---

<article>
  <h2>Understanding the Concept of "Minimum" in JavaScript</h2>

  <p>In programming, we often need to compare values and find the smallest one. This is called the <strong>minimum</strong>. In JavaScript, there is a standard function <code>Math.min</code> that returns the smallest of the values passed to it:</p>

  <pre><code>
console.log(Math.min(0, 10));  // → 0
console.log(Math.min(0, -10)); // → -10
  </code></pre>

  <p>However, we can also create our own function to find the minimum of two numbers. This helps us understand how comparisons work and practice defining functions:</p>

  <pre><code>
function min(a, b) {
  return a < b ? a : b;
}

console.log(min(0, 10));  // → 0
console.log(min(0, -10)); // → -10
  </code></pre>

  <p>The <code>min</code> function takes two arguments, compares them using <code>&lt;</code>, and returns the smaller one.</p>

  </ul>

<article>
  <h2>Find the Minimum Number (Interactive)</h2>

  <p>Enter numbers one by one. The minimum of all entered numbers will be shown.</p>

  <label for="numInput">Number:</label>
  <input id="numInput" type="number">
  <button id="addBtn">Add Number</button>
  <button id="getMinBtn">Get Minimum</button>

  <p>Numbers entered: <span id="numbersList">[]</span></p>
  <p>Minimum: <span id="minResult">-</span></p>

  <script>
    // Array to store numbers
    const numbers = [];

    // Function to calculate minimum of an array
    function minArray(arr) {
      if (arr.length === 0) return null; // No numbers entered
      let minVal = arr[0];
      for (let i = 1; i < arr.length; i++) {
        if (arr[i] < minVal) minVal = arr[i];
      }
      return minVal;
    }

    // Add number to array
    document.getElementById('addBtn').onclick = function() {
      const num = Number(document.getElementById('numInput').value);
      if (!isNaN(num)) {
        numbers.push(num);
        document.getElementById('numbersList').textContent = JSON.stringify(numbers);
        document.getElementById('numInput').value = '';
        document.getElementById('numInput').focus();
      }
    };

    // Get minimum number
    document.getElementById('getMinBtn').onclick = function() {
      const minVal = minArray(numbers);
      document.getElementById('minResult').textContent = minVal !== null ? minVal : 'No numbers entered';
    };
  </script>
</article>



  <p>This example shows how recursion can help us solve problems step by step until reaching a base case.</p>

  <h3>Conclution</h3>
  <ul>
    <li>The <strong>minimum</strong> is the smallest value in a set of numbers.</li>
    <li>We can use <code>Math.min</code> or define our own <code>min</code> function to get it.</li>
    <li>Recursion is useful for problems that can be broken down into smaller steps, such as determining if a number is even.</li>
  </ul>
</article>

<!-- Fixed Button to Reversing Array -->
<a href="/articles/programming-1/" id="reversingBtn">Reversing Array</a>

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