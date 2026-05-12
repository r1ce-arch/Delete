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
# Ответы на теоретические вопросы к экзамену по РПМ

---

## 1. Основные этапы разработки программного обеспечения. Жизненный цикл

**Жизненный цикл программного обеспечения (ЖЦПО)** — это период времени от момента принятия решения о создании ПО до его полного вывода из эксплуатации.

### Основные этапы:

**1. Анализ требований**
Сбор и изучение требований заказчика. Определяется, что должна делать система. Результат — техническое задание (ТЗ).

**2. Проектирование**
Разработка архитектуры системы, выбор технологий, проектирование базы данных и интерфейсов. Результат — техническая документация, UML-диаграммы.

**3. Реализация (кодирование)**
Написание программного кода на основе проектной документации. Разработчики создают модули и компоненты системы.

**4. Тестирование**
Проверка соответствия ПО требованиям. Виды: модульное, интеграционное, системное, приёмочное тестирование.

**5. Внедрение (развёртывание)**
Установка готового ПО на оборудование заказчика, настройка, обучение пользователей.

**6. Сопровождение**
Исправление ошибок, выпуск обновлений, адаптация к новым требованиям в процессе эксплуатации.

---

## 2. Модели жизненного цикла программного обеспечения

Модель ЖЦ — это описание того, как организован процесс разработки: в каком порядке выполняются этапы и как они связаны между собой.

### Основные модели:

| Модель | Краткое описание |
|--------|-----------------|
| Каскадная | Этапы идут строго последовательно, возврат назад не предусмотрен |
| V-модель | Каждому этапу разработки соответствует этап тестирования |
| Спиральная | Цикличная разработка с анализом рисков на каждом витке |
| Итерационная | Система строится постепенно, выпускаются версии с нарастающей функциональностью |
| Agile | Гибкая разработка короткими итерациями (спринтами) с постоянным участием заказчика |

---

## 3. Каскадная модель жизненного цикла ПО

**Каскадная модель (Waterfall)** — самая первая и классическая модель ЖЦ, предложена в 1970-х годах.

### Принцип работы:
Этапы выполняются строго последовательно, как водопад — сверху вниз:
```
Анализ → Проектирование → Реализация → Тестирование → Внедрение → Сопровождение
```
Каждый следующий этап начинается только после полного завершения предыдущего.

### Достоинства:
- Простота и понятность процесса
- Чёткая документация на каждом этапе
- Легко планировать сроки и бюджет
- Подходит для проектов с чёткими и стабильными требованиями

### Недостатки:
- Невозможно вернуться на предыдущий этап без больших затрат
- Требования должны быть известны заранее и не меняться
- Заказчик видит результат только в конце
- Ошибки в требованиях обнаруживаются слишком поздно

### Применение:
Государственные проекты, военные системы, медицинское ПО — там, где требования фиксированы с самого начала.

---

## 4. V-модель ЖЦПО

**V-модель** — расширение каскадной модели, в которой каждому этапу разработки соответствует этап тестирования.

### Структура (форма буквы V):
```
Анализ требований  ←────────────────→  Приёмочное тестирование
  Проектирование системы  ←────────→  Системное тестирование
    Проектирование модулей  ←──────→  Интеграционное тестирование
      Кодирование  ←─────────────────→  Модульное тестирование
```

Левая ветвь — разработка, правая — тестирование. Нижняя точка — написание кода.

### Особенности:
- Тестирование планируется параллельно с разработкой
- Тест-планы пишутся на этапе анализа требований
- Каждый уровень тестирования проверяет соответствующий уровень разработки

### Достоинства:
- Тестирование заложено в процесс с самого начала
- Высокое качество продукта
- Ошибки обнаруживаются раньше

### Недостатки:
- Жёсткая структура, как и в каскадной модели
- Не подходит для проектов с меняющимися требованиями
- Высокая стоимость документирования

---

## 5. Спиральная модель ЖЦПО

**Спиральная модель** — предложена Барри Боэмом в 1986 году. Разработка идёт по спирали, каждый виток — новая версия продукта.

### Каждый виток спирали включает 4 фазы:
1. **Определение целей** — задачи текущей итерации, альтернативы, ограничения
2. **Анализ рисков** — выявление и оценка рисков, возможные пути их устранения
3. **Разработка и тестирование** — создание очередной версии продукта
4. **Планирование следующего витка** — анализ результатов, планирование следующей итерации

### Достоинства:
- Риски учитываются на каждом этапе
- Заказчик участвует в процессе и видит промежуточные результаты
- Можно изменять требования в процессе разработки
- Хорошо для крупных и сложных проектов

### Недостатки:
- Сложно планировать сроки и бюджет
- Требует участия опытных специалистов по анализу рисков
- Много документации

---

## 6. Принципы объектно-ориентированного программирования (ООП)

ООП — парадигма программирования, основанная на представлении программы как набора взаимодействующих объектов.

### 4 основных принципа:

**1. Инкапсуляция**
Скрытие внутренней реализации объекта от внешнего мира. Данные и методы объединяются внутри класса, доступ к полям осуществляется через методы (свойства).
```csharp
class Person {
    private string name; // скрытое поле
    public string Name { get => name; set => name = value; } // открытый доступ
}
```

**2. Наследование**
Возможность создавать новый класс на основе существующего. Дочерний класс получает все поля и методы родительского класса и может добавлять свои.
```csharp
class Animal { public void Eat() { } }
class Dog : Animal { public void Bark() { } } // Dog наследует Eat()
```

**3. Полиморфизм**
Способность объектов разных классов реагировать на один и тот же метод по-разному. Достигается через виртуальные методы и переопределение.
```csharp
class Animal { public virtual string Sound() => "..."; }
class Cat : Animal { public override string Sound() => "Мяу"; }
class Dog : Animal { public override string Sound() => "Гав"; }
```

**4. Абстракция**
Выделение существенных характеристик объекта и игнорирование несущественных деталей. Реализуется через абстрактные классы и интерфейсы.
```csharp
abstract class Shape {
    public abstract double Area(); // что делать — определено, как — нет
}
```

---

## 7. Структурное программирование

**Структурное программирование** — методология разработки ПО, предложенная Дейкстрой в 1960-х. Основана на разбиении программы на логические блоки.

### Основные принципы:
1. **Использование только трёх управляющих конструкций:**
   - Последовательность (одна инструкция за другой)
   - Ветвление (if/else, switch)
   - Цикл (for, while, do-while)

2. **Отказ от оператора GOTO** — безусловных переходов, которые делают код запутанным («спагетти-код»)

3. **Декомпозиция** — разбиение задачи на подзадачи (процедуры и функции)

### Достоинства:
- Код легче читать и понимать
- Упрощается отладка и тестирование
- Улучшается сопровождаемость программы

### В C# структурное программирование реализуется через:
- Методы и функции
- Управляющие конструкции (if, for, while, switch)
- Разбиение на классы и модули

---

## 8. Модульное программирование

**Модульное программирование** — методология, при которой программа разбивается на независимые части — **модули**, каждый из которых решает конкретную подзадачу.

### Свойства модуля:
- **Функциональная завершённость** — выполняет одну чётко определённую задачу
- **Независимость** — минимальные зависимости от других модулей
- **Интерфейс** — чётко определённый способ взаимодействия с другими модулями

### Преимущества:
- Разные разработчики могут работать над разными модулями одновременно
- Модуль можно тестировать отдельно
- Модуль можно переиспользовать в других проектах
- Проще найти и исправить ошибку

### В C# модульность реализуется через:
- Классы и пространства имён (namespaces)
- Библиотеки классов (DLL-файлы)
- Разбиение на файлы и папки проекта

---

## 9. Язык визуального моделирования UML

**UML (Unified Modeling Language)** — унифицированный язык моделирования, стандарт для визуального описания программных систем.

### Назначение:
- Документирование архитектуры системы
- Общение между разработчиками и заказчиками
- Проектирование до написания кода

### Виды диаграмм UML (основные):

