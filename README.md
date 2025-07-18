# Practice C++

## Phase 1 : Basic Programs : 27 programs [Question_Pdf](Phase_1/phase-1.pdf)

1. Meena face an isuue to perform a mathematical operation to find a cube of any number. Write a C++ Program which helps Meena to solve her issue.

```cpp
#include <iostream>
using namespace std;

int cube(int num)
{
    return num * num * num;
}

int main() {
    int num;
    cout << "Enter a number: ";
    cin >> num;
    cout << "The cube of " << num << " is " << cube(num) << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 3
The cube of 3 is 27
```

2. Sameer is too weak to find multiplication of any three numbers. Write a C++ Program which helps Sameer to solve his issue.

```cpp
#include <iostream>
using namespace std;

int multiply(int a, int b, int c);

int main()
{
    int num1, num2, num3;
    cout << "Enter value num1: ";
    cin >> num1;
    cout << "Enter value num2: ";
    cin >> num2;
    cout << "Enter value num3: ";
    cin >> num3;
    cout << "The multiplication of " << num1 << ", " << num2 << ", and " << num3 << " is " << multiply(num1, num2, num3) << endl;
    return 0;
}

int multiply(int a, int b, int c)
{
    return a * b * c;
}
```

**Output:**

```
Enter value num1: 2
Enter value num2: 3
Enter value num3: 4
The multiplication of 2, 3, and 4 is 24
```

3. A student in a fifth class encounters a very easy math problem to find quotient and remainder. Write a C++ Program which provides a solution for this particular problem.

```cpp
#include <iostream>
using namespace std;

void quotient_remainder(int dividend, int divisor, int &quotient, int &remainder);

int main() {
    int dividend, divisor, quotient, remainder;
    cout << "Enter dividend: ";
    cin >> dividend;
    cout << "Enter divisor: ";
    cin >> divisor;

    quotient_remainder(dividend, divisor, quotient, remainder);

    cout << "Quotient: " << quotient << endl;
    cout << "Remainder: " << remainder << endl;

    return 0;
}

void quotient_remainder(int dividend, int divisor, int &quotient, int &remainder) {
    quotient = dividend / divisor;
    remainder = dividend % divisor;
}
```

**Output:**

```
Enter dividend: 17
Enter divisor: 5
Quotient: 3
Remainder: 2
```

4. Two classmates wants to exchange their seating with each other. But the problem is that there are only two chairs in the small classroom which already aquires by them. Write a C++ Program which provides a solution for this particular problem.

```cpp
#include <iostream>
using namespace std;

void swap(int &a, int &b);

int main()
{
    int a, b;
    cout << "Enter the value of a: ";
    cin >> a;
    cout << "Enter the value of b: ";
    cin >> b;
    cout << "Before swapping: a = " << a << ", b = " << b << endl;
    swap(a, b);
    cout << "After swapping: a = " << a << ", b = " << b << endl;
}
void swap(int &a, int &b)
{
    a = a + b;
    b = a - b;
    a = a - b;
}
```

**Output:**

```
Enter the value of a: 10
Enter the value of b: 20
Before swapping: a = 10, b = 20
After swapping: a = 20, b = 10
```

5. Two college collegues had argue with a ASCII value conversion method. Write a C++ Program which provides a solution for their issue.

```cpp
#include <iostream>
#include <stdio.h>
#include <string.h>
#include <ctype.h>
using namespace std;

void displayMenu();

int main()
{
    int choice;
    do
    {
        displayMenu();

        cout << "Enter your choice: ";
        cin >> choice;
        cin.ignore();

        switch (choice)
        {
        case 1:
        {
            char input[10], letter;

            printf("Enter a single letter: ");
            fgets(input, sizeof(input), stdin);

            if (strlen(input) > 2 || !isalpha(input[0]) || input[1] != '\n')
            {
                cout << "Error: Input must be a single valid alphabet letter." << endl;
                return 1;
            }

            letter = input[0];
            int assci;
            assci = (int)letter;

            cout << "ASCII value of '" << letter << "' is " << assci << endl;
        }
        break;

        case 2:
        {
            int ascii;
            cout << "Enter an ASCII value (0-127): ";
            cin >> ascii;
            cin.ignore();

            if (ascii < 0 || ascii > 127)
            {
                cout << "Error: Please enter a valid ASCII value between 0 and 127." << endl;
                break;
            }

            char letter = static_cast<char>(ascii);
            cout << "Character for ASCII value " << ascii << " is '" << letter << "'" << endl;
            break;
        }
        break;

        case 0:
            cout << "Exiting Proram...";
            break;

        default:
            cout << "Invalid choice...";
            break;
        }
    } while (choice != 0);
}

void displayMenu()
{
    cout << endl;
    cout << "+------------------------------+" << endl;
    cout << "|             Menu             |" << endl;
    cout << "+------------------------------+" << endl;
    cout << "| 1. Character to ASCII value  |" << endl;
    cout << "| 2. ASCII value to Character  |" << endl;
    cout << "| 0. Exit                      |" << endl;
    cout << "+------------------------------+" << endl;
}
```

**Output:**

```
+------------------------------+
|             Menu             |
+------------------------------+
| 1. Character to ASCII value  |
| 2. ASCII value to Character  |
| 0. Exit                      |
+------------------------------+
Enter your choice: 1
Enter a single letter: A
ASCII value of 'A' is 65

+------------------------------+
|             Menu             |
+------------------------------+
| 1. Character to ASCII value  |
| 2. ASCII value to Character  |
| 0. Exit                      |
+------------------------------+
Enter your choice: 2
Enter an ASCII value (0-127): 66
Character for ASCII value 66 is 'B'

+------------------------------+
|             Menu             |
+------------------------------+
| 1. Character to ASCII value  |
| 2. ASCII value to Character  |
| 0. Exit                      |
+------------------------------+
Enter your choice: 0
Exiting Proram...
```

