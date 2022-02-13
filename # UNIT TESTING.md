# UNIT TEST

## Mục lục
- [Introduction](#introduction)
- [Vòng đời của Unit test](#v%C3%B2ng-%C4%91%E1%BB%9Di-c%E1%BB%A7a-unit-test) <br>
- [Tính chất của Unit Test](#Tính-chất-của-Unit-Test)

## Introduction
Unit test là quá trình kiểm thử từng đơn vị lập trình, có thể là:

- Function (hàm)
- Method (phương thức)
- Class (lớp)

## Vòng đời của Unit test
Unit test có 3 trạng thái cơ bản:
- Fail (thất bại)
- Ignore (bỏ qua khi rơi vào vòng lặp vô tận,...)
- Pass (vượt qua kiểm thử)

Khi vận hành một (hoặc nhiều) Unit test (sau viết tắt là UT) thì mỗi UT sẽ rơi vào một trong 3 trạng thái trên.

## Tính chất của Unit Test

1. UT được thực hiện trong một môi trường độc lập. Tức là mỗi UT thực hiện tách biệt với các UT khác, không ảnh hưởng lẫn nhau.
1. UT có thể được thực hiện bởi Developer, Tester hoặc có thể là Quality Control.
1. Mỗi một UT sẽ có nhiều Test case. Mỗi test case sẽ bao gồm: Context (ngữ cảnh), Input data (dữ liệu đầu vào), Expected output (kết quả đầu ra mong đợi), Test step (các bước thực hiện) và Actual output (kết quả thực tế).

Ví dụ về một Unit test case cho hàm chia hai số thực:
- Unit test case: Kết quả của chia hai số thực
- Context: không
- Function: `double Divide (double a, double b)`
- Input data: (1, 2)
- Expected output: (0.5)
- Test step: 
    1.  `double Result = Divide(1, 2);`
    1. So sánh với Expected output
- Actual output: `Result = 0.5`



```cs
public class Test
{
    [Theory]
    [InlineData(1, 2, 0.5)]
    public void TestChia(double x, double y, double exp)
    {
        double actual = Program.chia(x, y);
        Assert.Equal(exp, actual);         
    }
}
```