| Тип | Описание |
|-----|----------|
| Use Case (вариантов использования) | Описывает функциональность с точки зрения пользователя |
| Классов (Class) | Структура классов, их поля, методы и связи |
| Последовательности (Sequence) | Взаимодействие объектов во времени |
| Состояний (State) | Возможные состояния объекта и переходы между ними |
| Деятельности (Activity) | Алгоритм или бизнес-процесс (похожа на блок-схему) |
| Компонентов | Архитектура системы на уровне компонентов |
| Развёртывания | Распределение ПО по оборудованию |

---

## 10. Use Case Diagram (Диаграмма вариантов использования)

**Use Case Diagram** — диаграмма, показывающая, как пользователи взаимодействуют с системой.

### Основные элементы:
- **Актор (Actor)** — пользователь или внешняя система, взаимодействующая с системой. Изображается в виде человечка.
- **Вариант использования (Use Case)** — функция системы, которую может вызвать актор. Изображается в виде эллипса.
- **Система** — прямоугольник, внутри которого находятся варианты использования.
- **Связи:**
  - **Ассоциация** — линия между актором и вариантом использования
  - **Include** — один вариант использования обязательно включает другой (`<<include>>`)
  - **Extend** — один вариант использования может расширять другой (`<<extend>>`)
  - **Generalization** — наследование между акторами или вариантами использования

### Пример:
Система интернет-магазина:
- Акторы: Покупатель, Администратор
- Варианты использования: Просмотр товаров, Оформление заказа, Оплата, Управление каталогом

---

## 11. Диаграмма последовательности (Sequence Diagram)

**Диаграмма последовательности** — показывает порядок взаимодействия объектов во времени.

### Основные элементы:
- **Объекты (участники)** — изображаются прямоугольниками вверху диаграммы
- **Линия жизни (Lifeline)** — вертикальная пунктирная линия от объекта вниз, показывает существование объекта во времени
- **Активация** — прямоугольник на линии жизни, показывает, что объект в данный момент выполняет операцию
- **Сообщения** — стрелки между линиями жизни:
  - Синхронное сообщение — сплошная стрелка с закрашенным наконечником
  - Асинхронное сообщение — сплошная стрелка с открытым наконечником
  - Возврат — пунктирная стрелка

### Пример (авторизация):
```
Пользователь → Форма: нажать «Войти»
Форма → Контроллер: проверить данные
Контроллер → База данных: найти пользователя
База данных → Контроллер: результат
Контроллер → Форма: показать результат
```

---

## 12. Характеристика языка C#

**C#** (произносится «си шарп») — объектно-ориентированный язык программирования, разработан Microsoft в 2000 году (Андерс Хейлсберг). Является основным языком платформы .NET.

### Характеристики:
- **Объектно-ориентированный** — всё является объектом, поддерживает инкапсуляцию, наследование, полиморфизм
- **Строго типизированный** — тип каждой переменной определяется при объявлении
- **Компилируемый** — компилируется в промежуточный язык (IL), затем JIT-компилятор преобразует его в машинный код
- **Управляемый** — управление памятью осуществляет среда CLR (сборщик мусора)
- **Кроссплатформенный** — .NET 5+ работает на Windows, Linux, macOS
- **Синтаксис** — похож на Java и C++

### Применение:
- Десктопные приложения (Windows Forms, WPF)
- Веб-приложения (ASP.NET Core)
- Мобильные приложения (Xamarin, MAUI)
- Игры (Unity)
- Серверные приложения

---

## 13. Структура программы C#

Базовая структура программы на C#:

```csharp
// 1. Подключение пространств имён
using System;
using System.Collections.Generic;

// 2. Объявление пространства имён
namespace МоёПриложение
{
    // 3. Объявление класса
    class Program
    {
        // 4. Точка входа — метод Main
        static void Main(string[] args)
        {
            // 5. Тело программы
            Console.WriteLine("Привет, мир!");
        }
    }
}
```

### Составные части:
| Элемент | Назначение |
|---------|-----------|
| `using` | Подключение пространств имён |
| `namespace` | Логическая группировка кода |
| `class` | Определение класса |
| `Main()` | Точка входа в программу (выполняется первой) |
| `{}` | Фигурные скобки обозначают блоки кода |

---

## 14. Программы верхнего уровня C# (Top-level statements)

Начиная с **C# 9** (2020) можно писать код без явного объявления класса и метода `Main`. Это называется **программы верхнего уровня**.

### Пример — раньше:
```csharp
using System;
namespace App {
    class Program {
        static void Main(string[] args) {
            Console.WriteLine("Привет!");
        }
    }
}
```

### Пример — с C# 9:
```csharp
Console.WriteLine("Привет!");
```

### Правила:
- Только один файл в проекте может содержать код верхнего уровня
- `using`-директивы пишутся в начале файла
- Можно определять методы и классы ниже кода верхнего уровня
- Параметры `args` доступны без явного объявления

---

## 15. Переменные C#

**Переменная** — именованная область памяти, хранящая значение определённого типа.

### Объявление:
```csharp
тип имяПеременной;           // объявление
тип имяПеременной = значение; // объявление с инициализацией
```

### Примеры:
```csharp
int age = 20;
double price = 99.99;
string name = "Артас";
bool isActive = true;
```

### Правила именования:
- Начинается с буквы или символа `_`
- Может содержать буквы, цифры, `_`
- Регистрозависимо: `name` и `Name` — разные переменные
- Нельзя использовать ключевые слова (`int`, `class` и т.д.)

### Ключевое слово var:
```csharp
var x = 10;      // компилятор сам определит тип int
var s = "текст"; // тип string
```
Тип определяется автоматически из значения (вывод типа).

---

## 16. Типы данных C#

### Встроенные типы данных:

**Целочисленные:**
| Тип | Размер | Диапазон |
|-----|--------|----------|
| `byte` | 1 байт | 0..255 |
| `sbyte` | 1 байт | -128..127 |
| `short` | 2 байта | -32768..32767 |
| `ushort` | 2 байта | 0..65535 |
| `int` | 4 байта | ≈ -2.1 млрд..2.1 млрд |
| `uint` | 4 байта | 0..≈ 4.3 млрд |
| `long` | 8 байт | очень большие числа |
| `ulong` | 8 байт | 0..очень большие |

**Вещественные:**
| Тип | Размер | Точность |
|-----|--------|----------|
| `float` | 4 байта | 7 знаков |
| `double` | 8 байт | 15–16 знаков |
| `decimal` | 16 байт | 28–29 знаков (финансы) |

**Прочие:**
| Тип | Описание | Пример |
|-----|----------|--------|
| `bool` | Логический | `true` / `false` |
| `char` | Один символ Unicode | `'A'` |
| `string` | Строка (ссылочный тип) | `"Привет"` |
| `object` | Базовый тип всех типов | любое значение |

### Типы-значения и ссылочные типы:
- **Value types** (int, double, bool, char, struct) — хранят значение напрямую в стеке
- **Reference types** (string, class, array) — хранят ссылку на объект в куче

---

## 17. Арифметические операции C#

| Оператор | Описание | Пример |
|----------|----------|--------|
| `+` | Сложение | `5 + 3 = 8` |
| `-` | Вычитание | `5 - 3 = 2` |
| `*` | Умножение | `5 * 3 = 15` |
| `/` | Деление | `10 / 3 = 3` (целочисл.) / `10.0/3 = 3.333` |
| `%` | Остаток от деления | `10 % 3 = 1` |

### Операторы инкремента/декремента:
```csharp
int x = 5;
x++;  // x = 6 (постфиксный — сначала использует, потом увеличивает)
++x;  // x = 7 (префиксный — сначала увеличивает, потом использует)
x--;  // x = 6
--x;  // x = 5
```

### Составные операторы присваивания:
```csharp
x += 3;  // x = x + 3
x -= 2;  // x = x - 2
x *= 4;  // x = x * 4
x /= 2;  // x = x / 2
x %= 3;  // x = x % 3
```

### Важно — целочисленное деление:
```csharp
int a = 7 / 2;       // a = 3 (дробная часть отбрасывается)
double b = 7.0 / 2;  // b = 3.5
double c = (double)7 / 2; // c = 3.5 (явное приведение)
```