---

6. Write a C++ program to check whether a number is even or odd.

```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    cout << "Enter a number: ";
    cin >> num;
    if (num % 2 == 0)
        cout << num << " is even." << endl;
    else
        cout << num << " is odd." << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 7
7 is odd.
```

---

7. Write a C++ program to find the largest of three numbers.

```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, c;
    cout << "Enter three numbers: ";
    cin >> a >> b >> c;
    int largest = a;
    if (b > largest) largest = b;
    if (c > largest) largest = c;
    cout << "The largest number is " << largest << endl;
    return 0;
}
```

**Output:**

```
Enter three numbers: 5 9 3
The largest number is 9
```

---

8. Write a C++ program to check whether a year is a leap year or not.

```cpp
#include <iostream>
using namespace std;

int main() {
    int year;
    cout << "Enter a year: ";
    cin >> year;
    if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0))
        cout << year << " is a leap year." << endl;
    else
        cout << year << " is not a leap year." << endl;
    return 0;
}
```

**Output:**

```
Enter a year: 2024
2024 is a leap year.
```

---

9. Write a C++ program to find the factorial of a number.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, fact = 1;
    cout << "Enter a number: ";
    cin >> n;
    for (int i = 1; i <= n; i++)
        fact *= i;
    cout << "Factorial of " << n << " is " << fact << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 5
Factorial of 5 is 120
```

---

10. Write a C++ program to print the Fibonacci series up to n terms.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, a = 0, b = 1, next;
    cout << "Enter number of terms: ";
    cin >> n;
    cout << "Fibonacci Series: ";
    for (int i = 1; i <= n; i++) {
        cout << a << " ";
        next = a + b;
        a = b;
        b = next;
    }
    cout << endl;
    return 0;
}
```

**Output:**

```
Enter number of terms: 6
Fibonacci Series: 0 1 1 2 3 5
```

---

11. Write a C++ program to reverse a number.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, rev = 0;
    cout << "Enter a number: ";
    cin >> n;
    while (n != 0) {
        rev = rev * 10 + n % 10;
        n /= 10;
    }
    cout << "Reversed number: " << rev << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 1234
Reversed number: 4321
```

---

12. Write a C++ program to check whether a number is palindrome or not.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, temp, rev = 0;
    cout << "Enter a number: ";
    cin >> n;
    temp = n;
    while (temp != 0) {
        rev = rev * 10 + temp % 10;
        temp /= 10;
    }
    if (n == rev)
        cout << n << " is a palindrome." << endl;
    else
        cout << n << " is not a palindrome." << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 121
121 is a palindrome.
```

---

13. Write a C++ program to check whether a number is prime or not.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, i, flag = 0;
    cout << "Enter a number: ";
    cin >> n;
    if (n <= 1) flag = 1;
    for (i = 2; i <= n / 2; i++) {
        if (n % i == 0) {
            flag = 1;
            break;
        }
    }
    if (flag == 0)
        cout << n << " is a prime number." << endl;
    else
        cout << n << " is not a prime number." << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 7
7 is a prime number.
```

---

14. Write a C++ program to find the sum of digits of a number.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;
    cout << "Enter a number: ";
    cin >> n;
    while (n != 0) {
        sum += n % 10;
        n /= 10;
    }
    cout << "Sum of digits: " << sum << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 1234
Sum of digits: 10
```

---

15. Write a C++ program to swap two numbers using a temporary variable.

```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, temp;
    cout << "Enter two numbers: ";
    cin >> a >> b;
    temp = a;
    a = b;
    b = temp;
    cout << "After swapping: a = " << a << ", b = " << b << endl;
    return 0;
}
```

**Output:**

```
Enter two numbers: 5 9
After swapping: a = 9, b = 5
```

---

16. Write a C++ program to calculate the power of a number.

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    double base, exponent, result;
    cout << "Enter base: ";
    cin >> base;
    cout << "Enter exponent: ";
    cin >> exponent;
    result = pow(base, exponent);
    cout << base << " raised to the power " << exponent << " is " << result << endl;
    return 0;
}
```

**Output:**

```
Enter base: 2
Enter exponent: 3
2 raised to the power 3 is 8
```

---

17. Write a C++ program to find the GCD of two numbers.

```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b;
    cout << "Enter two numbers: ";
    cin >> a >> b;
    int gcd = 1;
    for (int i = 1; i <= a && i <= b; i++) {
        if (a % i == 0 && b % i == 0)
            gcd = i;
    }
    cout << "GCD is " << gcd << endl;
    return 0;
}
```

**Output:**

```
Enter two numbers: 12 18
GCD is 6
```

---

18. Write a C++ program to find the LCM of two numbers.

```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, max;
    cout << "Enter two numbers: ";
    cin >> a >> b;
    max = (a > b) ? a : b;
    while (true) {
        if (max % a == 0 && max % b == 0) {
            cout << "LCM is " << max << endl;
            break;
        }
        ++max;
    }
    return 0;
}
```

**Output:**

```
Enter two numbers: 4 6
LCM is 12
```

---

19. Write a C++ program to print all factors of a number.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter a number: ";
    cin >> n;
    cout << "Factors of " << n << " are: ";
    for (int i = 1; i <= n; i++) {
        if (n % i == 0)
            cout << i << " ";
    }
    cout << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 12
Factors of 12 are: 1 2 3 4 6 12
```

