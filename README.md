# Код всех практических заданий — Windows Forms (C#)

> Для каждого задания: создать новый проект Windows Forms App, добавить элементы на форму, вставить код в Form1.cs.
> Все имена элементов указаны в скобках рядом с каждым заданием.

---

## Задание 1 — Сравнение двух чисел

**Элементы:** `TextBox` → `txtA`, `TextBox` → `txtB`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    double a = double.Parse(txtA.Text);
    double b = double.Parse(txtB.Text);

    if (a == b) lblRes.Text = "Числа равны";
    else if (a > b) lblRes.Text = "Первое больше";
    else lblRes.Text = "Второе больше";
}
```

---

## Задание 2 — Число больше 5 и меньше 10

**Элементы:** `TextBox` → `txtN`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    double n = double.Parse(txtN.Text);

    if (n > 5 && n < 10) lblRes.Text = "Число больше 5 и меньше 10";
    else lblRes.Text = "Неизвестное число";
}
```

---

## Задание 3 — Число равно 5 или 10

**Элементы:** `TextBox` → `txtN`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    double n = double.Parse(txtN.Text);

    if (n == 5 || n == 10) lblRes.Text = "Число либо равно 5, либо равно 10";
    else lblRes.Text = "Неизвестное число";
}
```

---

## Задание 4 — Проценты по вкладу

**Элементы:** `TextBox` → `txtSum`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    double sum = double.Parse(txtSum.Text);
    double rate;

    if (sum < 100) rate = 0.05;
    else if (sum <= 200) rate = 0.07;
    else rate = 0.10;

    lblRes.Text = $"Итого: {sum + sum * rate:F2}";
}
```

---

## Задание 5 — Проценты по вкладу + бонус 15

**Элементы:** `TextBox` → `txtSum`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    double sum = double.Parse(txtSum.Text);
    double rate;

    if (sum < 100) rate = 0.05;
    else if (sum <= 200) rate = 0.07;
    else rate = 0.10;

    lblRes.Text = $"Итого: {sum + sum * rate + 15:F2}";
}
```

---

## Задание 6 — Выбор операции через switch

**Элементы:** `TextBox` → `txtOp`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    int op = int.Parse(txtOp.Text);

    lblRes.Text = op switch
    {
        1 => "Сложение",
        2 => "Вычитание",
        3 => "Умножение",
        _ => "Операция не определена"
    };
}
```

---

## Задание 7 — Начисление процентов за месяцы (цикл for)

**Элементы:** `TextBox` → `txtSum`, `TextBox` → `txtM`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    double sum = double.Parse(txtSum.Text);
    int months = int.Parse(txtM.Text);

    for (int i = 0; i < months; i++)
        sum += sum * 0.07;

    lblRes.Text = $"Итого: {sum:F2}";
}
```

---

## Задание 8 — Таблица умножения

**Элементы:** `Button` → `btnGo`, `RichTextBox` → `rtb`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    rtb.Clear();
    for (int i = 1; i <= 9; i++)
    {
        for (int j = 1; j <= 9; j++)
            rtb.AppendText($"{i}x{j}={i*j}\t");
        rtb.AppendText("\n");
    }
}
```

---

## Задание 9 — Умножение двух чисел в диапазоне 0–10

**Элементы:** `TextBox` → `txtA`, `TextBox` → `txtB`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    double a = double.Parse(txtA.Text);
    double b = double.Parse(txtB.Text);

    if (a < 0 || a > 10 || b < 0 || b > 10)
        lblRes.Text = "Числа недопустимы! Введите от 0 до 10.";
    else
        lblRes.Text = $"Результат: {a * b}";
}
```

---

## Задание 10 — Сумма (чётные) или произведение (нечётные)

**Элементы:** `TextBox` → `txtA`, `TextBox` → `txtB`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    int a = int.Parse(txtA.Text);
    int b = int.Parse(txtB.Text);

    if (a % 2 == 0 && b % 2 == 0)
        lblRes.Text = $"Оба чётные. Сумма: {a + b}";
    else if (a % 2 != 0 && b % 2 != 0)
        lblRes.Text = $"Оба нечётные. Произведение: {a * b}";
    else
        lblRes.Text = "Числа разной чётности";
}
```

---

## Задание 11 — Количество положительных чисел в массиве

**Элементы:** `TextBox` → `txtArr` (ввод через запятую), `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    string[] parts = txtArr.Text.Split(',');
    int count = 0;

    foreach (string s in parts)
        if (double.TryParse(s.Trim(), out double n) && n > 0)
            count++;

    lblRes.Text = $"Положительных: {count}";
}
```