---

## 18. Ассоциативность операторов C#

**Ассоциативность** определяет порядок выполнения операторов с одинаковым приоритетом.

### Приоритет операторов (от высшего к низшему):
| Приоритет | Операторы |
|-----------|-----------|
| 1 (высший) | `()` скобки, `[]` индексация, `.` доступ к члену |
| 2 | `++`, `--` (постфикс), `!`, `~`, унарный `-` |
| 3 | `*`, `/`, `%` |
| 4 | `+`, `-` |
| 5 | `<<`, `>>` (битовые сдвиги) |
| 6 | `<`, `>`, `<=`, `>=` |
| 7 | `==`, `!=` |
| 8 | `&&` |
| 9 | `\|\|` |
| 10 (низший) | `=`, `+=`, `-=` и др. |

### Лево-ассоциативность (большинство операторов):
```csharp
int x = 10 - 3 - 2; // = (10 - 3) - 2 = 5
```

### Право-ассоциативность (операторы присваивания):
```csharp
int a, b, c;
a = b = c = 5; // c=5, потом b=5, потом a=5
```

---

## 19. Условные выражения C#

Используются для выполнения разных блоков кода в зависимости от условия.

### Операторы сравнения:
| Оператор | Значение |
|----------|----------|
| `==` | равно |
| `!=` | не равно |
| `>` | больше |
| `<` | меньше |
| `>=` | больше или равно |
| `<=` | меньше или равно |

### Логические операторы:
| Оператор | Значение |
|----------|----------|
| `&&` | И (логическое И) |
| `\|\|` | ИЛИ (логическое ИЛИ) |
| `!` | НЕ (логическое отрицание) |

### Примеры:
```csharp
bool result = (5 > 3) && (2 < 10); // true
bool r2 = (5 > 3) || (2 > 10);     // true
bool r3 = !(5 > 3);                 // false
```

---

## 20. Конструкция if...else и тернарная операция C#

### if...else:
```csharp
if (условие)
{
    // выполняется если условие true
}
else if (другое условие)
{
    // выполняется если второе условие true
}
else
{
    // выполняется если все условия false
}
```

### Пример:
```csharp
int age = 18;
if (age >= 18)
    Console.WriteLine("Совершеннолетний");
else
    Console.WriteLine("Несовершеннолетний");
```

### Тернарный оператор (? :):
Краткая форма if-else для простых условий:
```csharp
результат = условие ? значение_если_true : значение_если_false;
```

### Пример:
```csharp
int a = 10, b = 5;
int max = (a > b) ? a : b; // max = 10

string msg = (age >= 18) ? "Взрослый" : "Ребёнок";
```

---

## 21. Цикл for C#

**Цикл for** используется, когда заранее известно количество повторений.

### Синтаксис:
```csharp
for (инициализация; условие; обновление)
{
    // тело цикла
}
```

### Пример:
```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i); // выведет 0, 1, 2, 3, 4
}
```

### Порядок выполнения:
1. Выполняется инициализация (`int i = 0`) — один раз
2. Проверяется условие (`i < 5`) — если false, цикл завершается
3. Выполняется тело цикла
4. Выполняется обновление (`i++`)
5. Переход к шагу 2

### Вложенные циклы:
```csharp
for (int i = 1; i <= 3; i++)
    for (int j = 1; j <= 3; j++)
        Console.Write($"{i}x{j}={i*j}\t");
```

---

## 22. Цикл do...while C#

**Цикл do...while** — тело цикла выполняется **хотя бы один раз**, так как условие проверяется после выполнения тела.

### Синтаксис:
```csharp
do
{
    // тело цикла
}
while (условие);
```

### Пример:
```csharp
int i = 0;
do
{
    Console.WriteLine(i);
    i++;
}
while (i < 5); // выведет 0, 1, 2, 3, 4
```

### Отличие от while:
```csharp
int x = 10;
while (x < 5) { Console.WriteLine(x); } // не выполнится ни разу

do { Console.WriteLine(x); } while (x < 5); // выполнится 1 раз
```

---

## 23. Цикл while C#

**Цикл while** выполняется, пока условие истинно. Условие проверяется **до** выполнения тела.

### Синтаксис:
```csharp
while (условие)
{
    // тело цикла
}
```

### Пример:
```csharp
int i = 0;
while (i < 5)
{
    Console.WriteLine(i);
    i++;
}
```

### Бесконечный цикл:
```csharp
while (true)
{
    // выполняется бесконечно
    // выход через break
}
```

---

## 24. Цикл foreach C#

**Цикл foreach** используется для перебора элементов коллекций и массивов.

### Синтаксис:
```csharp
foreach (тип переменная in коллекция)
{
    // тело цикла
}
```

### Примеры:
```csharp
int[] numbers = { 1, 2, 3, 4, 5 };
foreach (int n in numbers)
    Console.WriteLine(n);

string[] names = { "Анна", "Борис", "Виктор" };
foreach (string name in names)
    Console.WriteLine(name);
```

### Особенности:
- Нельзя изменять коллекцию во время перебора
- Нельзя получить индекс элемента напрямую (нужен отдельный счётчик)
- Работает с любыми объектами, реализующими `IEnumerable`

---

## 25. Операторы continue и break C#

### break — досрочный выход из цикла:
```csharp
for (int i = 0; i < 10; i++)
{
    if (i == 5) break; // выход при i=5
    Console.WriteLine(i); // выведет 0, 1, 2, 3, 4
}
```

### continue — пропуск текущей итерации:
```csharp
for (int i = 0; i < 10; i++)
{
    if (i % 2 == 0) continue; // пропустить чётные
    Console.WriteLine(i); // выведет 1, 3, 5, 7, 9
}
```

### Применение в вложенных циклах:
`break` и `continue` действуют только на **ближайший** вложенный цикл:
```csharp
for (int i = 0; i < 3; i++)
{
    for (int j = 0; j < 3; j++)
    {
        if (j == 1) break; // выход только из внутреннего цикла
        Console.Write($"{i},{j} ");
    }
}
```

---

## 26. Массивы C#

**Массив** — структура данных, хранящая фиксированное количество элементов одного типа.

### Объявление и инициализация:
```csharp
// Одномерный массив
int[] arr = new int[5];           // массив из 5 нулей
int[] arr2 = { 1, 2, 3, 4, 5 }; // с инициализацией
int[] arr3 = new int[] { 1, 2, 3 };

// Доступ к элементам (индекс с 0)
arr[0] = 10;
int x = arr[0];

// Длина массива
int len = arr.Length;
```

### Многомерный массив (матрица):
```csharp
int[,] matrix = new int[3, 4]; // 3 строки, 4 столбца
matrix[0, 0] = 1;
int val = matrix[1, 2];

// Размеры
int rows = matrix.GetLength(0); // количество строк
int cols = matrix.GetLength(1); // количество столбцов
```

### Перебор массива:
```csharp
for (int i = 0; i < arr.Length; i++)
    Console.WriteLine(arr[i]);

foreach (int item in arr)
    Console.WriteLine(item);
```

---

## 27. Методы C#

**Метод** — именованный блок кода, выполняющий определённую задачу. Может принимать параметры и возвращать результат.

### Синтаксис:
```csharp
модификатор тип_возврата ИмяМетода(параметры)
{
    // тело метода
    return значение; // если тип не void
}
```

### Примеры:
```csharp
// Метод без параметров и возврата
void Greet()
{
    Console.WriteLine("Привет!");
}

// Метод с параметрами и возвратом
int Add(int a, int b)
{
    return a + b;
}

// Вызов методов
Greet();
int result = Add(3, 5); // result = 8
```

### Краткая запись (expression-bodied):
```csharp
int Square(int x) => x * x;
void Print(string s) => Console.WriteLine(s);
```

---

## 28. Параметры методов C#

### Обычные параметры (по значению):
```csharp
void Change(int x) { x = 100; } // изменение не влияет на оригинал
int a = 5;
Change(a);
// a всё ещё равно 5
```