---

20. Write a C++ program to count the number of digits in a number.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, count = 0;
    cout << "Enter a number: ";
    cin >> n;
    while (n != 0) {
        n /= 10;
        count++;
    }
    cout << "Number of digits: " << count << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 12345
Number of digits: 5
```

---

21. Write a C++ program to check whether a character is a vowel or consonant.

```cpp
#include <iostream>
using namespace std;

int main() {
    char ch;
    cout << "Enter a character: ";
    cin >> ch;
    if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u' ||
        ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U')
        cout << ch << " is a vowel." << endl;
    else
        cout << ch << " is a consonant." << endl;
    return 0;
}
```

**Output:**

```
Enter a character: e
e is a vowel.
```

---

22. Write a C++ program to find the ASCII value of a character.

```cpp
#include <iostream>
using namespace std;

int main() {
    char ch;
    cout << "Enter a character: ";
    cin >> ch;
    cout << "ASCII value of " << ch << " is " << int(ch) << endl;
    return 0;
}
```

**Output:**

```
Enter a character: A
ASCII value of A is 65
```

---

23. Write a C++ program to convert temperature from Celsius to Fahrenheit.

```cpp
#include <iostream>
using namespace std;

int main() {
    float celsius, fahrenheit;
    cout << "Enter temperature in Celsius: ";
    cin >> celsius;
    fahrenheit = (celsius * 9 / 5) + 32;
    cout << "Temperature in Fahrenheit: " << fahrenheit << endl;
    return 0;
}
```

**Output:**

```
Enter temperature in Celsius: 37
Temperature in Fahrenheit: 98.6
```

---

24. Write a C++ program to convert temperature from Fahrenheit to Celsius.

```cpp
#include <iostream>
using namespace std;

int main() {
    float fahrenheit, celsius;
    cout << "Enter temperature in Fahrenheit: ";
    cin >> fahrenheit;
    celsius = (fahrenheit - 32) * 5 / 9;
    cout << "Temperature in Celsius: " << celsius << endl;
    return 0;
}
```

**Output:**

```
Enter temperature in Fahrenheit: 98.6
Temperature in Celsius: 37
```

---

25. Write a C++ program to calculate the sum of the first n natural numbers.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;
    cout << "Enter n: ";
    cin >> n;
    for (int i = 1; i <= n; i++)
        sum += i;
    cout << "Sum of first " << n << " natural numbers is " << sum << endl;
    return 0;
}
```

**Output:**

```
Enter n: 10
Sum of first 10 natural numbers is 55
```

---

26. Write a C++ program to print multiplication table of a number.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter a number: ";
    cin >> n;
    cout << "Multiplication table of " << n << ":" << endl;
    for (int i = 1; i <= 10; i++)
        cout << n << " x " << i << " = " << n * i << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 5
Multiplication table of 5:
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

---

27. Write a C++ program to print all even numbers between 1 and n.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter n: ";
    cin >> n;
    cout << "Even numbers between 1 and " << n << ": ";
    for (int i = 2; i <= n; i += 2)
        cout << i << " ";
    cout << endl;
    return 0;
}
```

**Output:**

```
Enter n: 10
Even numbers between 1 and 10: 2 4 6 8 10
```

## Phase 2 : Numerical Programs : 15 programs [Question_Pdf](Phase_2/phase-2.pdf)

1. Write a C++ program to check whether a number is positive, negative or zero.

```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    cout << "Enter a number: ";
    cin >> num;
    if (num > 0)
        cout << num << " is positive." << endl;
    else if (num < 0)
        cout << num << " is negative." << endl;
    else
        cout << "The number is zero." << endl;
    return 0;
}
```

**Output:**

```
Enter a number: -5
-5 is negative.
```

---

2. Write a C++ program to check whether a number is divisible by 5 and 11 or not.

```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    cout << "Enter a number: ";
    cin >> num;
    if (num % 5 == 0 && num % 11 == 0)
        cout << num << " is divisible by both 5 and 11." << endl;
    else
        cout << num << " is not divisible by both 5 and 11." << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 55
55 is divisible by both 5 and 11.
```

---

3. Write a C++ program to find the sum of all even numbers between 1 and n.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;
    cout << "Enter n: ";
    cin >> n;
    for (int i = 2; i <= n; i += 2)
        sum += i;
    cout << "Sum of even numbers between 1 and " << n << " is " << sum << endl;
    return 0;
}
```

**Output:**

```
Enter n: 10
Sum of even numbers between 1 and 10 is 30
```

---

4. Write a C++ program to find the sum of all odd numbers between 1 and n.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;
    cout << "Enter n: ";
    cin >> n;
    for (int i = 1; i <= n; i += 2)
        sum += i;
    cout << "Sum of odd numbers between 1 and " << n << " is " << sum << endl;
    return 0;
}
```

**Output:**

```
Enter n: 10
Sum of odd numbers between 1 and 10 is 25
```

---

5. Write a C++ program to find the sum of the series 1 + 2 + 3 + ... + n.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;
    cout << "Enter n: ";
    cin >> n;
    for (int i = 1; i <= n; i++)
        sum += i;
    cout << "Sum of the series is " << sum << endl;
    return 0;
}
```

**Output:**

```
Enter n: 5
Sum of the series is 15
```

---

