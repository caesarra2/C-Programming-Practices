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

**Example solution:**<br>

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


### Task #2 - Focusing on: Basic console input & output, Understanding user defined functions.<br>

Write a program that has main() call a user-defined function that takes a Celsius temperature value as an argument and then returns the equivalent Fahrenheit value.<br>
The program should request the Celsius value as input from the user and display the result as in the following example:<br>

```
Enter a Celsius value: 20
20 degrees Celsius is 68 degrees Fahrenheit.
```
<br>

For reference, the formula for making the conversion: **Fahrenheit = 1.8 x degrees Celsius + 32**<br>

**Example solution:**<br>

<details>
  <summary>Click to show solution</summary>
  
  ```c
  #include <stdio.h>

double celsiusToFahrenheit(int celsius)
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