---

## Задание 12 — Матрица 10×10: суммы строк, произведения столбцов, макс. диагональ

**Элементы:** `Button` → `btnGo`, `RichTextBox` → `rtb`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    int n = 10;
    var rnd = new Random();
    double[,] m = new double[n, n];

    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            m[i, j] = rnd.Next(-10, 20);

    rtb.Clear();
    rtb.AppendText("Суммы строк:\n");
    for (int i = 0; i < n; i++)
    {
        double s = 0;
        for (int j = 0; j < n; j++) s += m[i, j];
        rtb.AppendText($"  Строка {i+1}: {s}\n");
    }

    rtb.AppendText("Произведения столбцов:\n");
    for (int j = 0; j < n; j++)
    {
        double p = 1;
        for (int i = 0; i < n; i++) p *= m[i, j];
        rtb.AppendText($"  Столбец {j+1}: {p:F2}\n");
    }

    double max = m[0, 0];
    for (int i = 1; i < n; i++)
        if (m[i, i] > max) max = m[i, i];
    rtb.AppendText($"Макс. диагональ: {max}");
}
```

---

## Задание 13 — Элементы массива в диапазоне (0, 125)

**Элементы:** `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    var rnd = new Random();
    int count = 0;

    for (int i = 0; i < 100; i++)
    {
        int x = rnd.Next(-50, 200);
        if (x > 0 && x < 125) count++;
    }

    lblRes.Text = $"Элементов в диапазоне (0,125): {count}";
}
```

---

## Задание 14 — Матрица: отрицательные, положительные, нулевые

**Элементы:** `Button` → `btnGo`, `RichTextBox` → `rtb`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    int n = 5;
    var rnd = new Random();
    int[,] m = new int[n, n];
    int neg = 0, pos = 0;

    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            m[i, j] = rnd.Next(-5, 6);

    rtb.Clear();
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
        {
            if (m[i, j] < 0) neg++;
            else if (m[i, j] > 0) pos++;
            else rtb.AppendText($"Нуль: [{i},{j}]\n");
        }

    rtb.AppendText($"Отрицательных: {neg}, Положительных: {pos}");
}
```

---

## Задание 15 — Максимум и минимум массива

**Элементы:** `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    var rnd = new Random();
    double[] arr = new double[20];
    for (int i = 0; i < arr.Length; i++)
        arr[i] = rnd.Next(-100, 100);

    double max = arr[0], min = arr[0];
    foreach (double x in arr)
    {
        if (x > max) max = x;
        if (x < min) min = x;
    }

    lblRes.Text = $"Макс: {max}, Мин: {min}";
}
```

---

## Задание 16 — Массив Фибоначчи

**Элементы:** `TextBox` → `txtN`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    int n = int.Parse(txtN.Text);
    long[] fib = new long[n];
    fib[0] = 1; fib[1] = 1;

    for (int i = 2; i < n; i++)
        fib[i] = fib[i-1] + fib[i-2];

    lblRes.Text = string.Join(", ", fib);
}
```

---

## Задание 17 — Расстояние между двумя точками

**Элементы:** `TextBox` → `txtX1`, `txtY1`, `txtX2`, `txtY2`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
double Distance(double x1, double y1, double x2, double y2)
    => Math.Sqrt(Math.Pow(x2 - x1, 2) + Math.Pow(y2 - y1, 2));

private void btnGo_Click(object sender, EventArgs e)
{
    double x1 = double.Parse(txtX1.Text), y1 = double.Parse(txtY1.Text);
    double x2 = double.Parse(txtX2.Text), y2 = double.Parse(txtY2.Text);

    lblRes.Text = $"Расстояние: {Distance(x1, y1, x2, y2):F4}";
}
```

---

## Задание 18 — Факториал числа Фибоначчи (рекурсия)

**Элементы:** `TextBox` → `txtN`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
long Fib(int n) => n <= 1 ? 1 : Fib(n-1) + Fib(n-2);
long Fact(long n) => n <= 1 ? 1 : n * Fact(n-1);

private void btnGo_Click(object sender, EventArgs e)
{
    int n = int.Parse(txtN.Text);
    long fib = Fib(n);
    lblRes.Text = $"Fib({n})={fib}, {fib}!={Fact(fib)}";
}
```

---

## Задание 19 — Чётное → факториал, нечётное → Фибоначчи

**Элементы:** `TextBox` → `txtN`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
long Fib(int n) => n <= 1 ? 1 : Fib(n-1) + Fib(n-2);
long Fact(long n) => n <= 1 ? 1 : n * Fact(n-1);

private void btnGo_Click(object sender, EventArgs e)
{
    int n = int.Parse(txtN.Text);

    if (n % 2 == 0)
        lblRes.Text = $"{n}! = {Fact(n)}";
    else
        lblRes.Text = $"Fib({n}) = {Fib(n)}";
}
```

