# Programming tasks with provided solutions in C language.

### Task #1 - Focusing on: Basic console input & output, Understanding arithmetic operations.<br>

Write a short program that asks for your height in feet and inches and your weight in pounds. (Use three variables to store the information.)<br>
Have the program report your body mass index (BMI). To calculate the BMI, first convert your height in feet and inches to your height in inches (1 foot = 12 inches).
Then convert your height in inches to your height in meters by multiplying it by 0.0254. Then convert your weight in pounds into your mass in kilograms by dividing by 2.205.<br>
Finally, compute your BMI by dividing your mass in kilograms by the square of your height in meters.<br>

<br>

An example what the user could see in the console:<br>

```
Please enter your height in feet: 5
Now please enter the inches: 8
Please enter your weight in pounds: 165

According to your parameters, your BMI is: 25.083613
```

<br>
<br>

**Possible solution:**<br>

<details>
  <summary>Click to show solution</summary>
  
  
  ```c
  #include <stdio.h>


int main()
{
	int feet = 0, inches = 0;
	double weight = 0.0;

	printf("Please enter your height in feet: ");
	scanf("%d", &feet);

	printf("Now please enter the inches: ");
	scanf("%d", &inches);

	printf("Please enter your weight in pounds: ");
	scanf("%lf", &weight);

	inches = inches + (12 * feet); // Converting feet & inches to inches.
	double height_in_meters = inches * 0.0254; // Converting inches to meters.
	double weight_in_kilograms = weight / 2.205; // Converting pounds to kilograms.

	double BMI = weight_in_kilograms / (height_in_meters * height_in_meters); // Calculating BMI

	printf("\nAccording to your parameters, your BMI is: %lf", BMI);

	return 0;
}
  ```
  
</details>

<br>

-----

<br>
<br>

### Task #2 - Focusing on: Basic console input & output, Understanding user defined functions.<br>

Write a program that has main() call a user-defined function that takes a Celsius temperature value as an argument and then returns the equivalent Fahrenheit value.<br>
The program should request the Celsius value as input from the user and display the result as in the following example:<br>

```
Enter a Celsius value: 20
20 degrees Celsius is 68 degrees Fahrenheit.
```
<br>

For reference, the formula for making the conversion: **Fahrenheit = 1.8 x degrees Celsius + 32**<br>

<br>

**Possible solution:**<br>

<details>
  <summary>Click to show solution</summary>
  
  ```c
  #include <stdio.h>

double celsiusToFahrenheit(int celsius) // Function definition
{
	return 1.8 * celsius + 32;
}

int main()
{
	int input = 0;
	printf("Please enter a celsius value: ");
	scanf("%d", &input);

	printf("%d degrees Celsius is %lf degrees Fahrenheit.\n", input, celsiusToFahrenheit(input));

	return 0;
}
```
  
</details>

<br>

-----

<br>
<br>

### Task #3 - Focusing on: Basic console input & output, Loops.<br>

Write a program that requests the user to enter two integers. The program should then calculate and report the sum of all the integers between and including the two integers given by the user.<br>
At this point, assume that the smaller integer is entered first. For example, if the user enters **2** and **9**, the program should report that the sum of all the integers **2** through **9** is **44**.<br>

<br>

**Possible solution**<br>

<details>
  <summary>Click to show solution</summary>

```c
#include <stdio.h>



int main()
{
	int first = 0, second = 0, sum = 0;

	printf("Enter the first number: ");
	scanf("%d", &first);

	printf("Enter the second number: ");
	scanf("%d", &second);

	for (int i = first; i <= second; i++)
	{
		sum += i;
	}

	printf("The sum of all numbers from %d through %d is %d.", first, second, sum);


	return 0;
}
```
  
</details>

<br>

--------

<br>
<br>

### Task #4 - Focusing on: Basic console input & output, Loops.<br>

Write a program that asks the user to type in numbers. After each entry the program should report the cumulative sum of the entries to date.<br>
The program should terminate when the user enters **0**.<br>

**A sample run could look like this:**<br>

```
Enter a number(Enter 0 to terminate): 3
Enter a number(Enter 0 to terminate): 2
Enter a number(Enter 0 to terminate): 0
The sum of numbers entered: 5
```

<br>

**Possible solution**<br>

<details>
  <summary>Click to show solution</summary>

```c
#include <stdio.h>

int main()
{
	int sum = 0, input = 0;

	do {
		printf("Enter a number(Enter 0 to terminate): ");
		scanf("%d", &input);
		sum += input;

	} while (input != 0);

	printf("The sum of numbers entered: %d", sum);

	return 0;
}
```
  
</details>

<br>

-------

<br>
<br>

### Task #5 - Focusing on: Basic console output, Pointers.<br>

Write a program that displays the memory addresses of the following two integers, and then prints the sum of these numbers using pointers.<br>

```c
int number1 = 3;
int number2 = 1;
```

<br>

**Possible solution:**<br>

<details>
  <summary>Click to show solution</summary>

```c
#include <stdio.h>



int main()
{
	int number1 = 3;
	int number2 = 1;

	int* ptr1 = &number1; // Just a reminder, 'ptr1' is an address and '*ptr1' is the value at that address!
	int* ptr2 = &number2;

	int sum = *ptr1 + *ptr2; 

	printf("Address of number1: %p\n", ptr1);
	printf("Address of number2: %p\n", ptr2);
	printf("The sum of number1 and number2 is: %d", sum);


	return 0;
}
```
  
</details>

<br>

-------

<br>
<br>

### Task #6 - Focusing on: Array declaration, loops.<br>

