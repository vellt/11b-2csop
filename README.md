```c#
Random random = new Random();

int sz1 = random.Next(6); //[0,5]
//[0,10]
int sz2 = random.Next(11);
// [1,10]
int sz3 = random.Next(10)+1;
// [10,50]
int sz4 = random.Next(41)+10;
// [-10,50]
int sz5 = random.Next(61)-10;
// [-45,45]
int sz6 = random.Next(91)-45;
// [-30, 10]
int sz7 = random.Next(41)-30;
// [-60,-20]
int sz8 = random.Next(41)-60;
// [-20,-5]
int sz9 = random.Next(16)-20;
// [-20,-5]
int sz10 = random.Next(-20,-4);
// [-10,50]
int sz11 = random.Next(-10, 51);

/*
 5 véletlen szám [100,140], írassuk pket ki, és 
számoljuk ki az +, -, *, /, plusz az átlaguk!
 */

Random random1 = new Random();

int szam1 = random1.Next(41) + 100;
int szam2 = random1.Next(41) + 100;
int szam3 = random1.Next(41) + 100;
int szam4 = random1.Next(41) + 100;
int szam5 = random1.Next(41) + 100;

Console.WriteLine($"Az első véletlen szám: {szam1}");
Console.WriteLine($"Az második véletlen szám: {szam2}");
Console.WriteLine($"Az harmadik véletlen szám: {szam3}");
Console.WriteLine($"Az negyedik véletlen szám: {szam4}");
Console.WriteLine($"Az ötödik véletlen szám: {szam5}");

Console.WriteLine($"Összegük: {szam1+szam2+szam3+szam4+szam5}");
Console.WriteLine($"Kivonás: {szam1-szam2-szam3-szam4-szam5}");
Console.WriteLine($"Kivonás: {szam1*szam2*szam3*szam4*szam5}");
Console.WriteLine($"Kivonás:{Convert.ToDouble(szam1)/szam2/szam3/szam4/szam5}");
Console.WriteLine($"Átlaga: {(szam1 + szam2 + szam3 + szam4 + szam5)/5.0}");


/*
 Képezzünk 1 véletlen számot [10,51] között, majd állapítsuk meg
hogy a generált szám, páros avagy páratlan
 */

Random random2 = new Random();
//Console.WriteLine(43%2);
int x = random2.Next(42)+10; 
if (x%2==0) Console.WriteLine($"Az {x} az páros");
else Console.WriteLine($"Az {x} az páratlan");


/*
 Háromszög oldalait generáljuk le random [10, 50], nézzük meg, hogy
szerkeszthető-e a háromszög! Mikor szerkeszthető? Akkor amikor ezek teljesülnek:
(a+b>c) és (a+c>b) és (b+c>a)
 */

Random random3 = new Random();
int a = random3.Next(41) + 10;
int b = random3.Next(41) + 10;
int c = random3.Next(41) + 10;

Console.WriteLine($"Az a oldala: {a}");
Console.WriteLine($"A b oldala: {b}");
Console.WriteLine($"A c oldala: {c}");

if ((a + b > c) && (a + c > b) && (b + c > a)) Console.WriteLine("Szerkeztehtő a 3szög.");
else Console.WriteLine("Nem szerkezthető a 3szög.");

/*
 Egy random számról  [-100,50] döntsük el hogy -30, és 40 között van-e
 */

Random random4 = new Random();

int xxx = random4.Next(151)-100;

if ((xxx >= -30) && (xxx <= 40))
{
	Console.WriteLine($"{xxx} olyan szám, ami -30 és 40 között van.");
}
else
{
	Console.WriteLine("NEM olyan");
}
```