---

## Задание 20 — Время года по номеру месяца (switch)

**Элементы:** `TextBox` → `txtM`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    int m = int.Parse(txtM.Text);

    lblRes.Text = m switch
    {
        12 or 1 or 2 => "Зима",
        3 or 4 or 5  => "Весна",
        6 or 7 or 8  => "Лето",
        9 or 10 or 11 => "Осень",
        _ => "Неверный месяц"
    };
}
```

---

## Задание 21 — Расписание на неделю (switch)

**Элементы:** `TextBox` → `txtD`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    int d = int.Parse(txtD.Text);

    lblRes.Text = d switch
    {
        1 => "Пн: Математика, Физика",
        2 => "Вт: Русский, История",
        3 => "Ср: Программирование, БД",
        4 => "Чт: Английский, Химия",
        5 => "Пт: Биология, Информатика",
        6 => "Сб: Выходной",
        7 => "Вс: Выходной",
        _ => "Неверный день"
    };
}
```

---

## Задание 22 — Нечисловые → 0, min/max/сумма через методы

**Элементы:** `TextBox` → `txtArr` (через запятую), `Button` → `btnGo`, `RichTextBox` → `rtb`

```csharp
double[] ParseArr(string input)
{
    var parts = input.Split(',');
    var arr = new double[parts.Length];
    for (int i = 0; i < parts.Length; i++)
        arr[i] = double.TryParse(parts[i].Trim(), out double v) ? v : 0;
    return arr;
}

double Min(double[] a) { double m = a[0]; foreach (var x in a) if (x < m) m = x; return m; }
double Max(double[] a) { double m = a[0]; foreach (var x in a) if (x > m) m = x; return m; }
double Sum(double[] a) { double s = 0; foreach (var x in a) s += x; return s; }

private void btnGo_Click(object sender, EventArgs e)
{
    double[] arr = ParseArr(txtArr.Text);
    rtb.Text = $"Массив: {string.Join(", ", arr)}\n" +
               $"Мин: {Min(arr)}, Макс: {Max(arr)}, Сумма: {Sum(arr)}";
}
```

---

## Задание 23 — Вычисление n! / (k! * (n! - k!))

**Элементы:** `TextBox` → `txtN`, `txtK`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
decimal Fact(int n) { decimal r = 1; for (int i = 2; i <= n; i++) r *= i; return r; }

private void btnGo_Click(object sender, EventArgs e)
{
    int n = int.Parse(txtN.Text), k = int.Parse(txtK.Text);
    decimal nf = Fact(n), kf = Fact(k);
    lblRes.Text = $"Результат: {nf / (kf * (nf - kf))}";
}
```

---

## Задание 24 — Счастливый билет

**Элементы:** `TextBox` → `txtT1`, `txtT2`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
bool IsLucky(string t)
{
    if (t.Length != 6) return false;
    return (t[0]+t[1]+t[2]) == (t[3]+t[4]+t[5]);
}

private void btnGo_Click(object sender, EventArgs e)
{
    lblRes.Text = $"{txtT1.Text}: {(IsLucky(txtT1.Text) ? "Счастливый!" : "Нет")}\n" +
                  $"{txtT2.Text}: {(IsLucky(txtT2.Text) ? "Счастливый!" : "Нет")}";
}
```

---

## Задание 25 — Классы Student и Aspirant

**Элементы:** `Button` → `btnGo`

```csharp
class Student
{
    private string surname, recordBook;
    private int course;

    public Student(string s, int c, string r) { surname=s; course=c; recordBook=r; }

    public string Surname { get => surname; set => surname = value; }
    public int Course { get => course; set => course = value; }
    public string RecordBook { get => recordBook; set => recordBook = value; }

    public virtual string Print() => $"Студент: {Surname}, курс {Course}, зачётка {RecordBook}";
}

class Aspirant : Student
{
    private string topic;

    public Aspirant(string s, int c, string r, string t) : base(s, c, r) { topic = t; }

    public string Topic { get => topic; set => topic = value; }

    public override string Print() => base.Print() + $"\nТема диссертации: {Topic}";
}

private void btnGo_Click(object sender, EventArgs e)
{
    var s = new Student("Иванов", 3, "АС-001");
    var a = new Aspirant("Петров", 5, "АС-099", "Нейросети");
    MessageBox.Show(s.Print() + "\n\n" + a.Print());
}
```

