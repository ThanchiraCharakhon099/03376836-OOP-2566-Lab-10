# Lab 10 Exercise 3

## การส่งค่าไปยัง constructor ของ base class

1.สร้าง console application project

```cmd
dotnet new console --name Lab10_Ex03
```

2.เปลี่ยน code ให้เป็นดังต่อไปนี้

```cs
var circle = new Circle();
var rectangle = new Rectangle();
var triangle = new Triangle();

class Shape
{
    private int? NumOfSide;
    public Shape()
    {
        System.Console.WriteLine("This is some shape with unknown side");
    }
    public Shape(int NumOfSide)
    {
        System.Console.WriteLine($"This is some shape with {NumOfSide} sides" );
    }
}
class Circle :Shape
{
    public Circle():base()
    {
        System.Console.WriteLine("This is a circle");
    }
}
class Rectangle :Shape
{
    public Rectangle(): base(4)
    {
        System.Console.WriteLine("This is a rectangle");
    }
}
class Triangle :Shape
{
   public Triangle() : base(3)
    {
        System.Console.WriteLine("This is a triangle");
    }
}
```

3.Build project โดยการใช้คำสั่ง

```cmd
dotnet build  Lab10_Ex03
```

ถ้ามีที่ผิดพลาดในโปรแกรม ให้แก้ไขให้ถูกต้อง

4.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 3
![image](https://github.com/ThanchiraCharakhon099/03376836-OOP-2566-Lab-10/assets/144195708/c0091fc7-47e1-4a16-b2ff-91d1add3a829)

5.Run project โดยการใช้คำสั่ง

```cmd
dotnet run --project Lab10_Ex03
```

6.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 5
![image](https://github.com/ThanchiraCharakhon099/03376836-OOP-2566-Lab-10/assets/144195708/7e8a8c04-c196-4b36-9bed-735f8abe794b)

7.อธิบายสิ่งที่พบในการทดลอง
ในคลาส Shape มีการสร้างสองคอนสตรักเตอร์ คือ:

public Shape(): ที่ไม่รับพารามิเตอร์ และใช้สำหรับแสดงข้อความ "This is some shape with unknown side" 
 
public Shape(int NumOfSide): ที่รับพารามิเตอร์ NumOfSide เพื่อแสดงข้อความ "This is some shape with {NumOfSide} sides" 
