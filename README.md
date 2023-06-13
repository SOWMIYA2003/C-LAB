# C-LAB
### Eligibility-for-Admission
```

using System;

namespace engadm
{
    class criteria
    {
        static void Main(string[] args)
        {
            int phy, math, chem, tot1, tot2;
            string name;
            Console.Write("Enter the student name : ");
            name = Convert.ToString(Console.ReadLine());
            Console.Write("Enter the Marks obtained in physics :");
            phy = Convert.ToInt32(Console.ReadLine());
            Console.Write("Enter the Marks obtained in maths :");
            math = Convert.ToInt32(Console.ReadLine());
            Console.Write("Enter the Marks obtained in chemistry :");
            chem = Convert.ToInt32(Console.ReadLine());
            tot1 = phy + math + chem;
            tot2 = phy + math;
            if(phy>=55 && math>=65 && chem>=50)
            {
                if(tot1>=180 ||  tot2>=140)
                {
                    Console.WriteLine(name + " is eligible for engineering admission");
                }
                else
                {
                    Console.WriteLine(name+ " is not eligible for engineering admission");
                }
            }
            else
            {
                Console.WriteLine(name + " is not eligible for engineering admission");
            }
        }
    }
}

```
### Palindrome
```
using System;
namespace palindrome
{
    public class Program
    {
        static void Main(string[] args)
        {
            string str1;
            string rev = "";
            Console.Write("Enter a string : ");
            str1= Convert.ToString(Console.ReadLine());


            for (int i = str1.Length - 1; i >= 0; i--)
            {
                rev += str1[i];
            }

            if (str1 == rev)
            {
                Console.WriteLine("{0} is Palindrome.",str1);
            }
            else
            {
                Console.WriteLine("{0} is not Palindrome",str1);
            }
        }
    }
}

```
### Pascal Triangle.
```
using System;
using System.Globalization;

namespace Pattern
{
    class Program
    {
        static void Main(string[] args)
        {
            int n,i,j,c=1,space;
            Console.Write("Enter the No of Rows : ");
            n=Convert.ToInt32(Console.ReadLine());
            for(i = 0; i < n; i++)
            {
                for(space=1;space<=n-i;space++)
                {
                    Console.Write(" ");
                }
               for( j=0 ; j<=i ; j++)
               {
                    if(i==0 || j==0)
                    {
                        c = 1;
                    }
                    else
                    {
                        c = c*(i - j + 1) / j;
                    }
                    Console.Write("{0} ",c);
                }
                Console.WriteLine();
            }
        }
    }
}
```
### Constructor
```
using System;
public class Employee
{
   public String designation;
   public String employee_name;
   public int exp;
   public int bs;
   public int insurance;
   double hra, ta, salaryam;

   public Employee(String employee_name, String designation, int exp, int bs, int i)
   {
       this.employee_name = employee_name;
       this.designation = designation;
       this.exp = exp;
       this.bs = bs;
       this.insurance = i;
   }
   public void salary()
   {
       hra = this.bs * 0.2;
       ta = this.bs * 0.1;
       salaryam = this.bs + hra + ta - this.insurance;

   }
   public void display()
   {

       Console.WriteLine("Name of the employee is {0} having {1} of experience,working as {2}", this.employee_name, this.exp, this.designation);
       Console.WriteLine("Receives {0} of salary.", salaryam);

   }

}
class TestEmployee
{
   public static void Main(string[] args)
   {
       Employee e1 = new Employee("Hari", "Tester", 10, 30000, 1000);
       e1.salary();
       Employee e2 = new Employee("Latha", "Developer", 5, 25000, 1000);
       e2.salary();
       e1.display();
       e2.display();

   }
}

```
### JaggedArray
```
using System;
namespace standard
{
    class Program
    {
        public static void Main(string[] args)
        {
            int[][] cpu = new int[4][];
            cpu[0]=new int[3];
            cpu[1]=new int[5];
            cpu[2]=new int[4];
            cpu[3]=new int[6];
            for(int i=0; i<4; i++)
            {
                for(int j=0; j < cpu[i].Length; j++)
                {
                    cpu[i][j] = i*j+70;
                }
            }
            for(int i=0; i<4;i++)
            {
                for(int j = 0; j < cpu[i].Length; j++)
                {
                    Console.WriteLine("CPU usage for node {0} is {1}", i, cpu[i][j]);
                }
                Console.WriteLine();
            }
        }
    }
}
```
### Operator-Overloading
```
using System;
namespace OperatorOverload
{
   class Program
   {
       int n;
       public Program()
       {
           n = 10;
           Console.WriteLine("Default Constructor - The value is : {0} ",n);
       }
       public Program(int a)
       {
           n = a;
           Console.WriteLine("Parameterized Constructor - The value is : {0} ",n);
       }
       public static bool operator ==(Program p1, Program p2)
       {
           return p1.Equals(p2);

       }
       public static bool operator !=(Program p1, Program p2)
       {
           return !p1.Equals(p2);

       }

   }
   class Example
   {
       public static void Main()
       {
           Program p1 = new Program();
           Program p2 = new Program(12);
           if (p1 == p2)
           {
               Console.WriteLine("Both Object are Equal");
           }
           else
           {
               Console.WriteLine("Both Objects are different ");
           }
       }
   }
}
```
### Recursive-function
```
using System;
namespace Program
{
    class Program
    {
        int rem = 0, rev = 0;
        public int fun(int number)
        {
            rem = number % 10;
            if (rem == 0)
            {
                return rev;
            }
            else
            {
                rev = rev * 10 + rem;
                return fun(number / 10);
            }
        }
        static void Main(string[] args)
        {
            int n;
        
            Console.WriteLine("Enter a Number: ");
            n = Convert.ToInt32(Console.ReadLine());

            Program reverse= new Program();
            Console.WriteLine("Reverse Number : {0} ",reverse.fun(n));
            
        }
    }
}
```
### Inheritance
```
using System;
namespace Hello
{
    public class tyre
    {
        public tyre()
        {
            Console.WriteLine("tyre Constructor");
        }
        public virtual void Display()
        {
            Console.WriteLine("Method in tyre class");
        }
    }
    public class scooter : tyre
    {
        public scooter()
        {
            Console.WriteLine("scooter Constructor");
        }

        public override void Display()
        {
            base.Display();
            Console.WriteLine("Method in scooter class");
        }
    }

    public class car : tyre
    {
        public car()
        {
            Console.WriteLine("car Constructor");
        }
        public override void Display()
        {
            base.Display();
            Console.WriteLine("Methos in car class");
        }
    }
    public class Program
    {
        public static void Main(string[] args)
        {
            car c1 = new car();
            c1.Display();
            scooter s1 = new scooter();
            s1.Display();
        }
    }
}
```
### Interface
```
using System;
namespace Hello
{
    class Program
    {
        public interface bank
        {
            void deposit(int amount);
            void withdrwal(int amount);
        }
        public class bank1:bank
        {
            int balance = 1000;
            int amount;
            public void deposit(int amount)
            {
                balance = balance+amount;
                Console.WriteLine(balance);
            }
            public void withdrwal(int amount)
            {
                balance = balance-amount;
                Console.WriteLine(balance);
            }
            public static void Main()
            {
                bank1 obj = new bank1();
                Console.WriteLine("Enter your choice :");
                Console.WriteLine("Enter 1 to deposit");
                Console.WriteLine("Enter 2 to withdraw");
                int ch = Convert.ToInt32(Console.ReadLine());
                if (ch == 1)
                {
                    Console.WriteLine("Enter the amount to be deposited:");
                    int amount = Convert.ToInt32(Console.ReadLine());
                    Console.WriteLine("Balance Amount in your Account : ");
                    obj.deposit(amount);
                }
                else if (ch == 2)
                {
                    Console.WriteLine("Enter the amount to be withdrawed:");
                    int amount = Convert.ToInt32(Console.ReadLine());
                    Console.WriteLine("Balance Aamount in your Account : ");
                    obj.withdrwal(amount);
                }
            }
        }

    }
}
```