### Параметры по ссылке (ref):
```csharp
void Change(ref int x) { x = 100; }
int a = 5;
Change(ref a);
// a = 100
```

### Выходные параметры (out):
```csharp
void GetMinMax(int[] arr, out int min, out int max)
{
    min = arr[0]; max = arr[0];
    foreach (int n in arr) { if (n < min) min = n; if (n > max) max = n; }
}
int[] data = { 3, 1, 5, 2 };
GetMinMax(data, out int minimum, out int maximum);
```

### Входные параметры (in):
```csharp
void Print(in int x) { Console.WriteLine(x); }
// x нельзя изменить внутри метода — только чтение
```

### Массив параметров (params):
```csharp
int Sum(params int[] nums) { int s = 0; foreach (int n in nums) s += n; return s; }
int result = Sum(1, 2, 3, 4, 5); // можно передать любое количество
```

---

## 29. Необязательные и именованные параметры методов C#

### Необязательные параметры (со значением по умолчанию):
```csharp
void Greet(string name, string greeting = "Привет")
{
    Console.WriteLine($"{greeting}, {name}!");
}

Greet("Артас");             // Привет, Артас!
Greet("Артас", "Здравствуй"); // Здравствуй, Артас!
```
Параметры со значением по умолчанию должны стоять **после** обязательных.

### Именованные параметры:
Позволяют передавать аргументы в любом порядке, указывая имя параметра:
```csharp
void Order(string product, int count, double price) { ... }

Order(price: 9.99, product: "Хлеб", count: 2); // порядок не важен
```

---

## 30. Возвращение значения. Оператор return C#

**return** — завершает выполнение метода и возвращает значение вызывающему коду.

```csharp
int Max(int a, int b)
{
    if (a > b) return a; // ранний выход
    return b;
}

// void-методы могут использовать return для раннего выхода:
void PrintPositive(int n)
{
    if (n <= 0) return; // выход без возврата значения
    Console.WriteLine(n);
}
```

### Возврат нескольких значений через кортеж:
```csharp
(int min, int max) GetMinMax(int a, int b)
{
    return (Math.Min(a, b), Math.Max(a, b));
}

var (min, max) = GetMinMax(5, 3);
```

---

## 31. Передача параметров по значению C#

При передаче по значению метод получает **копию** переменной. Изменения внутри метода не влияют на оригинал.

```csharp
void Double(int x)
{
    x = x * 2;
    Console.WriteLine($"Внутри метода: {x}"); // 20
}

int a = 10;
Double(a);
Console.WriteLine($"После вызова: {a}"); // 10 — не изменилось!
```

Это поведение **по умолчанию** для всех типов-значений (int, double, bool, char, struct).

Для ссылочных типов (классов) передаётся копия **ссылки**, но объект — тот же. Поэтому изменение свойств объекта будет видно снаружи.

---

## 32. Передача по ссылке. Модификатор ref C#

`ref` позволяет передать переменную по ссылке — метод работает с **оригинальной** переменной.

```csharp
void Swap(ref int a, ref int b)
{
    int temp = a;
    a = b;
    b = temp;
}

int x = 5, y = 10;
Swap(ref x, ref y);
Console.WriteLine($"x={x}, y={y}"); // x=10, y=5
```

### Требования к ref:
- Переменная должна быть **инициализирована** перед передачей
- Ключевое слово `ref` указывается и при объявлении метода, и при вызове

---

## 33. Выходные параметры. Модификатор out C#

`out` — похож на `ref`, но переменную не нужно инициализировать перед передачей. Метод **обязан** присвоить значение out-параметру.

```csharp
bool TryParse(string s, out int result)
{
    if (int.TryParse(s, out result))
        return true;
    result = 0;
    return false;
}

// Использование:
if (TryParse("123", out int num))
    Console.WriteLine(num); // 123
```

### Отличия ref от out:
| | ref | out |
|--|-----|-----|
| Инициализация до вызова | Обязательна | Не нужна |
| Присваивание в методе | Не обязательно | Обязательно |

---

## 34. Входные параметры. Модификатор in C#

`in` — передаёт параметр по ссылке, но запрещает его изменение внутри метода (только чтение).

```csharp
void Print(in int value)
{
    // value = 10; // ОШИБКА — нельзя изменять
    Console.WriteLine(value);
}

int x = 5;
Print(in x);
```

### Зачем нужен:
- Эффективность при передаче больших структур (без копирования)
- Гарантия неизменности параметра

---

## 35. Рекурсивные функции C#

**Рекурсия** — это когда метод вызывает сам себя. Каждый рекурсивный метод должен иметь:
1. **Базовый случай** — условие завершения рекурсии (иначе бесконечный вызов)
2. **Рекурсивный случай** — вызов самого себя с изменёнными параметрами

### Пример — факториал:
```csharp
long Factorial(int n)
{
    if (n <= 1) return 1;       // базовый случай
    return n * Factorial(n - 1); // рекурсивный случай
}
// Factorial(5) = 5 * 4 * 3 * 2 * 1 = 120
```

### Пример — числа Фибоначчи:
```csharp
long Fibonacci(int n)
{
    if (n <= 1) return n;
    return Fibonacci(n - 1) + Fibonacci(n - 2);
}
```

### Опасность рекурсии:
При очень глубокой рекурсии возникает `StackOverflowException`. Поэтому для больших значений лучше использовать цикл.

---

## 36. Конструкция switch C#

**switch** — альтернатива длинной цепочке if-else для проверки одной переменной на несколько значений.

### Классический синтаксис:
```csharp
switch (переменная)
{
    case значение1:
        // действие
        break;
    case значение2:
        // действие
        break;
    default:
        // если ничего не совпало
        break;
}
```

### Пример:
```csharp
int day = 3;
switch (day)
{
    case 1: Console.WriteLine("Понедельник"); break;
    case 2: Console.WriteLine("Вторник"); break;
    case 3: Console.WriteLine("Среда"); break;
    default: Console.WriteLine("Другой день"); break;
}
```

### Несколько значений для одного case:
```csharp
switch (month)
{
    case 12:
    case 1:
    case 2:
        Console.WriteLine("Зима");
        break;
}
```

---

## 37. Возвращение значения из switch C#

Начиная с **C# 8** появилось **switch-выражение** (switch expression), которое возвращает значение.

### Синтаксис:
```csharp
var result = переменная switch
{
    значение1 => результат1,
    значение2 => результат2,
    _ => результатПоУмолчанию // _ вместо default
};
```

### Пример:
```csharp
int day = 3;
string name = day switch
{
    1 => "Понедельник",
    2 => "Вторник",
    3 => "Среда",
    4 => "Четверг",
    5 => "Пятница",
    _ => "Выходной"
};
Console.WriteLine(name); // Среда
```

---

## 38. Получение результата из switch C#

В switch можно возвращать результат несколькими способами:

### 1. Через переменную:
```csharp
string season;
switch (month)
{
    case 12: case 1: case 2: season = "Зима"; break;
    case 3: case 4: case 5: season = "Весна"; break;
    default: season = "Другое"; break;
}
```

### 2. Через return в методе:
```csharp
string GetSeason(int month)
{
    switch (month)
    {
        case 12: case 1: case 2: return "Зима";
        case 3: case 4: case 5: return "Весна";
        default: return "Другое";
    }
}
```

### 3. Switch-выражение (C# 8+):
```csharp
string season = month switch
{
    12 or 1 or 2 => "Зима",
    3 or 4 or 5  => "Весна",
    6 or 7 or 8  => "Лето",
    _            => "Осень"
};
```

---

## 39. Классы, структуры и пространства имён C#

### Класс (class):
Ссылочный тип. Хранится в куче. Используется для сложных объектов с поведением.
```csharp
class Person
{
    public string Name;
    public void Greet() => Console.WriteLine($"Привет, я {Name}");
}
```

### Структура (struct):
Тип-значение. Хранится в стеке. Используется для небольших объектов без наследования.
```csharp
struct Point
{
    public int X, Y;
}
Point p = new Point { X = 10, Y = 20 };
```