6. Write a C++ program to find the sum of the series 1^2 + 2^2 + 3^2 + ... + n^2.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;
    cout << "Enter n: ";
    cin >> n;
    for (int i = 1; i <= n; i++)
        sum += i * i;
    cout << "Sum of the series is " << sum << endl;
    return 0;
}
```

**Output:**

```
Enter n: 3
Sum of the series is 14
```

---

7. Write a C++ program to find the sum of the series 1^3 + 2^3 + 3^3 + ... + n^3.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;
    cout << "Enter n: ";
    cin >> n;
    for (int i = 1; i <= n; i++)
        sum += i * i * i;
    cout << "Sum of the series is " << sum << endl;
    return 0;
}
```

**Output:**

```
Enter n: 3
Sum of the series is 36
```

---

8. Write a C++ program to find the sum of digits of a given number.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;
    cout << "Enter a number: ";
    cin >> n;
    while (n != 0) {
        sum += n % 10;
        n /= 10;
    }
    cout << "Sum of digits is " << sum << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 1234
Sum of digits is 10
```

---

9. Write a C++ program to reverse a given number.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, rev = 0;
    cout << "Enter a number: ";
    cin >> n;
    while (n != 0) {
        rev = rev * 10 + n % 10;
        n /= 10;
    }
    cout << "Reversed number is " << rev << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 1234
Reversed number is 4321
```

---

10. Write a C++ program to check whether a number is a palindrome or not.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, temp, rev = 0;
    cout << "Enter a number: ";
    cin >> n;
    temp = n;
    while (temp != 0) {
        rev = rev * 10 + temp % 10;
        temp /= 10;
    }
    if (n == rev)
        cout << n << " is a palindrome." << endl;
    else
        cout << n << " is not a palindrome." << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 121
121 is a palindrome.
```

---

11. Write a C++ program to check whether a number is an Armstrong number or not.

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    int n, temp, sum = 0, digits = 0;
    cout << "Enter a number: ";
    cin >> n;
    temp = n;
    while (temp != 0) {
        digits++;
        temp /= 10;
    }
    temp = n;
    while (temp != 0) {
        sum += pow(temp % 10, digits);
        temp /= 10;
    }
    if (sum == n)
        cout << n << " is an Armstrong number." << endl;
    else
        cout << n << " is not an Armstrong number." << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 153
153 is an Armstrong number.
```

---

12. Write a C++ program to print all Armstrong numbers between 1 and n.

```cpp
#include <iostream>
#include <cmath>
using namespace std;

bool isArmstrong(int num) {
    int temp = num, sum = 0, digits = 0;
    while (temp != 0) {
        digits++;
        temp /= 10;
    }
    temp = num;
    while (temp != 0) {
        sum += pow(temp % 10, digits);
        temp /= 10;
    }
    return sum == num;
}

int main() {
    int n;
    cout << "Enter n: ";
    cin >> n;
    cout << "Armstrong numbers between 1 and " << n << ": ";
    for (int i = 1; i <= n; i++) {
        if (isArmstrong(i))
            cout << i << " ";
    }
    cout << endl;
    return 0;
}
```

**Output:**

```
Enter n: 500
Armstrong numbers between 1 and 500: 1 2 3 4 5 6 7 8 9 153 370 371 407
```

---

13. Write a C++ program to check whether a number is a perfect number or not.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;
    cout << "Enter a number: ";
    cin >> n;
    for (int i = 1; i < n; i++) {
        if (n % i == 0)
            sum += i;
    }
    if (sum == n)
        cout << n << " is a perfect number." << endl;
    else
        cout << n << " is not a perfect number." << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 28
28 is a perfect number.
```

---

14. Write a C++ program to print all perfect numbers between 1 and n.

```cpp
#include <iostream>
using namespace std;

bool isPerfect(int n) {
    int sum = 0;
    for (int i = 1; i < n; i++) {
        if (n % i == 0)
            sum += i;
    }
    return sum == n;
}

int main() {
    int n;
    cout << "Enter n: ";
    cin >> n;
    cout << "Perfect numbers between 1 and " << n << ": ";
    for (int i = 1; i <= n; i++) {
        if (isPerfect(i))
            cout << i << " ";
    }
    cout << endl;
    return 0;
}
```

**Output:**

```
Enter n: 1000
Perfect numbers between 1 and 1000: 6 28 496
```

---

15. Write a C++ program to check whether a number is a strong number or not.

```cpp
#include <iostream>
using namespace std;

int factorial(int n) {
    int fact = 1;
    for (int i = 1; i <= n; i++)
        fact *= i;
    return fact;
}

int main() {
    int n, temp, sum = 0;
    cout << "Enter a number: ";
    cin >> n;
    temp = n;
    while (temp != 0) {
        sum += factorial(temp % 10);
        temp /= 10;
    }
    if (sum == n)
        cout << n << " is a strong number." << endl;
    else
        cout << n << " is not a strong number." << endl;
    return 0;
}
```

**Output:**

```
Enter a number: 145
145 is a strong number.
```

---

## Phase 3 : String Programs : 10 programs [Question_Pdf](Phase_3/phase-3.pdf)

1. Write a C++ program to sort an array using bubble sort.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    int arr[100];
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++)
        cin >> arr[i];
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;
    return 0;
}
```

**Output:**

```
Enter number of elements: 5
Enter elements: 4 2 5 1 3
Sorted array: 1 2 3 4 5
```

---