Declare an array of *ints* that holds the following numbers: **3, 7, 9, -11, 5, 6, 8**<br>
Write a program that finds and displays the largest number in the array.<br>

<br>

**Possible solution:**<br>

<details>
  <summary>Click to show solution</summary>

```c
#include <stdio.h>



int main()
{
	int arr[7] = { 3, 7, 9, -11, 5, 6, 8 };

	int largest = arr[0]; // Assigning the first element of the array

	for (int i = 1; i < (sizeof(arr) / sizeof(int)); i++) // Notice this line!
	{
		if (arr[i] > largest) // If the (i)th element is greater than our current largest one, we change what the larest number is so far.
			largest = arr[i];
	}

	printf("The largest number in the array is: %d", largest);

	return 0;
}
```
  
</details>

<br>

-------

<br>
<br>

### Task #7 - Focusing on: Basic console input & output, String manipulation.<br>

Write a program that asks the user to enter their first name and then the last name, and then construct, store and display a third string, consisting of their last name followed by a comma, a space and first name.<br>
Use **char** arrays and functions from the 'string.h' header file.<br> 

**A sample run could look like this:**<br>
```
Enter your first name: Flip
Enter your second name: Fleming
Here's the information in a single string: Fleming, Flip
```

<br>

**Possible Solution:**<br>

<details>
  <summary>Click to show solution</summary>
	
```c
#include <stdio.h>
#include <string.h>

int main()
{
	char first_name[20];
	char last_name[20];

	printf("Please enter your first name: ");
	scanf("%s", first_name);

	printf("Please enter your last name: ");
	scanf("%s", last_name);

	char full_name[50];

	strcpy(full_name, last_name); // Copying last_name to the currently empty full_name string.
	strcat(full_name, ", "); // Expanding the string with a comma and a space.
	strcat(full_name, first_name); // Finally expanding it with the first name.

	printf("Here's the information in a single string: %s", full_name);

	return 0;
}
```
  
</details>

<br>

-------

<br>
<br>

### Task #8 - Focusing on: Basic console input & output, Dynamic memory allocation, Pointers, Loops.<br>

Your task is to write a program that stores students' test scores(Which are integer values).<br>
Ask the user how many student's test results they'd like to store and then using dynamic memory allocation allocate memory that can hold those values.<br>
Then ask the user to enter the scores and store them in the previously allocated memory.<br>
Finally the program should display the scores.<br>

**A sample run could look like this:**<br>

```
Enter how many scores you'd like to store: 4
Enter student #1's score: 67
Enter student #2's score: 34
Enter student #3's score: 99
Enter student #4's score: 16

The scores you've entered are the following:
1 - 67
2 - 34
3 - 99
4 - 16
```
<br>

**Possible solution:**<br>

<details>
  <summary>Click to show solution</summary>

```c
#include <stdio.h>

int main()
{
	int amount = 0;
	printf("Enter how many scores you'd like to store: ");
	scanf("%d", &amount);

	int* p_scores = (int*)calloc(amount, sizeof(int)); // Allocating 'amount' blocks of memory, each has the size of an int.

	for (int i = 0; i < amount; i++) // We loop 'amount' times
	{
		printf("Enter student #%d's score: ", i + 1); // i + 1 so the user doesnt see that we start from 0, has no other purpose.
		scanf("%d", &(*(p_scores + i)));
	}

	printf("\nThe scores you've entered are the following: ");

	for (int i = 0; i < amount; i++)
	{
		printf("\n%d - %d", i + 1, *(p_scores + i));
	}

	free(p_scores);

	return 0;
}
```
  
</details>

<br>

-------

<br>
<br>

### Task #9 - Focusing on: Basic console input & output, Structures, Dynamic memory allocation, Pointers.<br>

William Wingate runs a pizza-analysis service. For each pizza, he needs to record the following information:<br>
- The name of the pizza, which can consist of more than one word.
- The diameter of the pizza(In centimeters).
- The weight of the pizza(In grams).

<br>

Define a structure that can hold these informations and write a program that uses a dynamically allocated structure variable of that type.<br>
The program should ask the user to enter each of the preceding items of information, and then the program should display that information.<br>

**A sample run could look like this:**<br>

```
Enter the name of the pizza: BBQ Chicken
Enter the diameter of the pizza in centimeters: 32
Enter the weight of the pizza in grams: 286.8


Pizza Info:
Name: BBQ Chicken
Diameter: 32 cm
Weight: 286.800000 g
```
<br>

**Possible solution:**<br>

<details>
  <summary>Click to show solution</summary>

```c
#include <stdio.h>

struct PizzaInfo // struct definition
{
	char name[30];
	int diameter;
	double weight;
};

int main()
{
	struct PizzaInfo* pizza = (struct PizzaInfo*)malloc(sizeof(struct PizzaInfo)); // Allocating memory that's large enough to hold a 'PizzaInfo' struct.

	printf("Enter the name of the pizza: ");
	fgets((*pizza).name, 30, stdin); // '(*pizza).name' is same as 'pizza->name', just a different way of expressing it.

	printf("Enter the diameter of the pizza in centimeters: ");
	scanf("%d", &((*pizza).diameter));

	printf("Enter the weight of the pizza in grams: ");
	scanf("%lf", &((*pizza).weight));

	printf("\n\nPizza Info:\n");
	printf("Name: %s\n", (*pizza).name);
	printf("Diameter: %d cm\n", (*pizza).diameter);
	printf("Weight: %lf g\n", (*pizza).weight);

	free(pizza);

	return 0;
}
```
  
</details>

<br>

-------

<br>
<br>