### Отличия class от struct:
| | class | struct |
|--|-------|--------|
| Хранение | Куча (heap) | Стек (stack) |
| Передача | По ссылке | По значению |
| Наследование | Да | Нет |
| null | Может быть null | Не может |

---

## 40. Классы и объекты C#

**Класс** — шаблон (чертёж) для создания объектов. Определяет поля, свойства и методы.

**Объект** — экземпляр класса, созданный по этому шаблону.

```csharp
// Определение класса
class Car
{
    public string Brand;
    public int Year;

    public void Start() => Console.WriteLine($"{Brand} заведён");
}

// Создание объектов
Car car1 = new Car();
car1.Brand = "Toyota";
car1.Year = 2020;
car1.Start(); // Toyota заведён

Car car2 = new Car { Brand = "BMW", Year = 2022 }; // инициализатор
```

---

## 41. Создание конструкторов класса C#

**Конструктор** — специальный метод класса, вызываемый при создании объекта. Имя совпадает с именем класса, не имеет возвращаемого типа.

```csharp
class Person
{
    public string Name;
    public int Age;

    // Конструктор без параметров (по умолчанию)
    public Person()
    {
        Name = "Неизвестно";
        Age = 0;
    }

    // Конструктор с параметрами
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}

// Использование:
Person p1 = new Person();               // конструктор по умолчанию
Person p2 = new Person("Артас", 20);    // с параметрами
```

### Перегрузка конструкторов:
В одном классе может быть несколько конструкторов с разными наборами параметров.

---

## 42. Ключевое слово this C#

`this` — ссылка на **текущий объект** класса. Используется для:

### 1. Разграничения полей и параметров с одинаковыми именами:
```csharp
class Person
{
    private string name;

    public Person(string name)
    {
        this.name = name; // this.name — поле, name — параметр
    }
}
```

### 2. Вызова другого конструктора того же класса:
```csharp
class Point
{
    public int X, Y;

    public Point() : this(0, 0) { } // вызов конструктора с параметрами

    public Point(int x, int y)
    {
        X = x; Y = y;
    }
}
```

### 3. Передачи текущего объекта в качестве параметра:
```csharp
void Register(Person p) { ... }
Register(this); // передаём текущий объект
```

---

## 43. Инициализаторы объектов класса C#

**Инициализаторы объектов** позволяют задавать значения свойств и публичных полей сразу при создании объекта, без специального конструктора.

```csharp
class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
    public string City { get; set; }
}

// Инициализатор объекта:
Person p = new Person
{
    Name = "Артас",
    Age = 20,
    City = "Москва"
};

// Совмещение с конструктором:
Person p2 = new Person("Борис") { Age = 25, City = "Питер" };
```

---

## 44. Область видимости переменных и констант C#

**Область видимости** — часть программы, в которой переменная доступна.

### Виды:
```csharp
int globalVar = 10; // уровень класса — видна во всём классе

void Method()
{
    int localVar = 5; // локальная — видна только в этом методе

    for (int i = 0; i < 3; i++)
    {
        int loopVar = i * 2; // видна только внутри цикла
    }
    // loopVar здесь недоступна
}
```

### Константы:
```csharp
const double PI = 3.14159; // значение нельзя изменить
const int MAX_SIZE = 100;
```
- `const` — известна в момент компиляции, всегда `static`
- `readonly` — может быть присвоена только в конструкторе

---

## 45. Пространства имён C#

**Пространство имён (namespace)** — логическая группировка связанных классов и типов.

### Объявление:
```csharp
namespace МоёПриложение
{
    class Program { }
    class Helper { }
}
```

### Подключение:
```csharp
using System;               // стандартная библиотека
using System.Collections.Generic; // коллекции
using МоёПриложение;         // своё пространство
```

### Вложенные пространства имён:
```csharp
namespace МоёПриложение.Модели
{
    class User { }
}
// Подключение: using МоёПриложение.Модели;
```

### Пространства имён уровня файла (C# 10+):
```csharp
namespace МоёПриложение; // без фигурных скобок — распространяется на весь файл

class Program { } // принадлежит пространству МоёПриложение
```

---

## 46. Глобальные пространства имён C#

Начиная с **C# 10** можно объявить глобальный `using`, который применяется ко **всем файлам** проекта:

```csharp
global using System;
global using System.Collections.Generic;
```

### Неявные глобальные using:
В проектах .NET 6+ часть `using` подключается **автоматически** (без явного указания):
- `System`
- `System.Collections.Generic`
- `System.Linq`
- `System.Threading.Tasks`
- и другие

Это настраивается в файле `.csproj`:
```xml
<ImplicitUsings>enable</ImplicitUsings>
```

---

## 47. Подключение пространств имён по умолчанию C#

В .NET 6+ при создании нового проекта уже подключены следующие пространства:

```csharp
global using global::System;
global using global::System.Collections.Generic;
global using global::System.IO;
global using global::System.Linq;
global using global::System.Net.Http;
global using global::System.Threading;
global using global::System.Threading.Tasks;
```

Это позволяет использовать `Console`, `List<T>`, `Task` и т.д. без явных `using`-директив.

Отключить можно в `.csproj`:
```xml
<ImplicitUsings>disable</ImplicitUsings>
```

---

## 48. Библиотеки классов C#

**Библиотека классов (Class Library)** — проект, который компилируется в `.dll`-файл и может использоваться другими проектами.

### Создание:
В Visual Studio: Файл → Создать → Проект → Class Library

### Структура:
```csharp
// В файле MathHelper.cs
namespace МояБиблиотека
{
    public class MathHelper
    {
        public static int Add(int a, int b) => a + b;
        public static double Sqrt(double x) => Math.Sqrt(x);
    }
}
```

### Подключение к другому проекту:
1. Правой кнопкой на проекте → Добавить ссылку
2. Выбрать нужный проект или `.dll`-файл
3. Добавить `using МояБиблиотека;` в код

### Зачем нужны:
- Переиспользование кода в нескольких проектах
- Разделение ответственности (разные команды)
- Публикация в NuGet-пакеты

---

## 49. Модификаторы доступа C#

**Модификаторы доступа** определяют, откуда можно обращаться к члену класса.

| Модификатор | Доступ |
|-------------|--------|
| `public` | Откуда угодно |
| `private` | Только внутри того же класса |
| `protected` | Внутри класса и его наследников |
| `internal` | Только внутри той же сборки (.dll или .exe) |
| `protected internal` | В той же сборке или в наследниках |
| `private protected` | В том же классе и наследниках в той же сборке |

### Пример:
```csharp
class BankAccount
{
    private double balance;           // только внутри класса
    public string Owner { get; set; } // везде
    protected void Log() { }         // класс и наследники
}
```

### Правило:
По умолчанию поля — `private`, классы — `internal`.

---

## 50. Свойства — специальные методы доступа C#

**Свойство** — специальный механизм для доступа к приватным полям класса через аксессоры `get` и `set`. Выглядит как поле, но работает как методы.

```csharp
class Person
{
    private int age; // приватное поле

    public int Age  // свойство
    {
        get { return age; }
        set
        {
            if (value < 0) throw new Exception("Возраст не может быть отрицательным");
            age = value;
        }
    }
}

Person p = new Person();
p.Age = 20;      // вызывает set
int a = p.Age;   // вызывает get
```

---

## 51. Вычисляемые свойства C#

**Вычисляемое свойство** — свойство, значение которого вычисляется при каждом обращении, а не хранится в отдельном поле.

```csharp
class Rectangle
{
    public double Width { get; set; }
    public double Height { get; set; }

    // Вычисляемое свойство — нет отдельного поля
    public double Area => Width * Height;
    public double Perimeter => 2 * (Width + Height);
}

Rectangle r = new Rectangle { Width = 5, Height = 3 };
Console.WriteLine(r.Area);      // 15
Console.WriteLine(r.Perimeter); // 16
```

---

## 52. Автоматические свойства C#

**Автоматическое свойство** — краткая запись, при которой компилятор сам создаёт скрытое поле.

