# string-operations
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace occuranceofstring
{
    class Program
    {//count occurance*********************
        public void Occuranceofatring(string str)
        {
                while (str.Length > 0)
                {
                    Console.Write(str[0] + "-");
                    int call = 0;
                    for (int i = 0; i < str.Length; i++)
                    {
                        if (str[0] == str[i])
                        {
                            call++;
                        }
                        
                    }
                    Console.WriteLine(call);
                    str = str.Replace(str[0].ToString(), string.Empty);
                }
            }
        //***************************************************************
       //reverse a string********************************************
        public void reversestring( string str)
        {
            string rev = " ";
            int len;
            len = str.Length ;
            while(len>0)
            {
                rev = rev + str[len-1];
                len--;
            }
            Console.WriteLine(rev);

            
        }
        //**********************************
       //reverse the order of string****************
        public void Reversewordsinstring(string str)
        {
            int start;
            int end;
            string rev = " ";

           end = str.Length-1;

            for (int i = str.Length - 1; i >= 0; i--)
            {
                if (str[i] == ' ' || i == 0)
                {

                    if (i == 0)
                    {
                        start = 0;
                    }
                    else
                    {
                        start = i + 1;
                     
                    }
                    for (int j = start; j <= end; j++)
                    {
                        Console.Write(str[j]);
                        
                    }
                    end = i - 1;
                    Console.Write('\t');
                }
                //Console.WriteLine();
            } 
        }
        //********************************************
       //reverse eachword in a string*****************
        public void reversecharinword(string str)
        {
            string result = string.Join(" ", str.Split(' ').
                Select(x => new String(x.Reverse().ToArray())));

            Console.WriteLine('\n'+result);
              //***   /*int start;
           
                         int end;
            string rev = " ";

            end = str.Length - 1;

            for (int i = end; i >= 0; i--)
            {
               if (str[i] == ' ' || i == 0)
                {

                    if (i == 0)
                    {
                        start = 0;
                    }
                    else
                    {
                        start = i + 1;

                    }
                    for (int j = start; j <= end; j++)
                    {
                        while (end > 0)
                        {
                            rev = rev + str[end];
                            end--;
                        }
                    }
                    end = i - 1;
                 }
               
            }
            Console.WriteLine("\n"+rev);*************//

        }
        //*************************
        //possible number of substrings******************
        public void possiblesubstrin(string str1)
        {
        
            for (int i = 1; i < str1.Length; i++)
            {
                for (int start = 0; start <= str1.Length - i; start++)
                {
                    string substr = str1.Substring(start, i);
                    Console.WriteLine(substr);
                    
                }
            }
           
        }
        //***************************************
//second largest in array******************
        public void secondlargest(int []arr)
        {
            int  first=int.MinValue, second=int.MinValue;
            foreach(int i in arr)
            {
                if(i>first)
                {
                    second = first;
                    first = i;
                }
                else if(i>second)
                {
                    second = i;
                }
                
            }
            Console.WriteLine("second largest" + second);
  
            
        }
      //*****************************************************
        class proram
        {

            static void Main(string[] args)
            {
               string str = " ";
                str = Convert.ToString(Console.ReadLine());
                Program p = new Program();
                p.Occuranceofatring(str);
                 
                p.reversestring(str);
                p.Reversewordsinstring(str);
                p.reversecharinword(str);
                p.possiblesubstrin("abcd");
                p.secondlargest(new int[] { 2, 3, 4,5, 1 });
                Console.ReadKey();

            }
        }
    }
}