2. Write a C++ program to search an element in an array using linear search.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, key, found = 0;
    cout << "Enter number of elements: ";
    cin >> n;
    int arr[100];
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++)
        cin >> arr[i];
    cout << "Enter element to search: ";
    cin >> key;
    for (int i = 0; i < n; i++) {
        if (arr[i] == key) {
            found = 1;
            break;
        }
    }
    if (found)
        cout << key << " is found in the array." << endl;
    else
        cout << key << " is not found in the array." << endl;
    return 0;
}
```

**Output:**

```
Enter number of elements: 5
Enter elements: 1 2 3 4 5
Enter element to search: 3
3 is found in the array.
```

---

3. Write a C++ program to find the transpose of a matrix.

```cpp
#include <iostream>
using namespace std;

int main() {
    int r, c;
    cout << "Enter rows and columns: ";
    cin >> r >> c;
    int mat[10][10], trans[10][10];
    cout << "Enter matrix elements:\n";
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            cin >> mat[i][j];
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            trans[j][i] = mat[i][j];
    cout << "Transpose of the matrix:\n";
    for (int i = 0; i < c; i++) {
        for (int j = 0; j < r; j++)
            cout << trans[i][j] << " ";
        cout << endl;
    }
    return 0;
}
```

**Output:**

```
Enter rows and columns: 2 3
Enter matrix elements:
1 2 3
4 5 6
Transpose of the matrix:
1 4
2 5
3 6
```

---

4. Write a C++ program to multiply two matrices.

```cpp
#include <iostream>
using namespace std;

int main() {
    int r1, c1, r2, c2;
    cout << "Enter rows and columns of first matrix: ";
    cin >> r1 >> c1;
    cout << "Enter rows and columns of second matrix: ";
    cin >> r2 >> c2;
    if (c1 != r2) {
        cout << "Matrix multiplication not possible." << endl;
        return 0;
    }
    int a[10][10], b[10][10], prod[10][10] = {0};
    cout << "Enter first matrix:\n";
    for (int i = 0; i < r1; i++)
        for (int j = 0; j < c1; j++)
            cin >> a[i][j];
    cout << "Enter second matrix:\n";
    for (int i = 0; i < r2; i++)
        for (int j = 0; j < c2; j++)
            cin >> b[i][j];
    for (int i = 0; i < r1; i++)
        for (int j = 0; j < c2; j++)
            for (int k = 0; k < c1; k++)
                prod[i][j] += a[i][k] * b[k][j];
    cout << "Product matrix:\n";
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++)
            cout << prod[i][j] << " ";
        cout << endl;
    }
    return 0;
}
```

**Output:**

```
Enter rows and columns of first matrix: 2 3
Enter rows and columns of second matrix: 3 2
Enter first matrix:
1 2 3
4 5 6
Enter second matrix:
7 8
9 10
11 12
Product matrix:
58 64
139 154
```

---

5. Write a C++ program to find the sum of each row and column of a matrix.

```cpp
#include <iostream>
using namespace std;

int main() {
    int r, c;
    cout << "Enter rows and columns: ";
    cin >> r >> c;
    int mat[10][10];
    cout << "Enter matrix elements:\n";
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            cin >> mat[i][j];
    cout << "Sum of each row:\n";
    for (int i = 0; i < r; i++) {
        int sum = 0;
        for (int j = 0; j < c; j++)
            sum += mat[i][j];
        cout << "Row " << i + 1 << ": " << sum << endl;
    }
    cout << "Sum of each column:\n";
    for (int j = 0; j < c; j++) {
        int sum = 0;
        for (int i = 0; i < r; i++)
            sum += mat[i][j];
        cout << "Column " << j + 1 << ": " << sum << endl;
    }
    return 0;
}
```

**Output:**

```
Enter rows and columns: 2 2
Enter matrix elements:
1 2
3 4
Sum of each row:
Row 1: 3
Row 2: 7
Sum of each column:
Column 1: 4
Column 2: 6
```

---

6. Write a C++ program to find the largest element in an array.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, max;
    cout << "Enter number of elements: ";
    cin >> n;
    int arr[100];
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++)
        cin >> arr[i];
    max = arr[0];
    for (int i = 1; i < n; i++)
        if (arr[i] > max)
            max = arr[i];
    cout << "Largest element is " << max << endl;
    return 0;
}
```

**Output:**

```
Enter number of elements: 5
Enter elements: 2 8 1 6 4
Largest element is 8
```

---

7. Write a C++ program to reverse an array.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    int arr[100];
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++)
        cin >> arr[i];
    cout << "Reversed array: ";
    for (int i = n - 1; i >= 0; i--)
        cout << arr[i] << " ";
    cout << endl;
    return 0;
}
```

**Output:**

```
Enter number of elements: 4
Enter elements: 1 2 3 4
Reversed array: 4 3 2 1
```

---

8. Write a C++ program to merge two arrays.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n1, n2;
    cout << "Enter size of first array: ";
    cin >> n1;
    int arr1[100];
    cout << "Enter elements of first array: ";
    for (int i = 0; i < n1; i++)
        cin >> arr1[i];
    cout << "Enter size of second array: ";
    cin >> n2;
    int arr2[100];
    cout << "Enter elements of second array: ";
    for (int i = 0; i < n2; i++)
        cin >> arr2[i];
    int arr3[200];
    for (int i = 0; i < n1; i++)
        arr3[i] = arr1[i];
    for (int i = 0; i < n2; i++)
        arr3[n1 + i] = arr2[i];
    cout << "Merged array: ";
    for (int i = 0; i < n1 + n2; i++)
        cout << arr3[i] << " ";
    cout << endl;
    return 0;
}
```

**Output:**

```
Enter size of first array: 3
Enter elements of first array: 1 2 3
Enter size of second array: 2
Enter elements of second array: 4 5
Merged array: 1 2 3 4 5
```

