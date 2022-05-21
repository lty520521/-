# -
输入年月查询天数。大佬们看看，这代码还能不能在修改一下

using System;
namespace MyApp 

{

    internal class Program
    {
    
        static string cmdReader(string cmd)
        {
        
            float year_ = float.Parse(cmd);
            
            int year = (int)year_;
            
            char montch_0 = cmd[cmd.Length - 2];
            
            char montch_1 = cmd[cmd.Length - 1];
            
            int number0 = (Convert.ToInt32(montch_0) - 48) * 10;
            
            int number1 = Convert.ToInt32(montch_1) - 48;
            
            int montch = number0 + number1;
            
            if (montch == 1 | montch == 3 | montch == 5 | montch == 7 | montch == 8 | montch == 10 | montch == 12)
            {
            
                cmd = year + "年" + montch + "月有31天。";
            }
            else if (montch == 4 | montch == 6 | montch == 9 | montch == 11)
            {
                cmd = year + "年" + montch + "月有30天。";
            }
            else if (montch == 2)
            {
                if (year % 4 == 0)
                {
                    cmd = year + "年" + montch + "月有29天。";
                }
                else
                {
                    cmd = year + "年" + montch + "月有28天。";
                }
            }
            else
            {
                cmd = "输入月份错误，请重新输入";
            }
            return cmd;
        }
        static void Main(string[] args)
        {

            while (true)//while(trur){return/break} 循环体
            {
                Console.WriteLine("请输入年月查询天数（格式为：2002.02）");
                Console.WriteLine("若要退出程序，请输入： 退出 ");
                string yearMontch = Console.ReadLine();
                if (yearMontch == "退出")
                {
                    Console.WriteLine("程序结束");
                    return;
                }
                string output = cmdReader(yearMontch);
                Console.WriteLine(output);
            }
        }
    }

}