```csharp
class Person
{
    // Полная запись
    private string name;
    public string Name { get { return name; } set { name = value; } }

    // Автоматическое свойство (то же самое, но короче)
    public string Name { get; set; }
    public int Age { get; set; }

    // Только для чтения (можно задать только в конструкторе)
    public string Id { get; } = Guid.NewGuid().ToString();

    // Начальное значение
    public int Count { get; set; } = 0;
}
```

---

## 53. Перегрузка методов C#

**Перегрузка** — возможность иметь в одном классе несколько методов с **одинаковым именем**, но **разными параметрами**.

```csharp
class Calculator
{
    public int Add(int a, int b) => a + b;
    public double Add(double a, double b) => a + b;
    public int Add(int a, int b, int c) => a + b + c;
    public string Add(string a, string b) => a + b; // конкатенация
}

var calc = new Calculator();
calc.Add(1, 2);          // вызовет int-версию
calc.Add(1.5, 2.5);      // вызовет double-версию
calc.Add(1, 2, 3);       // вызовет трёхпараметровую
```

Компилятор выбирает нужный метод по типу и количеству аргументов.

**Нельзя** перегружать методы, отличающиеся только возвращаемым типом.

---

## 54. Статические поля C#

**Статическое поле** — принадлежит **классу**, а не объекту. Существует в единственном экземпляре, общем для всех объектов класса.

```csharp
class Counter
{
    private static int count = 0; // одно на весь класс

    public Counter()
    {
        count++; // каждый новый объект увеличивает счётчик
    }

    public static int GetCount() => count;
}

var c1 = new Counter();
var c2 = new Counter();
var c3 = new Counter();
Console.WriteLine(Counter.GetCount()); // 3
```

Доступ: через имя класса `Counter.GetCount()`, а не через объект.

---

## 55. Статические свойства C#

**Статическое свойство** — свойство, принадлежащее классу, а не экземпляру.

```csharp
class AppSettings
{
    private static string appName = "МоёПриложение";

    public static string AppName
    {
        get => appName;
        set => appName = value;
    }

    public static int MaxUsers { get; set; } = 100;
}

// Доступ через имя класса:
Console.WriteLine(AppSettings.AppName);
AppSettings.MaxUsers = 200;
```

---

## 56. Статические методы и конструкторы C#

### Статический метод:
```csharp
class MathHelper
{
    public static double Square(double x) => x * x;
    public static double Sqrt(double x) => Math.Sqrt(x);
}

// Вызов без создания объекта:
double result = MathHelper.Square(5); // 25
```

### Статический конструктор:
Вызывается **один раз** при первом обращении к классу (для инициализации статических членов).
```csharp
class Config
{
    public static string ConnectionString;

    static Config() // без модификатора доступа, без параметров
    {
        ConnectionString = "Server=localhost;Database=mydb";
        Console.WriteLine("Конфигурация загружена");
    }
}
```

---

## 57. Проверка на null, операторы ?. и ?? C#

### Проблема null:
Обращение к члену null-объекта вызывает `NullReferenceException`.

### Оператор ?.  (null-conditional):
Обращается к члену только если объект не null, иначе возвращает null.
```csharp
string s = null;
int? len = s?.Length; // len = null, а не исключение

// Вместо:
int length = (s != null) ? s.Length : 0;
// Короче:
int length = s?.Length ?? 0;
```

### Оператор ?? (null-coalescing):
Возвращает левый операнд, если он не null, иначе — правый.
```csharp
string name = null;
string result = name ?? "Не указано"; // "Не указано"

// Оператор ??= (присваивает если null):
name ??= "Гость"; // если name == null, присваивает "Гость"
```

---

## 58. Наследование C#

**Наследование** — механизм, позволяющий создать новый класс на основе существующего.

```csharp
class Animal // базовый класс
{
    public string Name { get; set; }
    public void Eat() => Console.WriteLine($"{Name} ест");
}

class Dog : Animal // производный класс
{
    public void Bark() => Console.WriteLine("Гав!");
}

Dog dog = new Dog();
dog.Name = "Рекс";
dog.Eat();  // унаследованный метод
dog.Bark(); // собственный метод
```

### Ключевое слово base:
Доступ к членам базового класса:
```csharp
class GuideDog : Dog
{
    public GuideDog(string name) : base() // вызов конструктора Dog
    {
        Name = name;
    }

    public new void Bark() => base.Bark(); // вызов метода предка
}
```

### Порядок вызова конструкторов:
При создании объекта сначала вызывается конструктор базового класса, затем производного.

### Запрет наследования — sealed:
```csharp
sealed class FinalClass { } // нельзя наследовать
```

---

## 59. Виртуальные методы и свойства C#

**Виртуальный метод** — метод базового класса, который может быть **переопределён** в производном классе.

```csharp
class Animal
{
    public virtual string Sound() => "...";
    public virtual string Description => $"Животное: {GetType().Name}";
}

class Cat : Animal
{
    public override string Sound() => "Мяу";
}

class Dog : Animal
{
    public override string Sound() => "Гав";
}

Animal a = new Cat();
Console.WriteLine(a.Sound()); // "Мяу" — вызывается метод Cat!
```

Это называется **полиморфизм** — один и тот же вызов `a.Sound()` даёт разный результат в зависимости от реального типа объекта.

`virtual` — разрешает переопределение, `override` — выполняет переопределение.

---

## 60. Абстрактные классы C#

**Абстрактный класс** — класс, который:
- Не может быть создан напрямую (`new AbstractClass()` — ошибка)
- Может содержать абстрактные методы (без реализации)
- Производные классы обязаны реализовать все абстрактные методы

```csharp
abstract class Shape
{
    public string Color { get; set; }

    // Абстрактный метод — без тела
    public abstract double Area();

    // Обычный метод — с телом
    public void Print()
    {
        Console.WriteLine($"Фигура, площадь: {Area()}");
    }
}

class Circle : Shape
{
    public double Radius { get; set; }
    public override double Area() => Math.PI * Radius * Radius;
}

class Rectangle : Shape
{
    public double Width, Height;
    public override double Area() => Width * Height;
}

Shape s = new Circle { Radius = 5, Color = "Красный" };
s.Print();
```

---

## 61. Конструкция try...catch...finally C#

**Обработка исключений** — механизм для перехвата и обработки ошибок во время выполнения программы.

```csharp
try
{
    // Код, который может вызвать исключение
    int result = 10 / 0;
}
catch (DivideByZeroException ex)
{
    // Обработка конкретного исключения
    Console.WriteLine($"Деление на ноль: {ex.Message}");
}
catch (Exception ex)
{
    // Обработка любого другого исключения
    Console.WriteLine($"Ошибка: {ex.Message}");
}
finally
{
    // Выполняется всегда — и при ошибке, и без неё
    Console.WriteLine("Блок finally выполнен");
}
```

### Порядок блоков:
- `try` — обязателен
- `catch` — один или несколько, от частных к общим
- `finally` — необязателен, выполняется всегда (закрытие файлов, соединений)

---

## 62. Типы исключений. Класс Exception C#

**Exception** — базовый класс для всех исключений.

### Иерархия исключений:
```
Exception
├── SystemException
│   ├── NullReferenceException     — обращение к null
│   ├── IndexOutOfRangeException   — выход за границу массива
│   ├── DivideByZeroException      — деление на ноль
│   ├── InvalidCastException       — неверное приведение типа
│   ├── OverflowException          — переполнение числового типа
│   ├── StackOverflowException     — переполнение стека (рекурсия)
│   └── FormatException            — неверный формат данных
└── ApplicationException           — пользовательские исключения
```

### Свойства класса Exception:
```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);    // сообщение об ошибке
    Console.WriteLine(ex.StackTrace); // трассировка стека
    Console.WriteLine(ex.Source);     // источник исключения
}
```

### Создание собственного исключения:
```csharp
class AgeException : Exception
{
    public AgeException(string message) : base(message) { }
}
// Использование:
throw new AgeException("Возраст не может быть отрицательным");
```

---

## 63. Добавление форм. Взаимодействие между формами (Windows Forms)

### Добавление новой формы:
В Visual Studio: ПКМ на проект → Добавить → Форма (Windows Forms)

