# HowManyCoins

C# code that calculates the smallest number of coins needed to make the amount of money.
Type the amount of money in pennies and it will tell you the number of coins you need for each type.

```c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace HowManyCoins
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Type the amount of money in pennies.");
            string amount = Console.ReadLine();
            int money = 0;

            //Check if only numbers were typed
            while (Int32.TryParse(amount, out money) != true)
            {
                Console.WriteLine("Type only numbers.");
                amount = Console.ReadLine();
            }

            int[] coins = {200, 100, 50, 20, 10, 5, 2, 1};
            string[] coinsInWord = {"£2", "£1", "50p", "20p", "10p", "5p", "2p", "1p"};

            for (int i = 0; i < 8; i++)
            {
                int numberOfCoins = money / coins[i];
                //Don't show the coin if you don't need it
                if (numberOfCoins > 0)
                {
                    Console.WriteLine($"{numberOfCoins} {coinsInWord[i]} coin(s)");
                    money = money % coins[i];
                }
            }
            Console.ReadLine();
        }
    }
}
```