---

## Задание 26 — Классы Book, BookGenre, BookGenrePubl

**Элементы:** `Button` → `btnGo`

```csharp
class Book
{
    private string title, author;
    private double price;

    public Book(string t, string a, double p) { title=t; author=a; price=p; }

    public string Title { get => title; set => title = value; }
    public string Author { get => author; set => author = value; }
    public double Price { get => price; set => price = value; }

    public virtual string Print() => $"\"{Title}\", {Author}, {Price:F2} руб.";
}

class BookGenre : Book
{
    private string genre;

    public BookGenre(string t, string a, double p, string g) : base(t, a, p) { genre=g; }

    public string Genre { get => genre; set => genre = value; }

    public override string Print() => base.Print() + $", Жанр: {Genre}";
}

sealed class BookGenrePubl : BookGenre
{
    private string publisher;

    public BookGenrePubl(string t, string a, double p, string g, string pub)
        : base(t, a, p, g) { publisher=pub; }

    public string Publisher { get => publisher; set => publisher = value; }

    public override string Print() => base.Print() + $", Издатель: {Publisher}";
}

private void btnGo_Click(object sender, EventArgs e)
{
    var b = new BookGenrePubl("Война и мир", "Толстой", 590, "Роман", "Эксмо");
    MessageBox.Show(b.Print());
}
```

---

## Задание 27 — Абстрактный класс Figure и Triangle

**Элементы:** `TextBox` → `txtA`, `txtB`, `txtC`, `Button` → `btnGo`, `Label` → `lblRes`

```csharp
abstract class Figure
{
    private string name;
    public Figure(string n) { name = n; }
    public string Name { get => name; }
    public abstract double Area2 { get; }
    public abstract double Area();
    public virtual string Print() => $"Фигура: {Name}";
}

class Triangle : Figure
{
    private double a, b, c;

    public Triangle(string n, double a, double b, double c) : base(n)
    { this.a=a; this.b=b; this.c=c; }

    public void SetABC(double a, double b, double c) { this.a=a; this.b=b; this.c=c; }
    public (double,double,double) GetABC() => (a,b,c);

    public override double Area2
    {
        get { double s=(a+b+c)/2; return Math.Sqrt(s*(s-a)*(s-b)*(s-c)); }
    }

    public override double Area() => Area2;

    public override string Print() => base.Print() + $", стороны: {a},{b},{c}, площадь: {Area():F4}";
}

private void btnGo_Click(object sender, EventArgs e)
{
    double a = double.Parse(txtA.Text);
    double b = double.Parse(txtB.Text);
    double c = double.Parse(txtC.Text);
    var t = new Triangle("Треугольник", a, b, c);
    lblRes.Text = t.Print();
}
```

---

## Задание 28 — Круглая форма

**Код в конструкторе Form1:**

```csharp
public Form1()
{
    InitializeComponent();

    this.Width = 300;
    this.Height = 300;
    this.FormBorderStyle = FormBorderStyle.None;
    this.BackColor = Color.LimeGreen;
    this.TransparencyKey = Color.LimeGreen;

    var gp = new System.Drawing.Drawing2D.GraphicsPath();
    gp.AddEllipse(0, 0, Width, Height);
    this.Region = new Region(gp);

    var btn = new Button { Text = "X", Size = new Size(40,40),
                           Location = new Point(130, 130) };
    btn.Click += (s, e) => Close();
    Controls.Add(btn);
}
```

---

## Задание 29 — Таблица значений y = a * ln(x)

**Элементы:** `TextBox` → `txtA`, `txtX0`, `txtXk`, `txtDx`, `Button` → `btnGo`, `DataGridView` → `dgv`

```csharp
private void btnGo_Click(object sender, EventArgs e)
{
    double a  = double.Parse(txtA.Text);
    double x0 = double.Parse(txtX0.Text);
    double xk = double.Parse(txtXk.Text);
    double dx = double.Parse(txtDx.Text);

    dgv.Columns.Clear();
    dgv.Columns.Add("x", "x");
    dgv.Columns.Add("y", "y = a*ln(x)");
    dgv.Rows.Clear();

    for (double x = x0; x <= xk + 1e-9; x += dx)
        dgv.Rows.Add(x.ToString("F4"), (a * Math.Log(x)).ToString("F4"));
}
```
