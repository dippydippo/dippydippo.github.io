---
type: page
---
```csharp
using System;
using System.Text.RegularExpressions;

namespace ConsoleApp4
{
    class Program
    {
        static void Main(string[] args)
        {
            string veta = "Dne 29. 11. máme 2 hodiny programování.";



            //1) Vymažte z vìty všechny mezery

            string veta1 = veta.Replace(" ", String.Empty);
            Console.WriteLine(veta1);

            //2) Nahraïte všechny znaky kromì mezer 

            string veta2 = veta;
            var res = new Regex("\\S").Replace(veta2, "X");
            Console.WriteLine(res);

            //3) Vypište text pozpátku - nepoužívat funkci reverse!

            string reversestring = "";
            int length;

            length = veta.Length - 1;

            while (length >= 0)
            {
                reversestring = reversestring + veta[length];
                length--;
            }
            Console.WriteLine(reversestring);

            //4) Spoèítejte, kolik malých písmen vè. diakritiky je ve vìtì

            int countlower = 0;

            for (int i = 0; i < veta.Length; i++)
            {
                if (char.IsLower(veta[i])) { countlower++; }
            }
            Console.WriteLine(countlower);
        }
    }
}
```
