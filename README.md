using System;
using System.Collections.Generic;
using System.Linq;

class Student
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
}

class Program
{
    static void Main()
    {
        List<Student> students = new List<Student>
        {
            new Student { Id = 1, Name = "An", Age = 16 },
            new Student { Id = 2, Name = "Binh", Age = 18 },
            new Student { Id = 3, Name = "Chi", Age = 14 },
            new Student { Id = 4, Name = "Dung", Age = 17 },
            new Student { Id = 5, Name = "Anh", Age = 19 }
        };

        // a. In toàn bộ danh sách học sinh
        Console.WriteLine("a. Danh sách học sinh:");
        foreach (var student in students)
        {
            Console.WriteLine($"{student.Id} - {student.Name} - {student.Age}");
        }

        // b. Tìm học sinh có tuổi từ 15 đến 18
        Console.WriteLine("\nb. Học sinh có tuổi từ 15 đến 18:");
        var ageRange = students.Where(s => s.Age >= 15 && s.Age <= 18);
        foreach (var student in ageRange)
        {
            Console.WriteLine($"{student.Name} - {student.Age}");
        }

        // c. Tìm học sinh có tên bắt đầu bằng chữ "A"
        Console.WriteLine("\nc. Học sinh có tên bắt đầu bằng chữ 'A':");
        var nameA = students.Where(s => s.Name.StartsWith("A", StringComparison.OrdinalIgnoreCase));
        foreach (var student in nameA)
        {
            Console.WriteLine($"{student.Name}");
        }

        // d. Tính tổng tuổi
        Console.WriteLine("\nd. Tổng tuổi của tất cả học sinh:");
        int totalAge = students.Sum(s => s.Age);
        Console.WriteLine($"Tổng tuổi: {totalAge}");

        // e. Tìm học sinh có tuổi lớn nhất
        Console.WriteLine("\ne. Học sinh có tuổi lớn nhất:");
        int maxAge = students.Max(s => s.Age);
        var oldestStudents = students.Where(s => s.Age == maxAge);
        foreach (var student in oldestStudents)
        {
            Console.WriteLine($"{student.Name} - {student.Age}");
        }

        // f. Sắp xếp danh sách theo tuổi tăng dần
        Console.WriteLine("\nf. Danh sách sau khi sắp xếp theo tuổi tăng dần:");
        var sorted = students.OrderBy(s => s.Age);
        foreach (var student in sorted)
        {
            Console.WriteLine($"{student.Name} - {student.Age}");
        }
    }
}# baitap
