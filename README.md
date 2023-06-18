<h1 align="center">
  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTFmBwx9zT344IIpJJB-fFHU62TMDhDVctAovQSSaxosN_fakHRbWGWhBWkGNKduFgFTIE&usqp=CAU" alt="Hashcat Logo" width="200" height="90">
</h1>

<p align="center">
  Welcome to the <strong>Password Cracker</strong> repository! 🔒💻
</p>

<p align="center">
  This project showcases two password-cracking techniques: a dictionary-based attack and a brute-force attack. It provides a menu-driven interface for users to choose the desired attack method or exit the program. The code demonstrates the usage of cryptographic hashing, file I/O, string manipulation, and algorithmic techniques. Feel free to explore and modify the code to suit your needs! 🚀🔒💡
</p>

<h2>Code Overview</h2>

<p>The code starts by including several necessary libraries using code tags:</p>

<pre><code class="cpp">#include &lt;iostream&gt;
#include &lt;fstream&gt;
#include &lt;string&gt;
#include &lt;algorithm&gt;
#include &lt;sstream&gt;
#include &lt;iomanip&gt;
#include &lt;openssl/sha.h&gt;
</code></pre>

<h3>Hashing Function</h3>

<p>The <code>sha256</code> function is responsible for calculating the SHA-256 hash of a given input string. It takes a <code>std::string</code> parameter <code>str</code> and performs the necessary steps to compute the hash. Here's an overview:</p>

<pre><code class="cpp">std::string sha256(const std::string&amp; str) {
    // ... SHA-256 hashing implementation ...
}
</code></pre>

<h3>Password Checking</h3>

<p>The <code>checkPassword</code> function compares a provided password with a target hash. It calls the <code>sha256</code> function to calculate the hash of the password and then checks if it matches the <code>targetHash</code> string.</p>

<pre><code class="cpp">bool checkPassword(const std::string&amp; password, const std::string&amp; targetHash) {
    // ... Password checking implementation ...
}
</code></pre>

<h3>Dictionary-Based Attack</h3>

<p>The <code>crackPassword</code> function implements a dictionary-based attack. It takes two parameters: <code>dictionaryFile</code>, which represents the name of a file containing a list of passwords to try, and <code>targetHash</code>, which is the hash of the password we want to crack.</p>

<p>Here's an overview of the steps:</p>

<ol>
  <li>Attempt to open the specified dictionary file using an <code>std::ifstream</code>. If the file fails to open, an error message is displayed, and the function returns false.</li>
  <li>Read passwords from the file one by one, storing them in the <code>password</code> variable.</li>
  <li>For each password, call the <code>checkPassword</code> function to compare the password hash with the <code>targetHash</code>. If a match is found, display the cracked password and return true.</li>
  <li>If no match is found in the entire dictionary, display a message indicating that the password was not found and return false.</li>
</ol>

<pre><code class="cpp">bool crackPassword(const std::string&amp; dictionaryFile, const std::string&amp; targetHash) {
    // ... Dictionary-based attack implementation ...
}
</code></pre>

<h3>Brute-Force Attack</h3>

<p>The <code>performBruteForceAttack</code> function implements a brute-force attack. It takes a <code>targetHash</code> parameter, which represents the hash of the password to crack.</p>

<p>Here's an overview of the steps:</p>

<ol>
  <li>Initialize the <code>password</code> variable with an initial value of "a" and create a string <code>characters</code> containing all possible characters that can be used in the password.</li>
  <li>Enter an infinite loop.</li>
  <li>Check if the current password matches the <code>targetHash</code> by calling the <code>checkPassword</code> function. If a match is found, display the cracked password and return.</li>
  <li>If no match is found, generate the next password permutation by finding the rightmost character in the <code>characters</code> string that matches the last character of the current password. Replace the last character with the next character in <code>characters</code> and continue to the next iteration.</li>
  <li>If all possible password permutations up to a length of 8 characters are exhausted without finding a match, break the loop and display a message indicating that the password was not found.</li>
</ol>

<pre><code class="cpp">void performBruteForceAttack(const std::string&amp; targetHash) {
    // ... Brute-force attack implementation ...
}
</code></pre>

<h3>Main Function</h3>

<p>The <code>main</code> function serves as the entry point of the program. It provides a menu-driven interface for the user to choose between a dictionary-based attack, a brute-force attack, or exiting the program.</p>

<p>Here's an overview of the steps:</p>

<ol>
  <li>Inside the main loop, display the menu options and prompt the user for a choice using <code>std::cin</code>.</li>
  <li>Perform the corresponding action based on the user's input.</li>
  <li>If the user selects the dictionary-based attack (choice 1), prompt for the name of the dictionary file and call the <code>crackPassword</code> function with the provided file name and <code>targetHash</code>.</li>
  <li>If the user selects the brute-force attack (choice 2), prompt for the <code>targetHash</code> and call the <code>performBruteForceAttack</code> function with the provided hash.</li>
  <li>If the user selects to exit the program (choice 3), return, terminating the program.</li>
  <li>If an invalid choice is entered, display an error message, and the loop continues.</li>
</ol>

<pre><code class="cpp">int main() {
    // ... Main function and menu-driven interface ...
}
</code></pre>

<h2>Conclusion</h2>

<p>This code showcases two password-cracking techniques: a dictionary-based attack and a brute-force attack. It provides a menu-driven interface for users to choose the desired attack method or exit the program. The code demonstrates the usage of cryptographic hashing, file I/O, string manipulation, and algorithmic techniques. Feel free to explore and modify the code to suit your needs! 🚀🔒💡</p>
