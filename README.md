<h1>Lab 4 CIS 200 assignment</h1>

<h2>Description</h2>
This is an example of a coding assignment I completed for CIS 200. The lab creates the generic type for heldvalue and string for identifier
<br />




<p align="center">
 <br/>
<img src="blob:https://imgur.com/7a879d9d-6c45-4385-be51-6dcd72b549c6" alt="]"/>


<br/>
code: 
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Lab4
{
    //Part 1 - Modify the below Class to accept a generic held value, instead of only an integer. 
    class ObjectHolder<G>
    {
        //Constructor
        public ObjectHolder(string whatItsHolding, G heldValue)
        {
            WhatItsHolding = whatItsHolding;
            HeldValue = heldValue;
        }



        //do not modify
        public string WhatItsHolding
        {
            get; set;
        }


        //Update Property to Be Generic

        public G HeldValue
        {
            get;set;
        }
    }
}
Code for employee.cs:
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Lab4
{
    class Employee
    {
        public Employee(string name)
        {
            Name = name;
        }

        string Name
        {
            get; set;
        }

        public override string ToString()
        {
            return $"Employee's name is {Name}";
        }
    }
}
Code for program.cs:
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Lab4
{
    class Program
    {
        static void Main(string[] args)
        {



            //test for Int - should already succeed.
            ObjectHolder<int> intTest = new ObjectHolder<int>("Integer", 64);
            Console.WriteLine($"Int Test Results: Type Stored {intTest.WhatItsHolding} Value: {intTest.HeldValue}");
            //test for float - currently fails
            ObjectHolder <float> floatTest = new ObjectHolder<float>("Float", 64.5f);
            Console.WriteLine($"Int Test Results: Type Stored {floatTest.WhatItsHolding} Value: {floatTest.HeldValue}");
            //test for string - currently Fails
            ObjectHolder<string> stringTest = new ObjectHolder<string>("String", "This is indeed a string");
            Console.WriteLine($"Int Test Results: Type Stored {stringTest.WhatItsHolding} Value: {stringTest.HeldValue}");
            //test for Employee - currently Fails
            Employee michael = new Employee("Michael Doe");
            ObjectHolder<Employee> employeeTest = new ObjectHolder<Employee>("Employee", michael);
            Console.WriteLine($"Int Test Results: Type Stored {employeeTest.WhatItsHolding} Value: {employeeTest.HeldValue}");

            Console.ReadLine();
        }
    }
}
