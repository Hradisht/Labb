//here is something

using System;
class HelloWorld
{
    static void Main()
    {

        Console.WriteLine("Enter a string: ");
        string input = Console.ReadLine();
        string numbers = "1234567890";

        string number = "";
        string inrenumber = "";

        for (int i = 0; i < input.Length; i++)
        {
            char currentChar = input[i];

            if (numbers.Contains(currentChar))
            {
                number += currentChar;

                // hitta mönstret
                for (int j = i + 1; j < input.Length; j++)
                {
                    char innerChar = input[j];
                    if (numbers.Contains(innerChar))
                    {
                        inrenumber += innerChar;
                        if (innerChar == currentChar)
                        {
                            //skriv ut strängen innan delsträngen
                            if (i != 0)
                            {
                                Console.ForegroundColor = ConsoleColor.Black;
                                Console.Write(input.Substring(0, i - 1));
                            }
                            Console.ForegroundColor = ConsoleColor.Red;
                            Console.Write(number);
                            Console.ForegroundColor = ConsoleColor.Black;
                            if (i != input.Length)
                            {
                                Console.ForegroundColor = ConsoleColor.Black;
                                Console.Write(input.Substring(j + 1));
                            }

                        }

                    }
                }
            }
        }

    }
}
