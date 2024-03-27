# 1-6
using System;

class Complex
{
    public double Real { get; set; }
    public double Imaginary { get; set; }

    public Complex(double real, double imaginary)
    {
        Real = real;
        Imaginary = imaginary;
    }

    // Overloading the + operator to add two complex numbers
    public static Complex operator +(Complex c1, Complex c2)
    {
        return new Complex(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);
    }

    public override string ToString()
    {
        return $"{Real} + {Imaginary}i";
    }
}


class Program
{
    static void Main(string[] args)
    {
        Complex num1 = new Complex(2, 3);
        Complex num2 = new Complex(4, 5);

        Complex sum = num1 + num2;

        Console.WriteLine($"Sum of {num1} and {num2} is {sum}");
    }
}








//4.Write a Program in C# to find the sum of each row of given jagged array of 3
//inner arrays.

using System;
namespace jag
{
    class Program
    {
        static void Main(string[] args)
        {
            const int rows = 3;
            int i, sum = 0;
            int[][] j_arr = new int[rows][];
            j_arr[0] = new int[2];
            j_arr[1] = new int[3];
            j_arr[2] = new int[4];
            j_arr[0][1] = 10;
            j_arr[1][0] = 20;
            j_arr[1][1] = 30;
            j_arr[2][0] = 40;
            j_arr[2][2] = 50;
            j_arr[2][3] = 60;
            for (i = 0; i < 2; i++)
                sum += j_arr[0][i];
            for (i = 0; i < 3; i++)
                sum += j_arr[1][i];
            for (i = 0; i < 4; i++)
                sum += j_arr[2][i];
            Console.WriteLine("sum is :{0}", sum);
            Console.Read();
        }
    }

}








using System;

class Program
{
    static void Main(string[] args)
    {
        int[] numbers = { 1, 2, 3, 4, 5 };

        try
        {
            // Trying to access an element beyond the array bounds
            int index = 10;
            Console.WriteLine($"Accessing element at index {index}: {numbers[index]}");
        }
        catch (IndexOutOfRangeException e)
        {
            Console.WriteLine($"Error: {e.Message}");
        }
        finally
        {
            // This block will execute regardless of whether an exception occurred or not
            Console.WriteLine("Finally block executed.");
        }

        Console.WriteLine("Program continues after exception handling.");
    }
}






1. Write a Program in C# to demonstrate Command line arguments processing for 
the following. 
a) To find the square root of a given number. 
b) To find the sum & average of three numbers.
Solution:
a) To find the square root of a given number. 
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace lab1a
{
 class Program
 {
 static void Main(string[] args)
 {
 Console.WriteLine("Enter the value");
 int i;
 i = int.Parse(Console.ReadLine());
 double sqr = Math.Sqrt(i);
 Console.WriteLine("square root of the num is{0}is:{1}", i, sqr);
 Console.ReadLine();
 }
 }
}
Output:
Solution:
b) To find the sum & average of three numbers.
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
namespace lab1b
{
 class Program
 {
 static void Main(string[] args)
 {
 int a, b, c, sum;
 float avg;
 Console.WriteLine("Enter the 3 nums");
 a = int.Parse(Console.ReadLine());
 b = int.Parse(Console.ReadLine());
 c = int.Parse(Console.ReadLine());
 sum = a + b + c;
 Console.WriteLine("The sum is" + sum);
 Console.ReadLine();
 avg = sum / 3;
 Console.WriteLine("The avg of given sum is" + avg);
 Console.ReadLine();
 }
 }
}
Output:
2. Write a Program in C# to demonstrate the following :
a) Boxing and Unboxing
b) Invalid Unboxing. 
Solution:
a) Boxing and Unboxing
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace lab2a
{
 class Program
 {
 static void Main(string[] args)
 {
 int i = 123;
 object o = i;
 int j = (int)o;
 Console.WriteLine("The valuetype value before boxing is i=" + i);
 Console.WriteLine("The objecttype value after boxing is o=" + o);
 Console.WriteLine("The valuetype value after unboxing is j=" + 
j);
 Console.ReadLine();
 }
 }
}
Output:
Solution:
b) Invalid Unboxing. 
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
namespace lab2b
{
 class Program
 {
 static void Main(string[] args)
 {
 int i = 123;
 object o = i;
 try
 {
 int j = (Short)o;
 Console.WriteLine("unboxing is successful");
 }
 catch (System.InvalidCastException e)
 {
 Console.WriteLine("Invalid boxing" + e.Message);
 }
 Console.ReadLine();
 }
 }
}
