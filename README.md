# Exception-Handling
using System;

class Program
{
    static void Main()
    {
        while (true)
        {
            Console.WriteLine("Menu:");
            Console.WriteLine("1. Divide by Zero Exception");
            Console.WriteLine("2. Null Reference Exception");
            Console.WriteLine("3. Index Out of Range Exception");
            Console.WriteLine("4. Format Exception");
            Console.WriteLine("5. Exit");
            Console.Write("Enter your choice: ");
            
            string choice = Console.ReadLine();

            switch (choice)
            {
                case "1":
                    HandleDivideByZeroException();
                    break;
                case "2":
                    HandleNullReferenceException();
                    break;
                case "3":
                    HandleIndexOutOfRangeException();
                    break;
                case "4":
                    HandleFormatException();
                    break;
                case "5":
                    return;
                default:
                    Console.WriteLine("Invalid choice, please try again.");
                    break;
            }
        }
    }

    static void HandleDivideByZeroException()
    {
        try
        {
            Console.Write("Enter numerator: ");
            int numerator = Convert.ToInt32(Console.ReadLine());
            Console.Write("Enter denominator: ");
            int denominator = Convert.ToInt32(Console.ReadLine());
            int result = numerator / denominator;
            Console.WriteLine("Result: " + result);
        }
        catch (DivideByZeroException ex)
        {
            Console.WriteLine("Error: " + ex.Message);
        }
    }

    static void HandleNullReferenceException()
    {
        try
        {
            string str = null;
            Console.WriteLine(str.Length);
        }
        catch (NullReferenceException ex)
        {
            Console.WriteLine("Error: " + ex.Message);
        }
    }

    static void HandleIndexOutOfRangeException()
    {
        try
        {
            int[] arr = new int[5];
            Console.Write("Enter index to access (0-4): ");
            int index = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Value at index: " + arr[index]);
        }
        catch (IndexOutOfRangeException ex)
        {
            Console.WriteLine("Error: " + ex.Message);
        }
    }

    static void HandleFormatException()
    {
        try
        {
            Console.Write("Enter an integer: ");
            int number = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("You entered: " + number);
        }
        catch (FormatException ex)
        {
            Console.WriteLine("Error: " + ex.Message);
        }
    }
}
