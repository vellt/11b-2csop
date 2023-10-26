```c#
/* Intervallumok képzése a randommal */
Random r = new Random();
int sz1 = r.Next(10); // [0,9]
// [10,60]
int sz2 = r.Next(51)+10;
// [5,10]
int sz3 = r.Next(6)+5;
// [-50, 50]
int sz4 = r.Next(101)-50;
// [-30, 5]
int sz5 = r.Next(36)-30;
// [-60, -20]
int sz6 = r.Next(41)-60;
// [-5,-2]
int sz7 = r.Next(4)-5;

/*
 2 random szám, [0,10] 
írassuk ki a generált értékeket
és nézzük meg melyik a nagyobb, 
ha viszont a 2 egyenlő akkor írjuk ki
hogy a 2 szám az megegyezik!
 */
Random random1 = new Random();
int x1 = random1.Next(11);
int x2 = random1.Next(11);
Console.WriteLine($"{x1}, {x2}");
if (x1 > x2) Console.WriteLine($"az {x1} a nagyobb");
else if (x1 < x2) Console.WriteLine($"az {x2} a nagyobb");
else Console.WriteLine("A két szám egyenlő");

/*
 * generáljunk le 2 random számot [1,10], ezeket írjuk ki!
 * tudjuk meg, hogy a szam1 osztható-e maradék nélkül
 * a szám2-vel. (szam1%szam2)--->0
 */
Random random = new Random();
int x = random.Next(10)+1;
int y = random.Next(10)+1;
Console.WriteLine($"{x} {y}");
if (x % y == 0)
{
	Console.WriteLine($"Az {y} osztja az {x}-et maradék nélkül");
}
else
{
	Console.WriteLine("nem");
}

/*
 "alkohol szaga van": (1)--> igaz, (0)-->nem igaz
"bizonytalan mozgas": (1)--> igaz, (0)--> nem igaz
"fegyver birtoklás": (1)-->igaz, (0)--> nem igaz
(3 változó, [0,1] intervallum randommal)

biztonsági őr mit fog tenni az alábbi esetekben:
("alkohol szaga van" ÉS "bizonytalan mozgas")
	"kirugatja a kidobóval"
("alkohol szaga van" ÉS "bizonytalan mozgas" ÉS "fegyver birtoklás")
	"rendört hív"
("alkohol szaga van" VAGY "bizonytalan mozgas" VAGY "fegyver birtoklás")
	"figyel"
 */
Random random2 = new Random();
int alkohol = random2.Next(2);
int mozgas = random2.Next(2);
int fegyver = random2.Next(2);

Console.WriteLine("Az emberünk: ");
switch (alkohol)
{
	case 1: Console.WriteLine("Alkoholos szagú"); break;
	default: Console.WriteLine("Nincs alkohol szaggal"); break;
}
switch (mozgas)
{
	case 1: Console.WriteLine("bizonytalanul mozog"); break;
	default: Console.WriteLine("Magabiztosan mozog"); break;
}
switch (fegyver)
{
	case 1: Console.WriteLine("van fegyvere"); break;
	default: Console.WriteLine("Nincs fegyvere"); break;
}
if (alkohol == 1 && mozgas == 1) Console.WriteLine("kidobja");
else if (alkohol == 1 && mozgas == 1 && fegyver == 1) Console.WriteLine("rendőrt hív");
else if (alkohol == 1 || mozgas == 1 || fegyver == 1) Console.WriteLine("figyel");
// bónusz feltétel
else if (alkohol == 0 && mozgas == 0 && fegyver == 0) Console.WriteLine("aludhat");

/*
 * random generáljunk 3 értéket [-5,10], ezt írassuk ki
 * készítsünk statisztikát:
 */
Random random6 = new Random();
int num1 = random6.Next(16)-5;
int num2 = random6.Next(16)-5;
int num3 = random6.Next(16)-5;
Console.WriteLine($"{num1} {num2} {num3}");

// ezekből mennyi a pozitív szám
int szamlalo = 0;
if (num1 >= 0) szamlalo = szamlalo + 1;
if (num2 >= 0) szamlalo = szamlalo + 1;
if (num3 >= 0) szamlalo = szamlalo + 1;
Console.WriteLine($"Eddig {szamlalo} db pozitív szám volt.");

// mennyi a negatív szám
int nszamlalo = 0;
if (num1 < 0) nszamlalo++;
if (num2 < 0) nszamlalo++;
if (num3 < 0) nszamlalo++;
Console.WriteLine($"Eddig {nszamlalo} db negatív szám volt.");

// mennyi a páros szám
int parosszamlalo = 0;
if (num1 % 2 == 0) parosszamlalo = parosszamlalo + 1;
if (num2 % 2 == 0) parosszamlalo = parosszamlalo + 1;
if (num3 % 2 == 0) parosszamlalo = parosszamlalo + 1;
Console.WriteLine($"{parosszamlalo} ennyi darab páros szám volt.");

// mennyi a páratlan szám
int paratlansz = 0;
if (num1 % 2 == 1) paratlansz = paratlansz + 1;
if (num2 % 2 == 1) paratlansz = paratlansz + 1;
if (num3 % 2 == 1) paratlansz = paratlansz + 1;
Console.WriteLine($"{paratlansz} ennyi darab páratlan szám van.");

// generáljunk a 3 változóknak új intervallummal [-10,20] random számot,
// írjuk ki az új értékeket
// és nézzük meg mennyi az összegük
num1 = random6.Next(31)-10;
num2 = random6.Next(31)-10;
num3 = random6.Next(31)-10;
Console.WriteLine($"Első szám:{num1}| Második szám: {num2} | Harmadik szám: {num3}");
Console.WriteLine($"Az összegük: {num1} + {num2} + {num3} = {num1+num2+num3}");

// generáljunk a 3 változóknak új intervallummal[-10, 20] random számot,
// írjuk ki az új értékeket
// osszuk el egymással a számokat (osztásnál ügyelni, hogy az egyik legalább double legyen!)
num1 = random6.Next(55)-4;
num2 = random6.Next(55)-4;
num3 = random6.Next(55)-4;
Console.WriteLine($"Első szám:{num1}| Második szám: {num2} | Harmadik szám: {num3}");
Console.WriteLine($"egymással elosztva: {Convert.ToDouble(num1)/num2/num3} ");


// feladat: generáljunk 2 random számot [-30,-20], írjuk ki az értékekekt,
// majd cseréljük meg és megint írassuk ki a 2 változó értékét
Random r1 = new Random();
int n1 = r1.Next(11)-30;
int n2 = r1.Next(11)-30;
Console.WriteLine($"{n1} {n2}");
int temp = n1;
n1 = n2;
n2 = temp;
Console.WriteLine($"{n1} {n2}");

// rendezzünk növekvő sorrendbe 3 értéket
// 5,4,3 <--[-3,10]
Random random3 = new Random();
int num_1 = random3.Next(14)-3;
int num_2 = random3.Next(14)-3;
int num_3 = random3.Next(14)-3;
Console.WriteLine($"{num_1} {num_2} {num_3}");
if (num_1 > num_2)
{
	int t = num_1;
	num_1 = num_2;
	num_2 = t;
}
if (num_1 > num_3)
{
	int t = num_1;
	num_1 = num_3;
	num_3 = t;
}
if (num_2 > num_3)
{
	int t = num_2;
	num_2 = num_3;
	num_3 = t;
}
Console.WriteLine($"{num_1} {num_2} {num_3}"); // növekvő

// A rendezett számokból
// osszuk el a legkissebbet a legnagyobbal, kerekítsünk 3 tizedesre
Console.WriteLine($"a legkissebb {num_1} a legnagyobb {num_3} " +
	$"{Math.Round(Convert.ToDouble(num_1) / num_3,3)}");

// A rendezett számokból a legkissebb értéknek
// a 6. gyökét számoljuk ki, kerekitsd 4 tizedre
double gyok = Math.Pow(num_1, (1.0 / 6));
Console.WriteLine($"a{num_1}-nej a 6. gyöke: {Math.Round(gyok,4)}");

//  A rendezett számokból a legnagyobb értéket emeljük a legkissebb elemre
double hatvany = Math.Pow(num_3, num_1);
Console.WriteLine($"A {num_3} {num_1}.dik hatványa {hatvany}");

//  A rendezett számokból a legnagyobb erteket
//  gyökvonásozzuk, és kerekítsük 2 tizedesjegyre
double gyokvonas = Math.Sqrt(num_3);
Console.WriteLine($" {gyokvonas:0.00}");
```