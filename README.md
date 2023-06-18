Code Overview
The code starts by including several necessary libraries using code tags:

cpp

#include <iostream>
#include <fstream>
#include <string>
#include <algorithm>
#include <sstream>
#include <iomanip>
#include <openssl/sha.h>
  
Hashing Function
  
The sha256 function is responsible for calculating the SHA-256 hash of a given input string. It takes a std::string parameter str and performs the necessary steps to compute the hash. Here's an overview:

Initialize an array hash to store the resulting hash.
  
Initialize a SHA-256 context sha256.
  
Update the context with the input string's content using SHA256_Update.
  
Retrieve the hash value into the hash array using SHA256_Final.
  
Convert the hash into a string representation using std::stringstream.
  

std::string sha256(const std::string& str) {
    // ... SHA-256 hashing implementation ...
}
  
Password Checking
  
The checkPassword function compares a provided password with a target hash. It calls the sha256 function to calculate the hash of the password and then checks if it matches the targetHash string. If the password hash matches the target hash, the function returns true; otherwise, it returns false.

bool checkPassword(const std::string& password, const std::string& targetHash) {
    // ... Password checking implementation ...
}
  
Dictionary-Based Attack
  
The crackPassword function implements a dictionary-based attack. It takes two parameters: dictionaryFile, which represents the name of a file containing a list of passwords to try, and targetHash, which is the hash of the password we want to crack.

Here's an overview of the steps:

Attempt to open the specified dictionary file using an std::ifstream. If the file fails to open, an error message is displayed, and the function returns false.
  
Read passwords from the file one by one, storing them in the password variable.
  
For each password, call the checkPassword function to compare the password hash with the targetHash. If a match is found, display the cracked password and return true.
  
If no match is found in the entire dictionary, display a message indicating that the password was not found and return false.

bool crackPassword(const std::string& dictionaryFile, const std::string& targetHash) {
    // ... Dictionary-based attack implementation ...
}
  
Brute-Force Attack
  
The performBruteForceAttack function implements a brute-force attack. It takes a targetHash parameter, which represents the hash of the password to crack.

Here's an overview of the steps:

Initialize the password variable with an initial value of "a" and create a string characters containing all possible characters that can be used in the password.
  
Enter an infinite loop.
  
Check if the current password matches the targetHash by calling the checkPassword function. If a match is found, display the cracked password and return.
  
If no match is found, generate the next password permutation by finding the rightmost character in the characters string that matches the last character of the current password. Replace the last character with the next character in characters and continue to the next iteration.
  
If all possible password permutations up to a length of 8 characters are exhausted without finding a match, break the loop and display a message indicating that the password was not found.
  

void performBruteForceAttack(const std::string& targetHash) {
    // ... Brute-force attack implementation ...
}
  
Main Function
  
The main function serves as the entry point of the program. It provides a menu-driven interface for the user to choose between a dictionary-based attack, a brute-force attack, or exiting the program.

Here's an overview of the steps:

Inside the main loop, display the menu options and prompt the user for a choice using std::cin.
Perform the corresponding action based on the user's input.
  
If the user selects the dictionary-based attack (choice 1), prompt for the name of the dictionary file and call the crackPassword function with the provided file name and targetHash.
  
If the user selects the brute-force attack (choice 2), prompt for the target hash and call the performBruteForceAttack function with the provided hash.
  
If the user selects to exit the program (choice 3), return, terminating the program.
If an invalid choice is entered, display an error message, and the loop continues.

int main() {
    // ... Main function and menu-driven interface ...
}
Conclusion
  
This code showcases two password-cracking techniques: a dictionary-based attack and a brute-force attack. It provides a menu-driven interface for users to choose the desired attack method or exit the program. The code demonstrates the usage of cryptographic hashing, file I/O, string manipulation, and algorithmic techniques. Feel free to explore and modify the code to suit your needs! 🚀🔒💡