### Открытие второй формы:
```csharp
// Открыть как дочернее окно (немодальное):
Form2 form2 = new Form2();
form2.Show();

// Открыть как модальное (блокирует родительское):
Form2 form2 = new Form2();
form2.ShowDialog();
```

### Передача данных между формами:
```csharp
// Способ 1 — через конструктор:
class Form2 : Form
{
    public Form2(string message)
    {
        InitializeComponent();
        label1.Text = message;
    }
}
// Вызов: new Form2("Привет!").Show();

// Способ 2 — через публичное свойство:
class Form2 : Form
{
    public string UserName { get; set; }
}
// Вызов:
Form2 f = new Form2();
f.UserName = "Артас";
f.Show();
```

---

## 64. События в Windows Forms C#

**Событие (Event)** — уведомление о том, что произошло какое-то действие (нажатие кнопки, ввод текста и т.д.).

### Подключение обработчика:
```csharp
// В дизайнере — двойной клик по элементу управления
// Или вручную в коде:
button1.Click += button1_Click;

private void button1_Click(object sender, EventArgs e)
{
    MessageBox.Show("Кнопка нажата!");
}
```

### Отключение обработчика:
```csharp
button1.Click -= button1_Click;
```

### Часто используемые события:
| Событие | Описание |
|---------|----------|
| `Click` | Нажатие на элемент |
| `TextChanged` | Изменение текста |
| `KeyDown` / `KeyUp` | Нажатие/отпускание клавиши |
| `MouseMove` | Движение мыши |
| `Load` | Загрузка формы |
| `FormClosing` | Закрытие формы |

---

## 65. Контейнеры Windows Forms C#

**Контейнер** — элемент управления, который может содержать другие элементы.

| Контейнер | Описание |
|-----------|----------|
| `Panel` | Простой контейнер, может иметь рамку и полосы прокрутки |
| `GroupBox` | Группирует элементы с заголовком и рамкой |
| `TabControl` | Вкладки — каждая вкладка (TabPage) — отдельный контейнер |
| `SplitContainer` | Делит форму на 2 панели с разделителем |
| `FlowLayoutPanel` | Автоматически располагает элементы по потоку |
| `TableLayoutPanel` | Располагает элементы по таблице (строки и столбцы) |

### Пример использования TabControl:
```csharp
// В дизайнере добавляем TabControl
// Добавляем вкладки (TabPage)
// На каждой вкладке размещаем нужные элементы
```

---

## 66. Элементы управления Windows Forms C#

| Элемент | Назначение | Ключевые свойства |
|---------|-----------|------------------|
| `Label` | Отображение текста | `Text`, `Font`, `ForeColor` |
| `TextBox` | Ввод однострочного текста | `Text`, `Multiline`, `PasswordChar` |
| `RichTextBox` | Многострочный текст с форматированием | `Text`, `Rtf` |
| `Button` | Кнопка | `Text`, `Click` |
| `CheckBox` | Флажок (да/нет) | `Checked`, `Text` |
| `RadioButton` | Переключатель | `Checked`, `Text` |
| `ComboBox` | Выпадающий список | `Items`, `SelectedItem` |
| `ListBox` | Список с выбором | `Items`, `SelectedItem` |
| `PictureBox` | Отображение изображения | `Image`, `SizeMode` |
| `NumericUpDown` | Числовой счётчик | `Value`, `Minimum`, `Maximum` |
| `DataGridView` | Таблица данных | `DataSource`, `Columns` |
| `ProgressBar` | Индикатор прогресса | `Value`, `Maximum` |
| `Timer` | Таймер | `Interval`, `Tick` |
| `DateTimePicker` | Выбор даты и времени | `Value`, `Format` |

---

## 67. Окно сообщения MessageBox. OpenFileDialog и SaveFileDialog (Windows Forms)

### MessageBox:
```csharp
// Простое сообщение:
MessageBox.Show("Привет!");

// С заголовком:
MessageBox.Show("Операция выполнена", "Информация");

// С кнопками и иконкой:
DialogResult result = MessageBox.Show(
    "Вы уверены?",
    "Подтверждение",
    MessageBoxButtons.YesNo,
    MessageBoxIcon.Question);

if (result == DialogResult.Yes)
    // пользователь нажал «Да»
```

### OpenFileDialog — диалог открытия файла:
```csharp
OpenFileDialog ofd = new OpenFileDialog();
ofd.Filter = "Текстовые файлы|*.txt|Все файлы|*.*";
ofd.Title = "Выберите файл";

if (ofd.ShowDialog() == DialogResult.OK)
{
    string path = ofd.FileName;
    string content = File.ReadAllText(path);
    textBox1.Text = content;
}
```

### SaveFileDialog — диалог сохранения файла:
```csharp
SaveFileDialog sfd = new SaveFileDialog();
sfd.Filter = "Текстовые файлы|*.txt";
sfd.DefaultExt = "txt";

if (sfd.ShowDialog() == DialogResult.OK)
{
    File.WriteAllText(sfd.FileName, textBox1.Text);
}
```

---

## 68. Меню и панели инструментов Windows Forms C#

### MenuStrip — главное меню:
В дизайнере:
1. Перетащить `MenuStrip` на форму
2. Кликать на пустые поля для добавления пунктов меню
3. Двойной клик — создаёт обработчик события

```csharp
private void fileToolStripMenuItem_Click(object sender, EventArgs e)
{
    // действие при нажатии пункта «Файл»
}

private void exitToolStripMenuItem_Click(object sender, EventArgs e)
{
    Application.Exit(); // закрыть приложение
}
```

### ContextMenuStrip — контекстное меню (по ПКМ):
```csharp
// В дизайнере: добавить ContextMenuStrip
// Привязать к элементу через свойство ContextMenuStrip
```

### ToolStrip — панель инструментов:
Содержит кнопки (`ToolStripButton`), разделители, выпадающие списки.

### StatusStrip — строка состояния:
Отображается внизу формы, содержит `ToolStripStatusLabel`.

---

## 69. Технология WPF. Преимущества WPF C#

**WPF (Windows Presentation Foundation)** — технология создания десктопных приложений, часть .NET. Альтернатива Windows Forms.

### Преимущества WPF перед Windows Forms:
1. **XAML** — разметка интерфейса отделена от логики (как HTML от JavaScript)
2. **Гибкость дизайна** — произвольные формы элементов, векторная графика, трансформации
3. **Масштабирование** — интерфейс масштабируется без потери качества (векторный)
4. **Анимации** — встроенная поддержка анимации элементов
5. **Стили и шаблоны** — единый стиль для всего приложения через ресурсы
6. **Data Binding** — мощная привязка данных (MVVM-паттерн)
7. **3D-графика** — встроенная поддержка
8. **Медиа** — видео, аудио, изображения

---

## 70. Файлы отделённого кода WPF C#

В WPF каждое окно состоит из двух файлов:

### MainWindow.xaml — разметка интерфейса:
```xml
<Window x:Class="МоёПриложение.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Моё приложение" Height="350" Width="500">
    <Grid>
        <Button Name="btnOk" Content="Нажми меня" Click="btnOk_Click"/>
    </Grid>
</Window>
```

### MainWindow.xaml.cs — код на C# (код за кадром / code-behind):
```csharp
using System.Windows;

namespace МоёПриложение
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent(); // создаёт элементы из XAML
        }

        private void btnOk_Click(object sender, RoutedEventArgs e)
        {
            MessageBox.Show("Привет!");
        }
    }
}
```

`partial` — означает, что класс разделён между двумя файлами.

---

## 71. Пространства имён из C# в XAML (WPF)

Чтобы использовать классы C# в XAML, нужно объявить пространство имён через `xmlns`:

```xml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="clr-namespace:МоёПриложение"
    xmlns:sys="clr-namespace:System;assembly=mscorlib">

    <!-- Использование локального класса: -->
    <local:МойЭлемент />

    <!-- Использование System.String: -->
    <sys:String>Привет</sys:String>
</Window>
```

