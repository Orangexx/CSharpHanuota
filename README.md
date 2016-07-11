#CSharpHanuota 
This is a solution about hanuota.




using System;

using System.Collections.Generic;

using System.Linq;

using System.Text;

using System.Threading.Tasks;


namespace Console汉诺塔

{
    class Program
    {
        static void Main(string[] args)
        {
            hannuota c = new hannuota();
            int result = c.HntBuzhou(4, "a","b","c");
            Console.WriteLine(result);
        }
    }

    class hannuota
    {
        //public int SumTo1(int num)
        //{
        //    int result = 0;
        //    for (int i = 1; i < num + 1; i++)
        //    {
        //        result += i;
        //    }
        //    return result;
        //}
        //public int SumTo1(int num)
        //{
        //    int result;
        //    if(num == 1)
        //    {
        //        return 1;
        //    }
        //    else
        //    {
        //        result = num + sum(num - 1);
        //        return result;
        //    }
        //}
        public int HntBuzhou(int num,string a,string b,string c)
        {
            int result = 0;
            if (num == 1)
            {
                Console.WriteLine("{0} to {1}", a,b);
                return 1;
            }
            else
            {
                result = 2 * HntBuzhou(num - 1, a, c, b) + 1;
                HntBuzhou(1, a, b, c);
                HntBuzhou(num - 1, c, b, a);
                return result;
            }
        }
    }
}
