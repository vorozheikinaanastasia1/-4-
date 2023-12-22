using System;

namespace RandomArraySum
{
class Program
{
static void Main(string[] args)
{
Console.WriteLine("Введите длину массива:");
int length = Convert.ToInt32(Console.ReadLine());

int[] array = GenerateRandomArray(length);
Console.WriteLine("Сгенерированный массив:");
PrintArray(array);

int sumOfEvenNumbers = CalculateSumOfEvenNumbers(array);
Console.WriteLine($"Сумма четных чисел: {sumOfEvenNumbers}");
}

static int[] GenerateRandomArray(int length)
{
int[] array = new int[length];
Random random = new Random();
for (int i = 0; i < length; i++)
{
array[i] = random.Next(1, 101); // Генерация случайного числа от 1 до 100
}
return array;
}

static void PrintArray(int[] array)
{
foreach (int number in array)
{
Console.Write(number + " ");
}
Console.WriteLine();
}

static int CalculateSumOfEvenNumbers(int[] array)
{
int sum = 0;
foreach (int number in array)
{
if (number % 2 == 0) // Проверка на четность
{
sum += number;
}
}
return sum;
}
}
} 
