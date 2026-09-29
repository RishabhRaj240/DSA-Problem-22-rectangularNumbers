🔢 Pattern 22 – Concentric Number Pattern in C++

A C++ program that generates a concentric number pattern using nested loops and boundary-distance calculations. The pattern is symmetrical from all four sides, with the smallest value positioned at the center.

📌 Overview

The program takes an integer n and generates a square pattern with dimensions:

(2 × n - 1) × (2 × n - 1)

Each value is calculated based on the minimum distance of its position from the top, bottom, left, and right boundaries.

For n = 4, the output is:

4444444
4333334
4322234
4321234
4322234
4333334
4444444

The program also supports multiple test cases.

✨ Features
Generates a concentric number pattern.
Creates a symmetrical square structure.
Uses nested for loops.
Calculates distances from four boundaries.
Uses the min() function to determine the nearest boundary.
Supports multiple test cases.
Demonstrates coordinate-based pattern generation.
🛠️ Technologies Used
Technology	Purpose
C++	Programming language
iostream	Input and output
Nested Loops	Pattern generation
min()	Finding minimum boundary distance
📝 Problem Statement

Given an integer n, print a concentric number pattern of size:

(2n - 1) × (2n - 1)

The outermost layer contains the value n. As we move toward the center, the values decrease by 1 for each layer.

For example, when n = 4:

4444444
4333334
4322234
4321234
4322234
4333334
4444444
🧠 Approach

The program traverses a square grid using two nested loops:

for (int i = 0; i < 2 * n - 1; i++) {
    for (int j = 0; j < 2 * n - 1; j++) {

For every position, the distance from each boundary is calculated.

Boundary Calculations
int top = i;
int left = j;
int right = (2 * n - 2) - j;
int down = (2 * n - 2) - i;

The minimum distance is then calculated using:

min(min(top, down), min(left, right))

Finally, the value printed is:

n - minimumDistance

This produces the concentric layers of the pattern.

💻 Source Code
#include <iostream>
using namespace std;

void Pattern22(int n) {
    for (int i = 0; i < 2 * n - 1; i++) {

        for (int j = 0; j < 2 * n - 1; j++) {

            int top = i;
            int left = j;
            int right = (2 * n - 2) - j;
            int down = (2 * n - 2) - i;

            cout << (n - min(min(top, down), min(left, right)));
        }

        cout << endl;
    }
}

int main() {
    int t;
    cin >> t;

    for (int i = 0; i < t; i++) {
        int n;
        cin >> n;
        Pattern22(n);
    }

    return 0;
}
📥 Example Input
2
3
4
📤 Example Output
33333
32223
32123
32223
33333

4444444
4333334
4322234
4321234
4322234
4333334
4444444
▶️ How to Run
1. Clone the repository
git clone <repository-url>
cd <repository-folder>
2. Compile the program
g++ main.cpp -o main
3. Run the program
./main

Windows: Use main.exe instead of ./main.

📚 Learning Concepts

This program demonstrates:

Nested for loops
2D grid traversal
Boundary calculations
Coordinate-based logic
min() function
Mathematical pattern generation
Symmetric pattern construction
Functions in C++
Multiple test cases
Console input/output
⏱️ Complexity Analysis

For a given n, the pattern contains (2n - 1)² positions.

Time Complexity: O(n²)
Auxiliary Space: O(1)

The program processes every position in the square exactly once and does not use additional data structures.

📸 Screenshot

Add your program output screenshot to:

screenshots/output.png

Then include it in the README:

<img width="69" height="141" alt="Screenshot 2026-09-29 at 9 38 33 PM" src="https://github.com/user-attachments/assets/e2e4eed9-3e3a-4cda-8831-6d686fb100f5" />

Recommended project structure:

Pattern22/
│
├── main.cpp
├── README.md
└── screenshots/
    └── output.png
👤 Author

Rishab Raj Chourasia

C++ | Data Structures & Algorithms | Problem Solving