### Встроенные пространства XAML:
- `xmlns` — WPF-элементы (Button, Grid, TextBox и т.д.)
- `xmlns:x` — XAML-ключевые слова (x:Name, x:Class, x:Key)
- `xmlns:local` — текущий проект

---

## 72. Компоновка WPF

**Компоновка (Layout)** — система размещения элементов управления на форме. В WPF она гибкая и адаптивная.

### Принципы:
- Элементы автоматически адаптируются к размеру окна
- Нет жёсткой привязки к пикселям (как в WinForms)
- Используются контейнеры компоновки

### Свойства выравнивания:
```xml
<Button HorizontalAlignment="Center"
        VerticalAlignment="Top"
        Width="100" Height="40"
        Margin="10,5,10,5"/>
```

---

## 73. Контейнеры компоновки WPF

| Контейнер | Описание |
|-----------|----------|
| `Grid` | Табличная компоновка (строки и столбцы) |
| `StackPanel` | Элементы укладываются в стопку (вертикально или горизонтально) |
| `WrapPanel` | Элементы переносятся на следующую строку при нехватке места |
| `DockPanel` | Элементы прикрепляются к краям (Top, Bottom, Left, Right) |
| `Canvas` | Абсолютное позиционирование (как в WinForms) |
| `UniformGrid` | Сетка с ячейками одинакового размера |

### Пример Grid:
```xml
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="*"/>
        <ColumnDefinition Width="2*"/>
    </Grid.ColumnDefinitions>

    <Label Grid.Row="0" Grid.Column="0" Content="Имя:"/>
    <TextBox Grid.Row="0" Grid.Column="1"/>
</Grid>
```

### Пример StackPanel:
```xml
<StackPanel Orientation="Vertical">
    <Button Content="Кнопка 1" Margin="5"/>
    <Button Content="Кнопка 2" Margin="5"/>
    <Button Content="Кнопка 3" Margin="5"/>
</StackPanel>
```

---

## 74. Свойства компоновки элементов WPF

| Свойство | Описание |
|----------|----------|
| `Width`, `Height` | Ширина и высота элемента |
| `MinWidth`, `MaxWidth` | Минимальная/максимальная ширина |
| `Margin` | Отступ снаружи элемента (left, top, right, bottom) |
| `Padding` | Отступ внутри элемента (для контейнеров) |
| `HorizontalAlignment` | Горизонтальное выравнивание: Left, Center, Right, Stretch |
| `VerticalAlignment` | Вертикальное выравнивание: Top, Center, Bottom, Stretch |
| `Visibility` | Видимость: Visible, Hidden, Collapsed |

### Размеры:
- Фиксированный: `Width="100"`
- Авто: `Width="Auto"` — подстраивается под содержимое
- Пропорциональный: `Width="*"` (занять всё доступное место), `Width="2*"` (в 2 раза больше)

---

## 75. Элементы управления WPF

| Элемент | Аналог WinForms | Пример XAML |
|---------|----------------|-------------|
| `Label` | Label | `<Label Content="Текст"/>` |
| `TextBlock` | Label (только чтение) | `<TextBlock Text="Текст"/>` |
| `TextBox` | TextBox | `<TextBox x:Name="txtName"/>` |
| `Button` | Button | `<Button Content="ОК" Click="Btn_Click"/>` |
| `CheckBox` | CheckBox | `<CheckBox Content="Согласен" IsChecked="True"/>` |
| `RadioButton` | RadioButton | `<RadioButton Content="Да" GroupName="g1"/>` |
| `ComboBox` | ComboBox | `<ComboBox SelectedIndex="0">` |
| `ListBox` | ListBox | `<ListBox>` |
| `Image` | PictureBox | `<Image Source="photo.jpg"/>` |
| `ProgressBar` | ProgressBar | `<ProgressBar Value="50" Maximum="100"/>` |
| `Slider` | TrackBar | `<Slider Minimum="0" Maximum="100"/>` |
| `DataGrid` | DataGridView | `<DataGrid ItemsSource="{Binding}"/>` |

---

## 76. События клавиатуры WPF

| Событие | Описание |
|---------|----------|
| `KeyDown` | Клавиша нажата |
| `KeyUp` | Клавиша отпущена |
| `PreviewKeyDown` | Как KeyDown, но перехватывается раньше |
| `TextInput` | Введён текстовый символ |

### Пример:
```xml
<TextBox KeyDown="TextBox_KeyDown"/>
```
```csharp
private void TextBox_KeyDown(object sender, KeyEventArgs e)
{
    if (e.Key == Key.Enter)
    {
        MessageBox.Show("Нажат Enter");
        e.Handled = true; // предотвратить дальнейшую обработку
    }
}
```

---

## 77. События мыши и фокуса WPF

### События мыши:
| Событие | Описание |
|---------|----------|
| `MouseDown` / `MouseUp` | Нажатие/отпускание кнопки мыши |
| `MouseMove` | Перемещение мыши |
| `MouseEnter` / `MouseLeave` | Вход/выход курсора в элемент |
| `MouseWheel` | Прокрутка колёсика |

### Пример:
```csharp
private void Element_MouseDown(object sender, MouseButtonEventArgs e)
{
    Point pos = e.GetPosition(this); // координаты относительно окна
    if (e.LeftButton == MouseButtonState.Pressed)
        label1.Content = $"Клик: {pos.X:F0}, {pos.Y:F0}";
}
```

### События фокуса:
| Событие | Описание |
|---------|----------|
| `GotFocus` | Элемент получил фокус |
| `LostFocus` | Элемент потерял фокус |
| `IsKeyboardFocusedChanged` | Изменился фокус клавиатуры |

---

## 78. WPF Ресурсы

**Ресурсы WPF** — объекты (стили, кисти, шаблоны, строки), хранимые централизованно и повторно используемые в нескольких местах.

### Словарь ресурсов:
```xml
<Window.Resources>
    <!-- Кисть -->
    <SolidColorBrush x:Key="MainColor" Color="#2196F3"/>

    <!-- Стиль для всех кнопок -->
    <Style TargetType="Button">
        <Setter Property="Background" Value="{StaticResource MainColor}"/>
        <Setter Property="Foreground" Value="White"/>
        <Setter Property="Padding" Value="10,5"/>
    </Style>
</Window.Resources>
```

### Использование ресурса:
```xml
<Button Background="{StaticResource MainColor}" Content="ОК"/>
```

### StaticResource vs DynamicResource:
- `StaticResource` — значение берётся один раз при загрузке
- `DynamicResource` — значение обновляется при изменении ресурса

### App.xaml — глобальные ресурсы для всего приложения:
```xml
<Application.Resources>
    <!-- Ресурсы доступны во всех окнах -->
</Application.Resources>
```

---

## 79. Привязка данных WPF (Data Binding)

**Привязка данных (Data Binding)** — механизм автоматической синхронизации данных между источником и элементом интерфейса.

### Синтаксис:
```xml
<TextBox Text="{Binding PropertyName}"/>
```

### Пример — привязка к объекту:
```csharp
// Модель:
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
}
```
```xml
<!-- XAML: -->
<StackPanel>
    <TextBox Text="{Binding Name}"/>
    <TextBox Text="{Binding Age}"/>
</StackPanel>
```
```csharp
// Code-behind:
public MainWindow()
{
    InitializeComponent();
    DataContext = new Person { Name = "Артас", Age = 20 };
}
```

### Режимы привязки:
| Режим | Описание |
|-------|----------|
| `OneWay` | Источник → UI (только чтение) |
| `TwoWay` | Источник ↔ UI (двунаправленная) |
| `OneWayToSource` | UI → Источник |
| `OneTime` | Один раз при инициализации |

### INotifyPropertyChanged:
Чтобы UI автоматически обновлялся при изменении данных, класс должен реализовывать интерфейс `INotifyPropertyChanged`:

```csharp
public class Person : INotifyPropertyChanged
{
    private string name;
    public string Name
    {
        get => name;
        set { name = value; OnPropertyChanged(nameof(Name)); }
    }

    public event PropertyChangedEventHandler PropertyChanged;
    protected void OnPropertyChanged(string propName) =>
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propName));
}
```