---

9. Write a C++ program to count the frequency of each element in an array.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    int arr[100], freq[100] = {0};
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++)
        cin >> arr[i];
    for (int i = 0; i < n; i++) {
        if (freq[i] == -1)
            continue;
        int count = 1;
        for (int j = i + 1; j < n; j++) {
            if (arr[i] == arr[j]) {
                count++;
                freq[j] = -1;
            }
        }
        freq[i] = count;
    }
    cout << "Frequency of each element:\n";
    for (int i = 0; i < n; i++) {
        if (freq[i] != -1)
            cout << arr[i] << ": " << freq[i] << endl;
    }
    return 0;
}
```

**Output:**

```
Enter number of elements: 6
Enter elements: 1 2 2 3 3 3
Frequency of each element:
1: 1
2: 2
3: 3
```

---

10. Write a C++ program to copy one array to another.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    int arr1[100], arr2[100];
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++)
        cin >> arr1[i];
    for (int i = 0; i < n; i++)
        arr2[i] = arr1[i];
    cout << "Copied array: ";
    for (int i = 0; i < n; i++)
        cout << arr2[i] << " ";
    cout << endl;
    return 0;
}
```

**Output:**

```
Enter number of elements: 4
Enter elements: 5 6
```

---

11. Write a C++ program to check whether a number is an Armstrong number or not.

```cpp
#include <iostream>
#include <string>
using namespace std;

int main()
{
    string msg;
    int shift;
    int choice;
    cout << "Enter the message: ";
    cin >> msg;
    cout << "Enter shift value: ";
    cin >> shift;
    cout << "1. Encode\n2. Decode\nEnter choice: ";
    cin >> choice;
    string result = msg;
    if (choice == 1)
    {
        for (char &c : result)
        {
            c += shift;
        }
    }
    else if (choice == 2)
    {
        for (char &c : result)
        {
            c -= shift;
        }
    }
    else
    {
        cout << "Invalid choice\n";
        return 0;
    }
    cout << "Result: " << result << endl;
    return 0;
}

```

**Output:**

```
Enter a number: 153
153 is an Armstrong number.
```

---

## Phase 5 : Functional Programs : 10 programs [Question_Pdf](Phase_5/phase-5.pdf)

1. Write a C++ program to check if a string is a palindrome.

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string str, rev;
    cout << "Enter a string: ";
    cin >> str;
    rev = string(str.rbegin(), str.rend());
    if (str == rev)
        cout << str << " is a palindrome." << endl;
    else
        cout << str << " is not a palindrome." << endl;
    return 0;
}
```

**Output:**

```
Enter a string: madam
madam is a palindrome.
```

---

2. Write a C++ program to count vowels and consonants in a string.

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string str;
    int vowels = 0, consonants = 0;
    cout << "Enter a string: ";
    cin >> str;
    for (char c : str) {
        c = tolower(c);
        if (isalpha(c)) {
            if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u')
                vowels++;
            else
                consonants++;
        }
    }
    cout << "Vowels: " << vowels << endl;
    cout << "Consonants: " << consonants << endl;
    return 0;
}
```

**Output:**

```
Enter a string: Hello
Vowels: 2
Consonants: 3
```

---

3. Write a C++ program to implement a stack using an array.

```cpp
#include <iostream>
using namespace std;

#define MAX 100

int stack[MAX], top = -1;

void push(int val) {
    if (top >= MAX - 1)
        cout << "Stack Overflow" << endl;
    else
        stack[++top] = val;
}

void pop() {
    if (top < 0)
        cout << "Stack Underflow" << endl;
    else
        top--;
}

void display() {
    if (top < 0)
        cout << "Stack is empty" << endl;
    else {
        cout << "Stack: ";
        for (int i = 0; i <= top; i++)
            cout << stack[i] << " ";
        cout << endl;
    }
}

int main() {
    push(10);
    push(20);
    display();
    pop();
    display();
    return 0;
}
```

**Output:**

```
Stack: 10 20
Stack: 10
```

---

4. Write a C++ program to implement a queue using an array.

```cpp
#include <iostream>
using namespace std;

#define MAX 100

int queue[MAX], front = -1, rear = -1;

void enqueue(int val) {
    if (rear == MAX - 1)
        cout << "Queue Overflow" << endl;
    else {
        if (front == -1) front = 0;
        queue[++rear] = val;
    }
}

void dequeue() {
    if (front == -1 || front > rear)
        cout << "Queue Underflow" << endl;
    else
        front++;
}

void display() {
    if (front == -1 || front > rear)
        cout << "Queue is empty" << endl;
    else {
        cout << "Queue: ";
        for (int i = front; i <= rear; i++)
            cout << queue[i] << " ";
        cout << endl;
    }
}

int main() {
    enqueue(5);
    enqueue(15);
    display();
    dequeue();
    display();
    return 0;
}
```

**Output:**

```
Queue: 5 15
Queue: 15
```

---

5. Write a C++ program to find the frequency of characters in a string.

```cpp
#include <iostream>
#include <string>
#include <map>
using namespace std;

int main() {
    string str;
    map<char, int> freq;
    cout << "Enter a string: ";
    cin >> str;
    for (char c : str)
        freq[c]++;
    for (auto p : freq)
        cout << p.first << ": " << p.second << endl;
    return 0;
}
```

**Output:**

```
Enter a string: apple
a: 1
e: 1
l: 1
p: 2
```

---

6. Write a C++ program to reverse a linked list.

