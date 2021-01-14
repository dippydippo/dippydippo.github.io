```csharp
using System;
using System.Text.RegularExpressions;

namespace ConsoleApp4
{
    class Program
    {
        static void Main(string[] args)
        {
            string veta = "Dne 29. 11. m�me 2 hodiny programov�n�.";



            //1) Vyma�te z v�ty v�echny mezery

            string veta1 = veta.Replace(" ", String.Empty);
            Console.WriteLine(veta1);

            //2) Nahra�te v�echny znaky krom� mezer 

            string veta2 = veta;
            var res = new Regex("\\S").Replace(veta2, "X");
            Console.WriteLine(res);

            //3) Vypi�te text pozp�tku - nepou��vat funkci reverse!

            string reversestring = "";
            int length;

            length = veta.Length - 1;

            while (length >= 0)
            {
                reversestring = reversestring + veta[length];
                length--;
            }
            Console.WriteLine(reversestring);

            //4) Spo��tejte, kolik mal�ch p�smen v�. diakritiky je ve v�t�

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