# program-100





التكليف1

 using System;
using System.Collections.Generic;

class Shape
{
    public virtual double CalculateArea()
    {
        return 0;
    }
}

class Circle : Shape
{
    public double Radius;

    public Circle(double radius)
    {
        Radius = radius;
    }

    public override double CalculateArea()
    {
        return Math.PI * Radius * Radius;
    }
}

class Rectangle : Shape
{
    public double Width;
    public double Height;

    public Rectangle(double width, double height)
    {
        Width = width;
        Height = height;
    }

    public override double CalculateArea()
    {
        return Width * Height;
    }
}

class Program
{
    static void Main()
    {
        List<Shape> shapes = new List<Shape>();

        shapes.Add(new Circle(5));
        shapes.Add(new Rectangle(4, 6));

        foreach (Shape shape in shapes)
        {
            Console.WriteLine(
                shape.GetType().Name +
                " Area = " +
                shape.CalculateArea());
        }

        Console.ReadLine();
    }
}






التكليف2
 using System;

class Person
{
    public string Name;
    public string Email;

    public Person(string name, string email)
    {
        Name = name;
        Email = email;
        Console.WriteLine("Person Constructor");
    }

    public void DisplayBasicInfo()
    {
        Console.WriteLine("Name: " + Name);
        Console.WriteLine("Email: " + Email);
    }
}

class Student : Person
{
    public int StudentId;
    public double GPA;

    public Student(string name, string email, int studentId, double gpa)
        : base(name, email)
    {
        StudentId = studentId;
        GPA = gpa;
        Console.WriteLine("Student Constructor");
    }

    public void DisplayStudent()
    {
        Console.WriteLine("Student ID: " + StudentId);
        Console.WriteLine("GPA: " + GPA);
    }
}

class Employee : Person
{
    public int EmployeeId;
    public double Salary;

    public Employee(string name, string email, int employeeId, double salary)
        : base(name, email)
    {
        EmployeeId = employeeId;
        Salary = salary;
        Console.WriteLine("Employee Constructor");
    }
}

class Teacher : Employee
{
    public string CourseName;

    public Teacher(string name, string email, int employeeId,
                   double salary, string courseName)
        : base(name, email, employeeId, salary)
    {
        CourseName = courseName;
        Console.WriteLine("Teacher Constructor");
    }

    public void Teach()
    {
        Console.WriteLine("Teaching: " + CourseName);
    }
}

class Program
{
    static void Main()
    {
        Student student = new Student(
            "Ahmed", "ahmed@gmail.com", 101, 3.5);

        Console.WriteLine();
        student.DisplayBasicInfo();
        student.DisplayStudent();

        Console.WriteLine();

        Teacher teacher = new Teacher(
            "Ali", "ali@gmail.com", 201, 1000, "Programming");

        Console.WriteLine();
        teacher.DisplayBasicInfo();
        teacher.Teach();

        Console.ReadLine();
    }
}



التكليف3



 class Vehicle
{
    public string Brand;

    public void Start()
    {
        Console.WriteLine("Vehicle started");
    }
}

class Car : Vehicle
{
    public void Drive()
    {
        Console.WriteLine("Car is driving");
    }
}

class Bus : Vehicle
{
    public void CarryPassengers()
    {
        Console.WriteLine("Bus carries passengers");
    }
}

class Program
{
    static void Main()
    {
        Car car = new Car();
        car.Brand = "Toyota";
        car.Start();
        car.Drive();

        Bus bus = new Bus();
        bus.Brand = "Mercedes";
        bus.Start();
        bus.CarryPassengers();
    }





التكليف4
 class Person
{
    public string Name;
    public string Email;

    public Person(string name, string email)
    {
        Name = name;
        Email = email;
        Console.WriteLine("Person constructor");
    }

    public void DisplayBasicInfo()
    {
        Console.WriteLine(Name);
        Console.WriteLine(Email);
    }
}

class Student : Person
{
    public int StudentId;
    public double GPA;

    public Student(string name, string email, int studentId, double gpa)
        : base(name, email)
    {
        StudentId = studentId;
        GPA = gpa;
        Console.WriteLine("Student constructor");
    }
}

class Employee : Person
{
    public int EmployeeId;
    public double Salary;

    public Employee(string name, string email, int employeeId, double salary)
        : base(name, email)
    {
        EmployeeId = employeeId;
        Salary = salary;
        Console.WriteLine("Employee constructor");
    }
}

class Teacher : Employee
{
    public string CourseName;

    public Teacher(string name, string email, int employeeId,
                   double salary, string courseName)
        : base(name, email, employeeId, salary)
    {
        CourseName = courseName;
        Console.WriteLine("Teacher constructor");
    }

    public void Teach()
    {
        Console.WriteLine("Teacher teaches " + CourseName);
    }
}

class Program
{
    static void Main()
    {
        Student student = new Student(
            "Ahmed", "ahmed@gmail.com", 101, 3.5);

        student.DisplayBasicInfo();

        Teacher teacher = new Teacher(
            "Ali", "ali@gmail.com", 201, 1000, "Programming");

        teacher.DisplayBasicInfo();
        teacher.Teach();
    }
}