```cpp
#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
};

Node* reverse(Node* head) {
    Node* prev = nullptr;
    Node* curr = head;
    while (curr) {
        Node* next = curr->next;
        curr->next = prev;
        prev = curr;
        curr = next;
    }
    return prev;
}

void printList(Node* head) {
    while (head) {
        cout << head->data << " ";
        head = head->next;
    }
    cout << endl;
}

int main() {
    Node* head = new Node{1, new Node{2, new Node{3, nullptr}}};
    head = reverse(head);
    printList(head);
    return 0;
}
```

**Output:**

```
3 2 1
```

---

7. Write a C++ program to concatenate two strings without using library functions.

```cpp
#include <iostream>
using namespace std;

int main() {
    char str1[100], str2[100], result[200];
    cout << "Enter first string: ";
    cin >> str1;
    cout << "Enter second string: ";
    cin >> str2;
    int i = 0, j = 0;
    while (str1[i] != '\0') {
        result[i] = str1[i];
        i++;
    }
    while (str2[j] != '\0') {
        result[i++] = str2[j++];
    }
    result[i] = '\0';
    cout << "Concatenated string: " << result << endl;
    return 0;
}
```

**Output:**

```
Enter first string: Hello
Enter second string: World
Concatenated string: HelloWorld
```

---

8. Write a C++ program to find the length of a string without using library functions.

```cpp
#include <iostream>
using namespace std;

int main() {
    char str[100];
    int length = 0;
    cout << "Enter a string: ";
    cin >> str;
    while (str[length] != '\0')
        length++;
    cout << "Length of the string: " << length << endl;
    return 0;
}
```

**Output:**

```
Enter a string: OpenAI
Length of the string: 6
```

---

9. Write a C++ program to implement a simple calculator using switch case.

```cpp
#include <iostream>
using namespace std;

int main() {
    char op;
    float num1, num2;
    cout << "Enter operator (+, -, *, /): ";
    cin >> op;
    cout << "Enter two operands: ";
    cin >> num1 >> num2;
    switch (op) {
        case '+': cout << num1 + num2 << endl; break;
        case '-': cout << num1 - num2 << endl; break;
        case '*': cout << num1 * num2 << endl; break;
        case '/': cout << num2 != 0 ? num1 / num2 : 0 << endl; break;
        default: cout << "Invalid operator" << endl;
    }
    return 0;
}
```

**Output:**

```
Enter operator (+, -, *, /): *
Enter two operands: 4 5
20
```

---

10. Write a C++ program to check if two strings are anagrams.

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    string str1, str2;
    cout << "Enter first string: ";
    cin >> str1;
    cout << "Enter second string: ";
    cin >> str2;
    string s1 = str1, s2 = str2;
    sort(s1.begin(), s1.end());
    sort(s2.begin(), s2.end());
    if (s1 == s2)
        cout << "Anagrams" << endl;
    else
        cout << "Not anagrams" << endl;
    return 0;
}
```

**Output:**

```
Enter first string: listen
Enter second string: silent
Anagrams
```

---

## Phase 6 : OOP Programs : 10 programs [Question_Pdf](Phase_6/phase-6.pdf)

1. Write a C++ program to implement binary search on a sorted array.

```cpp
#include <iostream>
using namespace std;

int binarySearch(int arr[], int n, int key) {
    int left = 0, right = n - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == key)
            return mid;
        else if (arr[mid] < key)
            left = mid + 1;
        else
            right = mid - 1;
    }
    return -1;
}

int main() {
    int n, key;
    cout << "Enter number of elements: ";
    cin >> n;
    int arr[100];
    cout << "Enter sorted elements: ";
    for (int i = 0; i < n; i++)
        cin >> arr[i];
    cout << "Enter element to search: ";
    cin >> key;
    int result = binarySearch(arr, n, key);
    if (result != -1)
        cout << key << " found at index " << result << endl;
    else
        cout << key << " not found in the array." << endl;
    return 0;
}
```

**Output:**
```
Enter number of elements: 5
Enter sorted elements: 1 3 5 7 9
Enter element to search: 7
7 found at index 3
```

---

2. Write a C++ program to implement selection sort.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    int arr[100];
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++)
        cin >> arr[i];
    for (int i = 0; i < n - 1; i++) {
        int minIdx = i;
        for (int j = i + 1; j < n; j++)
            if (arr[j] < arr[minIdx])
                minIdx = j;
        int temp = arr[i];
        arr[i] = arr[minIdx];
        arr[minIdx] = temp;
    }
    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;
    return 0;
}
```

**Output:**
```
Enter number of elements: 5
Enter elements: 4 2 5 1 3
Sorted array: 1 2 3 4 5
```

---

3. Write a C++ program to implement insertion sort.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    int arr[100];
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++)
        cin >> arr[i];
    for (int i = 1; i < n; i++) {
        int key = arr[i], j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;
    return 0;
}
```

**Output:**
```
Enter number of elements: 5
Enter elements: 4 2 5 1 3
Sorted array: 1 2 3 4 5
```

---

4. Write a C++ program to implement quick sort.

```cpp
#include <iostream>
using namespace std;

void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pivot = arr[high], i = low - 1;
        for (int j = low; j < high; j++) {
            if (arr[j] < pivot) {
                i++;
                swap(arr[i], arr[j]);
            }
        }
        swap(arr[i + 1], arr[high]);
        int pi = i + 1;
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    int arr[100];
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++)
        cin >> arr[i];
    quickSort(arr, 0, n - 1);
    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;
    return 0;
}
```

**Output:**
```
Enter number of elements: 5
Enter elements: 4 2 5 1 3
Sorted array: 1 2 3 4 5
```

---

5. Write a C++ program to implement merge sort.

```cpp
#include <iostream>
using namespace std;

void merge(int arr[], int l, int m, int r) {
    int n1 = m - l + 1, n2 = r - m;
    int L[100], R[100];
    for (int i = 0; i < n1; i++)
        L[i] = arr[l + i];
    for (int j = 0; j < n2; j++)
        R[j] = arr[m + 1 + j];
    int i = 0, j = 0, k = l;
    while (i < n1 && j < n2) {
        if (L[i] <= R[j])
            arr[k++] = L[i++];
        else
            arr[k++] = R[j++];
    }
    while (i < n1)
        arr[k++] = L[i++];
    while (j < n2)
        arr[k++] = R[j++];
}

void mergeSort(int arr[], int l, int r) {
    if (l < r) {
        int m = l + (r - l) / 2;
        mergeSort(arr, l, m);
        mergeSort(arr, m + 1, r);
        merge(arr, l, m, r);
    }
}

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    int arr[100];
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++)
        cin >> arr[i];
    mergeSort(arr, 0, n - 1);
    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;
    return 0;
}
```

**Output:**
```
Enter number of elements: 5
Enter elements: 4 2 5 1 3
Sorted array: 1 2 3 4 5
```

---

6. Write a C++ program to implement a circular queue using an array.

```cpp
#include <iostream>
using namespace std;

#define MAX 5

class CircularQueue {
    int arr[MAX], front, rear, count;
public:
    CircularQueue() : front(0), rear(-1), count(0) {}
    void enqueue(int val) {
        if (count == MAX)
            cout << "Queue Overflow" << endl;
        else {
            rear = (rear + 1) % MAX;
            arr[rear] = val;
            count++;
        }
    }
    void dequeue() {
        if (count == 0)
            cout << "Queue Underflow" << endl;
        else {
            front = (front + 1) % MAX;
            count--;
        }
    }
    void display() {
        if (count == 0)
            cout << "Queue is empty" << endl;
        else {
            cout << "Queue: ";
            for (int i = 0; i < count; i++)
                cout << arr[(front + i) % MAX] << " ";
            cout << endl;
        }
    }
};

int main() {
    CircularQueue q;
    q.enqueue(10);
    q.enqueue(20);
    q.enqueue(30);
    q.display();
    q.dequeue();
    q.display();
    return 0;
}
```

**Output:**
```
Queue: 10 20 30
Queue: 20 30
```

---

7. Write a C++ program to implement a singly linked list and perform insertion and deletion.

```cpp
#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
};

void insertFront(Node*& head, int val) {
    Node* temp = new Node{val, head};
    head = temp;
}

void deleteFront(Node*& head) {
    if (head) {
        Node* temp = head;
        head = head->next;
        delete temp;
    }
}

void display(Node* head) {
    while (head) {
        cout << head->data << " ";
        head = head->next;
    }
    cout << endl;
}

int main() {
    Node* head = nullptr;
    insertFront(head, 10);
    insertFront(head, 20);
    insertFront(head, 30);
    display(head);
    deleteFront(head);
    display(head);
    return 0;
}
```

**Output:**
```
30 20 10
20 10
```

---

8. Write a C++ program to implement a doubly linked list and perform insertion and deletion.

```cpp
#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* prev;
    Node* next;
};

void insertFront(Node*& head, int val) {
    Node* temp = new Node{val, nullptr, head};
    if (head)
        head->prev = temp;
    head = temp;
}

void deleteFront(Node*& head) {
    if (head) {
        Node* temp = head;
        head = head->next;
        if (head)
            head->prev = nullptr;
        delete temp;
    }
}

void display(Node* head) {
    while (head) {
        cout << head->data << " ";
        head = head->next;
    }
    cout << endl;
}

int main() {
    Node* head = nullptr;
    insertFront(head, 10);
    insertFront(head, 20);
    insertFront(head, 30);
    display(head);
    deleteFront(head);
    display(head);
    return 0;
}
```

**Output:**
```
30 20 10
20 10
```

---

9. Write a C++ program to implement a stack using a linked list.

```cpp
#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
};

void push(Node*& top, int val) {
    Node* temp = new Node{val, top};
    top = temp;
}

void pop(Node*& top) {
    if (top) {
        Node* temp = top;
        top = top->next;
        delete temp;
    }
}

void display(Node* top) {
    while (top) {
        cout << top->data << " ";
        top = top->next;
    }
    cout << endl;
}

int main() {
    Node* top = nullptr;
    push(top, 10);
    push(top, 20);
    display(top);
    pop(top);
    display(top);
    return 0;
}
```

**Output:**
```
20 10
10
```

---

10. Write a C++ program to implement a queue using a linked list.

```cpp
#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
};

void enqueue(Node*& front, Node*& rear, int val) {
    Node* temp = new Node{val, nullptr};
    if (!rear) {
        front = rear = temp;
    } else {
        rear->next = temp;
        rear = temp;
    }
}

void dequeue(Node*& front, Node*& rear) {
    if (front) {
        Node* temp = front;
        front = front->next;
        if (!front)
            rear = nullptr;
        delete temp;
    }
}

void display(Node* front) {
    while (front) {
        cout << front->data << " ";
        front = front->next;
    }
    cout << endl;
}

int main() {
    Node* front = nullptr;
    Node* rear = nullptr;
    enqueue(front, rear, 10);
    enqueue(front, rear, 20);
    display(front);
    dequeue(front, rear);
    display(front);
    return 0;
}
```

**Output:**
```
10 20
20
```

---
